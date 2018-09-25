## Burglar Alarm
A simple burglar alarm built using an ATtiny45. You can attach it anywhere and will it will inform when someone tries to steal something.

![Alarm](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/main.jpg)


#### Story

We are going to build a burglar alarm, for that we need to use sensor that sense presence or something as input device and we also need output device as a alarm the people here we are using buzzer. first we need to choose the sensor, I selected Hall effect sensor because it's very simple and easy to use, it's working based on the proximity of magnet, so we can measure the magnetic field based on the output voltage and if we can put the sensor and magnet between our door and we can program it to alarm when the magnetic field is low. and it's very low power and smaller footprint, so let's get start to make.

here Iam using **A1302-Linear Hall-Effect Sensor**  ([datasheet!(https://www.allegromicro.com/~/media/Files/Datasheets/A1301-2-Datasheet.ashx)), and you can use any Hall-effect sensor for this project.

#### Sensor - A1302 - Continuous-Time Ratiometric Linear Hall-Effect Sensor

![sensor](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/004.jpg)

#### Features

- Low-noise output
- Fast power-on time
- Ratiometric rail-to-rail output
- 4.5 to 6.0 V operation
- Solid-state reliability
- Factory-programmed at end-of-line for optimum performance
- Robust ESD performance

![blockdiagram](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/002.jpg)

#### Output Device - Piezo Buzzer

![buzzer](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/003.jpg)

Piezo buzzer is an electronic device commonly used to produce sound. Light weight, simple construction and low price make it usable in various applications like car/truck reversing indicator, computers, call bells etc.

Piezo buzzer is based on the inverse principle of piezo electricity discovered in 1880 by Jacques and Pierre Curie. It is the phenomena of generating electricity when mechanical pressure is applied to certain materials and the vice versa is also true. Such materials are called piezo electric materials. Piezo electric materials are either naturally available or man made. Piezo-ceramic is class of man made material, which poses piezo electric effect and is widely used to make disc, the heart of piezo buzzer.

![piezo](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/005.gif)

When subjected to an alternating electric field they stretch or compress, in accordance with the frequency of the signal thereby producing sound.

A piezoelectric disk generates a voltage when deformed (change in shape is greatly exaggerated).

#### Sensor Testing

First we arr testing the hall-effect sensor and Buzzer with using arduino after that we are going to design custom pcb and make it next level

![sensor test](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0014.jpg)



#### Testing Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/gFu8SRU2_eU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

now we can confirm sensor and code are working fine, next we are going to make mill a custom pcb using CNC milling machine.

#### Circuit Design

I used **Eagle** to design the circuit.

![design](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0022.png)

and routed and completed the PCB designing

![pcb](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/009.png)



#### PCB Milling

I exported board file as Monochrome PNG image file and milled with Modela MDX CNC machine.

![trace](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0012.png)
![drill](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0011.png)
![drill](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0010.png)

for milling I used Flame Resist grade PCB, and milling completed perfectly.

![milled pcb](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0013.jpg)



#### Soldering Components

- ATtiny45/85 x 1
- Buzzer x 1
- Hall-effect sensor x 1
- 0.1 uF Cap x 1
- Coil cell battery x 1
- Coil cell battery Holder x 1
- ISP header x 1

![components](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0015.jpg)


soldered components successfully,

![soldered](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0017.jpg)


[soldered](https://raw.githubusercontent.com/salmanfarisvp/fablab-projects/master/BurglarAlarm/img/0016.jpg)

```
void setup()
 { 
  pinMode(2, INPUT_PULLUP);
  pinMode(3, OUTPUT);
 }
void loop()
 {  
    int data = analogRead(2);
    if (data >= 500 ) {   
        digitalWrite(3, HIGH);
        }  
    else{   
         digitalWrite(3, LOW);  
        }
 }

 ```

#### Demonstration

<iframe width="615" height="352" src="https://www.youtube.com/embed/Aqp0Zq_OJ4g" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

the same alarm we can use it in multiple places.

<iframe width="615" height="352" src="https://www.youtube.com/embed/o99wMoNA4Zo" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>


#### Thanks 