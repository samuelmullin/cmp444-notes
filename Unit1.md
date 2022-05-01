# Unit 1 - Introduction to Robotics

## What is a robot?

A robot has the following defining characteristics:
 - It is an autonomous system
 - It exists in the physical world
 - It senses it's environment
 - It can act on it's environment to achieve some goals

### Autonomy

Autonomy means that a robot cannot simply be teleoperated or controlled by a human.  It must act on the basis of it's own decisions.

### Existance in the physical world

This condition excludes things such as web crawlers, artificial intelligences and robots that exist as programs in a simulated world.  Existing in the physical world is likely the most challenging aspect of creating a true robot, as the rules of the physical world are very strict.

### Sensing it's environment

Simply existing in the physical world is not enough, but the robot needs to perceieve it.   To do this, robots rely on sensors, much like we rely on our senses.  A huge range of robot sensors exist, and anyone designing a robot should consider the robots objectives and what sensors would be most likely to assist the robot in achieving them.  This condition also works to exclude robots that existing in a simulated world, as they don't have  

### Achieving goals

A robot will have a purpose or a set of goals it is trying to achieve.  This could be incredibly simple (follow a line), or it could be incredibly complex (hitchhike across the country).  In order to do so, a robot must make use of the sensors it has been supplied.

## The History of Robots

The word robot was popularized by the Czech playwright [Karel Capek](), having been derived from the Czech words `rabota` ("obligatory work") and `robotnik` ("serf"). 

### Control Theory

Primarly only applied to non-intelligent systems, Control theory is one of the foundations of engineering.  It involves the study of automated control systems, such as those found in airplanes.  It was historically used to study systems that controlled things such as irrigation, temperature control, windmills, steam engines.  Because of it's applications, it was typically studied as a part of mechanical engineering, but it can also be applied to the field of robotics.

### Cybernetics

Cybernetics is control theory applied to biological systems, biological processes and behaviours with the intention of recreating those behaviours in artificial systems.  It can be used to understand something as intricate as the communication of neurons or applied to larger and more generic processes such as behaviour.  Some famous examples of this were Grey Walter's Tortoise(s) and Braitenbergs Vehicles, both of which used simple sensors and motors to mimic animal behaviours.

Grey Walters Tortoise used a series of prioritized reflexes to achieve simple goals (find and move towards a light but away from bright light and move around obstacles).  Braitenbergs vehicles were more of as series of thought experiements, designing robots that were meant to mimic things like being attracted to or afraid of light.  This was done by creating *excitatory* or *inhibitatory* connections between sensors and motors depending on the desired behaviour.

Cybernetics doesn't really exist today, though research into biomemetic robot behaviour is commonplace.


### Artificial Intelligence

To be considered intelligent, a machine needs to do the following:

- Use internal models of the world
- Search through possible solutions
- Use planning and reasoning to solve problems
- Represent information symbolically
- Implement hierachical system organization
- Execute sequential programs
  
Early artificial intelligence (AI) was mostly focused on purely deliberate control, because the field was new but also because the early robots lacked processing power and were large, clunky machines compared to what can be built today.  Modern AI uses reactive control, hybrid control and behaviour based control, all of which will be discussed later.  

### 

## Robot Components

Based on the requirements for a robot, we can infer that a robot will need the following:

- A body which exists in the physical world
- Sensors to measure characteristics of it's environment
- Motors, sensors, lights, etc (Effectors/Actuators) to allow it to take action
- A controller to embed it's program into to imbue it with autonomy

### Physical Body

A body imparts on a robot the same physical limitations that all creatures have  - it has to obey the laws of physics, thermodynamics, etc.  It also forces it to be aware of what is around it.  It's physical body would also include all the sensors, effectors, actuators, controller(s) and a power source.

### Sensors

In order to be aware of it's surrounding, a robot requires sensors.  It's sensors determine what it is able to perceive and by extension what it is capable of doing, (or, conversely, it's purpose determines what sensors it will require to be successful in it's goals).  

Sensors also allow the robot to understand it's state and the state of the world around it.  Not all state is obvious - it can be categorized as observable, partially observable and hidden.

State can be be discrete, (such as a relative direction, or a colour) or it can be continuous (9.8m/s ^ 2).

State has a defined space, which indicates the amount of possible unique states it can be in. A button can be on or off, and thus has 2 discrete states and a state space of 2.  A photoresistors state might be determined by the granularity offered by it's analog-digital-converter.  Adding more sensors increases the amount of state space a system has by growing it's perceptual space.

State can be considered to be internal or external.  Internal state is the state of the system - a robots internal state would be all the things it can percieve about itself (where is my arm?  what level does my battery have?), and external state is all the things it can percieve about it's world (is it dark?  is there a lot of noise?).  Some forms of internal state are representative, such as how a robot vaccuum might store a map of the spaces it has cleaned in a room.

### Effectors/Actuators

Effectors allow the robot to take action, but they require actuators to function.  A wheel is an effector, where a motor is an actuator.  Together, they allow for locomotion and manipulation, which are also describe the two major subfields of robotics:  Mobile robotics and manipulator robotics.

### Controllers

In order for a robot to be autonomous, it needs to be able to work to achieve it's goals by observing and acting on it's encironment.  In order to do that, it needs act on data consumed from its sensors and use it's effectors/actuators to take action.  Controllers allow the robot to process the data from sensors and act on it.  A robot may have a central controller coordinating everything, or it may have a number of disparate controllers working independently.  

Autonomy can be partial or complete.  Machines without at least partial autonomy are not considered robots.

## Food for Thought

### Is a thermostat a robot?

A theromostat is not autonomous, so it fails the first test of being a robot.

### Is a toaster a robot?

A toaster is not autonomous, so it fails the first test of being a robot.

### Is a web crawler a robot?

A web crawler is autonomous, but it does not exist in the physical world and is therefor not a robot.

### Is Hal from 2001 a Space Odyssey a robot?

Hal exists in the physical world and has sensors that allow it to observe it.  It can act on the information that is has found.  It can act autonomously (I'm afraid I can't let you do that).  Hal seems to check all the boxes to indicate that it is in fact a robot. 


### Reflections on the importance of robots mirroring biological systems

It is largely unimportant for robots to be inspired by biological systems, though they are a fantastic source of inspiration, unless the robot is being built for a purpose that requires it to integrate into a biological system or solve a problem that a specific biological entity has already solved.  Outside of that, I think there's a certain poetry in biomimicry that is worth ascribing value to.

### What do you think is more difficult, manipulation or mobility?

I don't think there's a straightforward answer to this question - the difficulty is relative to the task being assigned.  In the simplest scenarios, Mobilty is likely easier that manipulation.  Mobility can be achieved with minimal internal state and no external state - go forward.  Manipulation requires knowledge of external state (what is being manipulated, what is the state of the affector/actuator we are using to manipulate it).  However, in more complex scenarios (navigating a dangerous environment or avoiding obstacles), the difficulty of mobility greatly increases.

### How large do you think your sensor space is?

The human sensor space is huge, given the complexity of our nervous system.  The baffling thing to consider, though, is that most of our senses are quite limited compared to other species.  There are creatures that can se

### What are some examples of things that are observable, partially observable and hidden to you?

Observable:

- The colour of paint used on the wall
- The texture of the ceiling
- Whether or not the radio is switched on

Partially Observable:

- The temperature of the room - I can likely estimate the temperature based on my comfort level and knowledge of my own internal state (did I just do a bunch of cardio?) - but I can't provide a specific value without using some external resource.
- The emotional state of another person

Hidden:
- What's on the other side of a door
- The level of infrared light in the room
- The temperture next door


