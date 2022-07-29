

- Shiny dashboards consist of 2 main elements the `ui` and the `server` files
- Shiny dashboards are not great for high user traffic but can still handle mutliple user sessions. Hosting on RStudio is an option but shiny server can be hosted on your own system or containers.
- A great practice is to store shiny dashboards as R Packages to be distributed for interactive reproducable analysis.
- Shinydashboard and shinydashboard+ are packages that build off the shiny package base to allow greater aesthetic elements and more functionality with the web app.
- For unit testing shiny applications there is shinytest
  and for load testing there is shinyloadtest
- for making sure shiny apps load quickly you can use `profvis` and other methods to tackle your bigger and slower processes, another is to not load csv data into shiny directly, if loading data like this do your ETL first and save data as feather files, feather is slower to write but faster to read than csv's
- another would be to implement plot caching if the plots are taking a while to load
- Great presentations of your shiny apps like a walk along tutorial: [cicerone](https://github.com/JohnCoene/cicerone)

## Documentation

<iframe width="560" height="315" src="https://www.youtube.com/embed/Wy3TY0gOmJw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Code

```r
########################################
# A basic example of a shiny dashboard #
########################################
library(shiny)

# Define UI for application
shinyUI(fluidPage(
# Application title
titlePanel("Old Faithful Geyser Data"),
# Sidebar with input
sidebarLayout(
 sidebarPanel(
  sliderInput("bins",
     "Number of bins:",
     min = 1,
     max = 50,
     value = 30
  )#sliderInput
 ),#sidebarPanel
 # Show a plot of the generated distribution
 mainPanel(
  plotOutput("distPlot")
 )#mainPanel
)#sidebarLayout
))#shinyUI(fluidPage(

# Define server logic required to draw a histogram
shinyServer(function(input, output) {

output$distPlot <- renderPlot({

 # generate bins based on input$bins from ui.R
 x    <- faithful[, 2]
 bins <- seq(min(x), max(x), length.out = input$bins + 1)

 # draw the histogram with the specified number of bins
 hist(x, breaks = bins, col = 'darkgray', border = 'white')

})#renderPlot
})#shinyServer
```
