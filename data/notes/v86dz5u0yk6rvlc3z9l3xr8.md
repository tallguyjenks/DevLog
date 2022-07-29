
## Creational

> How objects are created

### Singleton

- a type of object that can only be instantiated once

### Prototype

- cloning and inheritance. 

### Builder

- Method chaining and instead of passing all arguments at instantiation it can be used to have setter methods that are called with method chaining so the object that gets returned after each method is progressively built up into its final form

### Factory

- instead of using `new` keywords to instantiate an object you use a function to do it for you

## Structural

> How objects relate to each other

### Facade

- a simplified API to hide other low level details in your code while still implementing them

![facade pattern](/assets/images/2022-07-05-18-23-04.png)

### Proxy

- using a stand in object in place of the original that can also contain side effects and additional behavior

## Behavioral

> How objects behave with each other

### Iterator

![iterator](/assets/images/2022-07-05-18-28-20.png)

### Observer

- allows many objects to intercept events broadcasted by other objects.
- It's a one to many relationship (like a radio tower and several receivers)

![Observer](/assets/images/2022-07-05-18-30-52.png)

### Mediator

- middle man or broker
- like runways and airplanes (is the runway clear for the airplane to land)
  - Instead of having all the objects talking to each other via a many to many relationship
- mediator is like an air traffic controller coordinating between airplanes and runways

### State

- where an object behaves a specific way based on a finite number of states

![bad, switch hell](/assets/images/2022-07-05-18-34-52.png)

![state machine implementation](/assets/images/2022-07-05-18-35-17.png)

![implemented methods](/assets/images/2022-07-05-18-35-41.png)

![when state changes. object will behave in a completely different way](/assets/images/2022-07-05-18-36-02.png)