---
layout: post
title:  "Pick and Place"
summary: "Automated placement of SMD arrangement on PCBs"
# author: xplor4r
date: '2021-06-21 1:35:23 +0530'
category: ['engineering','mechatronics', 'programming','CAD']
tags: jekyll
thumbnail: /assets/img/posts/pnp_complete.png
keywords: pick and place, CNC, 3d Printing, mechatronics, design, engineering, CAD, Solidworks
usemathjax: false
permalink: /portfolio/pick-and-place/
---
<br />
<h1> What is a Pick and Place </h1>
<p>
A pick and place machine is a device that automates the placement of surface-mount components on PCB boards. This is a CNC machine using systems almost identical to that of CNC routers, 3D Printers, Laser cutters, and the like. An xy gantry system is used with a nozzle attached to a vacuum pump that pneumatically attaches and detaches components for their placement on a PCB. In my case, I repurposed a 3D printer motor control board to control the subsystems of the device and configured the firmware (Marlin) to suit my specific application.
</p>
<br />

<h2>Movement System</h2>
<br />
<img
      style="width: 30%; height:30%; float:left; margin-bottom:10px"
      src="{{site.url}}{{site.baseurl}}/assets/img/posts/corexy.png"
      alt="{{ post.title }}"
    />
<p>
The initial design of this pick and place used the traditional xy gantry system, where the motors individually controlled the x and y axes of the machine. The problem with this was that it required the x-axis motor to be mounted on a moving rail.
</p>
<img
      style="width:30%; height:30%; float:right"
      src="{{site.url}}{{site.baseurl}}/assets/img/posts/pnp_corexy.png"
      alt="{{ post.title }}"
    />

<p>
 This design was unstable, so after taking apart a 3d printer and observing the system used for that, I decided to implement that design, the corexy gantry, into my pick and place. This provided the advantage of having the motors controlling the axes mounted independently of any moving parts, greatly increasing stability.
</p>
<br />

<h2>Electronics</h2>
<br />
<img
      style="width: 40%; height:40%; float: left"
      class="card-img-top"
      src="{{site.url}}{{site.baseurl}}/assets/img/posts/pnp_electronics.png"
      alt="{{ post.title }}"
    />
<p>
The electronics for this project are quite straightforward as it consists of the standard connections of a 3D printer with all of the customizations done through the Marlin firmware that is flashed onto the board via microUSB. Stepper motors are used throughout this configuration due to their high accuracy and controllability. Additionally, the fan terminals were repurposed for the solenoid to control the engagement and disengangement of the pump at the nozzle.
</p>
<br />

<h2>Takeaways</h2>
This is the first project of this scale I ever worked on. I came into this task knowing virtually nothing about what the systems consisted of or how it worked on a technical level. Through developing this project, I learned about stepper motors, how to read and understand datasheets, firmware configuration, mechanical assembly, and even improved on my CAD skills. Consequently, I also came to understand how CNC systems work, how they are designed and built.