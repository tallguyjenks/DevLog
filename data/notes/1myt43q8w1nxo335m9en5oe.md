

```r
#### engine size / highway MPG ####
ggplot(data = mpg) + 
  geom_point(mapping = aes(x = displ, 
						   y = hwy)
			 )
ggplot(data = mpg) + #--------------------------------------------------# Play with changing color to size 
  geom_point(mapping = aes(x = displ, #-------------------------------# (discrete variable "class" to ordered aesthetic "Size" not advised)
						   y = hwy, 
						   size = class)
			 )
ggplot(data = mpg) + #--------------------------------------------------# Transparancy of the points
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   alpha = class)
			 )
ggplot(data = mpg) + #--------------------------------------------------# Shape of the points
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   shape = class)
			 )
ggplot(data = mpg) + #--------------------------------------------------# Add Colors by class and add this to the aesthetic layer
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   color = class)
			 ) 
ggplot(data = mpg) + #--------------------------------------------------# change color of the points
  geom_point(mapping = aes(x = displ, 
						   y = hwy), 
			 color = "blue"
			 )
ggplot(data = mpg) + #--------------------------------------------------# change size and color to continious variables and shape to a categorical variable
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   color = year, 
						   size = cyl, 
						   shape = drv)
			 )
ggplot(data = mpg) + #--------------------------------------------------# Making the save variable cover multiple fields
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   color = cyl, 
						   size = cyl, 
						   shape = drv)
			 )
ggplot(data = mpg) + #--------------------------------------------------# testing the "stroke" argument
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   color = cyl, 
						   size = cyl, 
						   shape = drv, 
						   stroke = 5)
			 )   
ggplot(data = mpg) + #--------------------------------------------------# passing a condition into a aesthetic argument instead of the straight variable
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   color = displ < 5, 
						   size = cyl, 
						   shape = drv, 
						   stroke = 5)
			 )   
ggplot(data = mpg) + #--------------------------------------------------# Highway MPg / Engine Cylinders
  geom_point(mapping = aes(x = hwy, 
						   y = cyl)
			 )
ggplot(data = mpg) + #--------------------------------------------------# Type of car / What "Wheel Drive" the car is (F,B,4)
  geom_point(mapping = aes(x = class, 
						   y = drv)
			 )


#### Facets on descrete variables ####

ggplot(data = mpg) + 
  geom_point(mapping = aes(x = displ, 
						   y = hwy)
			 ) +
  facet_wrap(~ class, nrow = 2) #-------------------------------------# the tilda "~" means a formula not akin to an equation

ggplot(data = mpg) + #--------------------------------------------------# testing facet grid
  geom_point(mapping = aes(x = displ,
						   y = hwy)
			 ) +
  facet_grid(drv ~ cyl) 

ggplot(data = mpg) + #--------------------------------------------------# testing facet grid 2
  geom_point(mapping = aes(x = displ, 
						   y = hwy)
			 ) +
  facet_grid(. ~ cyl) #-----------------------------------------------# puts cyl facet into columns since argument is (r,c)

ggplot(data = mpg) + #--------------------------------------------------# testing facet grid 3
  geom_point(mapping = aes(x = displ, 
						   y = hwy)
			 ) +
  facet_grid(drv ~ .) #-----------------------------------------------# puts drv facet into rows since argument is (r,c)



#### Changing Geoms ####
ggplot(data = mpg) + 
  geom_smooth(mapping = aes(x = displ, 
							y = hwy)
			  ) #-----------------------------------------------------# from point to smooth


ggplot(data = mpg) + #--------------------------------------------------# line type based on a variable
  geom_smooth(mapping = aes(x = displ, 
							y = hwy, 
							linetype = drv)
			  )
ggplot(data = mpg) + #--------------------------------------------------# line type based on a variable with points and colors to show the seperation
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   color = drv)
			 ) + 
  geom_smooth(mapping = aes(x = displ, 
							y = hwy, 
							linetype = drv, 
							color = drv)
			  )


ggplot(data = mpg, mapping = aes(x = displ,
							   y = hwy)
	 ) + 
  geom_point() +
  geom_smooth()


ggplot(data = mpg) + 
  geom_point(mapping = aes(x = displ, 
						   y = hwy)
			 ) +
  geom_smooth(mapping = aes(x = displ, 
							y = hwy, 
							linetype = drv), 
			  show.legend = F
			  )


ggplot(data = mpg) + 
  geom_point(mapping = aes(x = displ, 
						   y = hwy, 
						   color = drv)
			 ) +
  geom_smooth(mapping = aes(x = displ, 
							y = hwy, 
							linetype = drv, 
							color = drv), 
			  show.legend = F
			  )


#### Bar Plots ####

ggplot(data = diamonds) +
  geom_bar(mapping = aes(x = cut))


```
