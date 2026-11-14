---
title: "Robotic End Effector (Critical Matter Group)"
excerpt: "Building a robotic end effector with the CM Group at MIT Media Lab"
date: 2026-06-01
layout: single
header:
  teaser: /assets/images/projects/cm_urop/cover_2.jpg
teaser_position: "50% 30%"
toc: true            # optional: table of contents on the right

gallery_1:
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643295/IMG_2263.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643295/IMG_2263.heic
    alt: "croc"
    title: "Croc End Effector"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643283/IMG_2250.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643283/IMG_2250.heic
    alt: "spin"
    title: "Melt-spun objects"

gallery_0:
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643261/IMG_1492.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643261/IMG_1492.heic
    alt: "lead"
    title: "Lead screw initial design"

gallery_2:
  - video: IMG_1817
  - video: IMG_2047

gallery_3:
  - video: IMG_1997
    title: Slip rings are pretty neat
  
gallery_4:
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643264/IMG_1779.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643264/IMG_1779.heic
    alt: "spin"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643268/IMG_1784.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643268/IMG_1784.heic
    alt: "spin"
  - video: IMG_2224
  - video: IMG_2233
    title: "Wrapping a pair of wire strippers"
  - video: IMG_2255
    title: "Sergio wrapping a model foot"
  - video: IMG_2256
    title: "Sergio wrapping his real foot"

gallery_5:
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643310/Screenshot_2026-11-14_023700.png
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643310/Screenshot_2026-11-14_023700.png
    alt: "cad"
    title: "Final CAD"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643298/IMG_3279.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643298/IMG_3279.heic
    alt: "ballscrew"
    title: "Initial ball screw design"
  - video: IMG_3288
    title: "Ball screw actuation"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643300/IMG_3281.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643300/IMG_3281.heic
    alt: "weigh"
    title: "Weighing the end effector"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643300/IMG_3281.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643300/IMG_3281.heic
    alt: "weigh"
    title: "Weighing the end effector"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643304/IMG_4340.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643304/IMG_4340.heic
    alt: "final"
    title: "Construction of final design"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643306/IMG_4350.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643306/IMG_4350.heic
    alt: "final"
    title: "Construction of final design"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643308/IMG_4353.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794643308/IMG_4353.heic
    alt: "final"
    title: "Construction of final design"
---

