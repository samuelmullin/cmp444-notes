# Unit 2 - Robotic Movement 1 - Locomotion

## Mechanisms of Robotic Movement

Movement in robot is dependent on actuators and effectors.  An effector is the thing that has an impact on it's environment - such as a wheel or an arm.  An actuator is the mechanism that enables the effector to impact it's enviroment - such as a motor or a servo.

## Actuation (active vs passive)

Though most forms of robots are focused on active actuation (using power to drive a motor, etc), it's also possible to use passive actuation but driving effectors with potential energy.  One example of this is a [passive walker](link here)

## Actuator Types

Common actuator types include:

- Electric Motors
- Hydraulics/Pneumatics
- Photoreactive Materials
- Chemically Reactive Materials
- Thermally Reactive Materials
- Piezoelectric Materials

## Motor types

### DC Motors

DC motors are some of the most common actuators, due to their availability, size, cost and ease of use.  The use magnets, wire and current to convert electrical energy into mechanical energy.    Providing proper volatage to a DC motor is essential, because providing too much will cause excessive wear and tear.

DC motors draw current proportional to the work they are doing.  This means that going up a hill will require more current than dricing on a flat surface, for example.   The more current that is being consumed, the more torque (rotational force) will be produced at the shaft.  The amount of power a motor can produce is proportional to the product of its torque and the rotational velocity of the shaft.

Most DC motors provide unloaded speeds between 3000 and 9000 rotations per second.  In order to reduce this to a level that is appropriate for typical robot usage, gears are used to adjust the force and torque output of motors.

### Gears

Gears generate force proportional to the ratio of their radius and the torque applied to them.  We describe the gear closer to the shaft as the input gear, and the gear further from the shaft as the output gear. As a general rule:

If the output gear is larger than the input gear, torque increases and speed decreases.
If the output gear is smaller than the input gear, torque decreases and speed increases.

Multiple gears can be ganged together in series to produce different results, and when they are, their effects are multiplied;  for example, two 3:1 gears ganged together would produce a 9:1 total reduction.

Gear teeth need to be designed to fit together precisely - the more precise the gearbox, the more expensive and complicated it will be.  Loose gears results in backlash.  Gears that are too tight increase friction and waste energy.

### Servos

Where DC motors are designed for continuous movement, servos are designed for precision movement within a range.  Servos are made from DC motors, but add a gearing reduction, a sensor to track the torque/rotation of of the shaft and a circuit to meet either the torque or position requested.

Rather than receiving continuous input, servos recieve waveforms sent using pulse-width-modulation - PWM.  The longer the pulse, the bigger the movement that is being requested.  These pulses need to be very precise, otherwise the servo will experience jitter or try to turn to an angle it does not support, damaging itself.

Servos provide two methods of control:

Position control - attempts to lock the shaft in a specific position, regardless of the torque required
Torque control - attempts to provide consistent torque, regardless of the shaft position


## Degrees of freedom

Degrees of freedom (DOF) is a measurement of the minimum number of coordinates required to specify the motion of a given object.  An unrestricted object has a total of six DOF.  Three of these DOF are translational (x, y, z position) and three are rotational (roll, pitch, yaw).

Roll - rotation anchored on the y axis
Pitch - rotation anchored on the x axis
Yaw - rotation anchored on the z axis

Some DOF are controllable, and some are not.  A degree of freedom is considered controllable if there is an actuator acting on that DOF - otherwise it would be uncontrollable.  A car, for example has three total DOF, but since it has no actuator to allow it to move sideways, only two are controllable.

If the total DOF is equal to the controllable DOF in a robot, it's called holonomic.  Otherwise, it's called non-holonomic.  If the controllable DOF is greater than the total DOF, the robot is called redundant.

Some examples:

Holonomic:  A helicopter has six DOF, and all are controllable.
Non Holonomic: A car has three DOF, but only two are controllable.
Redundant: The human arm has a total of six DOF, but has seven controllable DOF

## Stability

In order to accomplish their goals, robots need to be stable - they cannot wobble, lean or fall over easily.  Stability can be described as either static - which means a robot can stand still without falling over (and without expending energy) or dynamic - which requires constant, active control.  With enough legs, a robot could even be statically stable while walking.  The extra legs provide safety, trading off agility and energy efficiency.

How a thing walks is called it's gait.  For a robot, the following properties of gaits can be adjusted depending on the robots goals:

- Stability
- Speed
- Energy Effciency
- Robustness
- Simplicty

While they are not common in nature, wheels are a very common alternative to legs in modern robots.  Their comparative simplicity, inherent static stability and efficiency make them an ideal choice for many projects.  


## Locomotion

Locomotion is achieved through a combination of effectors and actuators - in robots, we most commonly see this in the form of legs, wheels or rotors.  Less commonly, we might also see arms or flippers, or any number of other mechanisms.  With respect to robots, the concerns that are addressed in locomotion are how we can get to a particular location, or how we can follow a particular path/trajectory.  Trajectory planning is a complex process, depending on wheter the requirement is to find the optimal trajectory (shortest, safest, most effcient, etc).  Trying to get to a specific point without the requirement to follow a specific trajectory is called navigation.


## Food for Thought

### How would you measure a motors torque?

There are two options available:

  - Directly measure the torque using a tool such as a strain gauge
  - Indirectly neasure the torque by measuring the power input and the rotational speed of the shaft and using that to calculate the torque.


### How many DOF are there in a human hand?

Each finger has four, one in each joint and two at the base. (16)
The thumb has five, one at the joint, two at the base and another two that allow it to be opposable (5)
The wrist has six, being able to flex up and down, turn left and right and being able to rotate clockwise or counterclockwise (6)

This gives us a total of 16 + 5 + 6 = 27 degrees of freedom in total for the human hand.

### How does mapping software find the optimal path

Having just completed an Algorithm's course, I can confidently say that mapping software is most commonly applying [Dijkstra's Algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm), at least in part.  Simple mapping software might do this with static values, while google maps utilizes phones running it's application to provide real time traffic data and adjust the distance between nodes accordingly.