This was a project that I undertook while working at the [Critical Matter Group](https://www.media.mit.edu/groups/critical-matter/overview/){:target="_blank" rel="noopener noreferrer"} in the MIT Media Lab throughout my freshman year. In short, it's an end effector mounted on a UR20 robotic arm that is capable of automatically melt-spinning polymer fibers around objects. In short, the objectives were to:
- Repeatedly stretch PCL into fibers through a dual heatbed/nail setup
- Modulate the width of the stretched PCL
- Wrap the stretched fibers around an object
It does this by closing and opening two crocodile "jaws" to create the fibrous strands, then rotating the entire jaw system around an object to wrap it. Hence, it got the nickname "Croc End Effector"

{% include gallery id="gallery_1" class="breakout gallery-equal" height="400px" shift="4vw" total_width="1300px"%}

This end effector underwent 5 iterations during the time I worked on it. In the earlier iterations, I was responsible for the entire system, from component selection, to CAD, to electronics design, to assembly. As more team members joined the project, I was able to focus more on the main frame design, system-level electronics, and assembly

The project can be broken up into 2 main pieces of hardware: a rotor (PCL system) and stator (houses motor that spins rotor)

The components of the rotor include:
- **Heatbeds**: The polymer we used for testing is PCL (polycaprolactone), which has a low melting point of around ~60C. We used ceramic heaters (the same kind in 3D printer nozzles!) mounted to an aluminum bed to hold the PCL, serving as the "jaws". Each "jaw" served a different purpose:
	- PCL Bed: This contained a heated, softened layer of PCL
	- Nail Bed: This heated up a set of aluminum nails so that each would melt and pull away a fiber as the jaw opened
- **Jaw Actuator**: Reliably open and close the jaws
- **Electrical System**: Power regulation, communication to UR20 and remote station
The components of the stator include:
- **Rotation Motor**: Be robust enough to spin a complex, heavy system
- **Electrical System**: Provide power and communication to an actively rotating device

## Early Experimentations
In the earlier iterations of this project, I was responsible for all mechanical/electrical design, assembly, and testing.

#### Jaw Actuator
The challenge with this design was reliably closing the jaws with enough force to fully set the nails into the PCL bed, while being able to pull, but not break the fibers on release. In addition, because the entire system was rotating, it had to be symmetrical and lightweight.

I experimented with several different designs, including a stepper-controlled lead screw that modulated a singular jaw (design and assembly done in a single week!). After this proved to be too slow, unstable, and unbalanced, I wanted to test a servo-driven 4-bar linkage mechanism.

{% include gallery id="gallery_0" class="breakout gallery-equal" height="400px" shift="4vw" total_width="1300px"%}

The concept behind the linkage design was driven by the realization that the jaws were only required to be level with each other, and that rotary motion was far simpler to implement than linear motion. 

This design actually worked quite well, and was the first demonstration of an automatic melt-spinning system in the lab! However, it fell short in rigidity due to tolerances in the ball bearing integration design, and servos proved to be slightly underpowered in driving the heatbeds. Furthermore, one fatal flaw of this design was the **change point** of the linkage system, in which the linkages had a chance of collapsing on itself when they passed through their rotation point and became collinear.

{% include gallery id="gallery_2" class="breakout gallery-equal" height="400px" shift="4vw" total_width="1300px"%}


#### Rotor Frame and Stator Design
The most important aspects of the frame are rigidity and symmetry. I centered my designs around these requirements.

My original design had the entire rotor system independently powered from its own battery, controlled wirelessly through an ESP32. While this worked in theory and would avoid dealing with wires between rotating systems, it proved to be impractical due to the high current draw of the heatbeds and the challenge of placing the battery in a symmetric way.

While iterating, I remembered this [Tom Scott Video](https://www.youtube.com/watch?v=gisdyTBMNyQ){:target="_blank" rel="noopener noreferrer"} that introduced me to slip rings, and realized I could implement them into my design. Slip rings allow electrical signals to travel between a stationary base to a rotating structure, achieving this with metal "brushes" that glide across conductive rings as it spins.

{% include gallery id="gallery_3" class="breakout gallery-equal" height="400px" shift="4vw" total_width="1300px"%}

The next iteration featured a slip ring that carried all power and communications through the stator and up to the rotor.

#### Heatbeds
Early iterations of the heatbeds used an array of PI heating elements that contacted the PCL directly. The nail bed is mounted to an aluminum plate, which is also heated up with PI heating elements.
#### Electrical System
As the components we used requested 5V, 6V, 9V, 12V, and 24V, I used buck converters to step-down voltages so each component got what they wanted. An Arduino connected to the stator commanded all motors and actuators, and I wrote a simple script to calibrate and send commands through USB Serial.

{% include gallery id="gallery_4" class="breakout gallery-equal" height="400px" shift="4vw" total_width="1300px"%}

## Later Iterations
As I progressed with the design of this end effector, a lot more progress was made in terms of reliability :). Yuxiang and Eleni also joined the Croc team, where they worked on the heatbeds and stator design.

#### Jaw Actuator
Because of their robustness, speed, and power, I switched to dual NEMA17 stepper motors driving 300mm SFU1204 ball screws, each controlling one jaw. To fix the rigidity issue from the previous lead screw design, I mounted each jaw on MGN9 linear rails that spanned the entire actuation range. This design proved to be incredibly robust, powerful, and precise enough for all jaw movements. 
#### Rotor Frame Design
For ease of assembly, the first of my iterations with the dual ball screw design had the entire system mounted on a piece of laser-cut acrylic. But as the end effector grew in complexity, we decided to 3D-print the entire frame so all components could be seamlessly integrated. 

Due to the size of the frame, it was impossible to print on a single printbed. We broke it up into 3 components (centerpiece and 2 rotationally symmetric side parts) that fit together with dovetails (thank you Yuxiang for the suggestion!)


#### Electrical System
While selecting components for this iteration, we were incredibly deliberate about voltages that each component requests, trying to simplify the power management system as much as possible. Ultimately, we ran all actuators and heatbeds at 24V, only using a single buck converter to bring it down to 6V for the microcontroller. 

We used an Arduino Nano ESP32 that communicated to a controller using the ESP-NOW protocol.

I also implemented limit switches in these iterations so the stepper motors could be calibrated. 


{% include gallery id="gallery_5" class="breakout gallery-equal" height="250px" shift="4vw" total_width="1300px"%}


Special thanks to [Yuxiang Cheng](https://www.yuxiang.design/){:target="_blank" rel="noopener noreferrer"}, [Sergio Mutis](https://www.sergiomutis.com/){:target="_blank" rel="noopener noreferrer"}, [Eleni Morales](https://elenimorales.com/){:target="_blank" rel="noopener noreferrer"}, and the entire Critical Matter team for their support!
