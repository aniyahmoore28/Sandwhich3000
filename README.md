# Sandwhich3000
## Table of Contents
* [Description](https://github.com/aniyahmoore28/Sandwhich3000#description)
* [Chosen Design](https://github.com/aniyahmoore28/Sandwhich3000#chosen-design)
* [Schedule](https://github.com/aniyahmoore28/Sandwhich3000#schedule)
* [Onshape parts](https://github.com/aniyahmoore28/Sandwhich3000#onshape-parts)
* [Base](https://github.com/aniyahmoore28/Sandwhich3000#base)
* [Bread Board](https://github.com/aniyahmoore28/Sandwhich3000#bread-board)
* [Battery Pack](https://github.com/aniyahmoore28/Sandwhich3000#battery-pack)
* [Arduino Board](https://github.com/aniyahmoore28/Sandwhich3000#arduino-board)
* [Holder For Servos](https://github.com/aniyahmoore28/Sandwhich3000#holder-for-servos)
* [Arms](https://github.com/aniyahmoore28/Sandwhich3000#arms)
* [Overall Reflection](https://github.com/aniyahmoore28/Sandwhich3000#overall-reflection)
* [Arduino Code](https://github.com/aniyahmoore28/Sandwhich3000#arduino-code)

# Description
We are creating a robot arm that is desighned to pick up sandwhiches. Our main "problemm" we are atteping to solve to to make the jobs of busy mothers easyer. Taking the stress of making sandwhiches off their shoulders by programming a robot arm to assemble and ingredients on a peice of bread. we intended to use potenchiamerters as a sort of turning dial to contol the movements of the robot. We will be making a ham and cheese sandwich instead of a peanut butter and jelly because the usage of knives and spoons to get out and spread the condiments as well as the condiments themselves, can be messy and sometimes even dangerous (the knife for the peanut butter). 

# Chosen Design
Chosen Design:
A single arm, with condiments in front of the arm on specific spots dedicated to each condiment aka. Ham, cheese, lettuce. The claw will open and close, turn directions on how it grabs the condiment aka down or sideways. The arm will turn and drop the condiment on the bread, making the arm turn a little more over each time to reach the next condiment. If we choose to make 2 sandwiches, then we can move the arm 180 degrees and do the same thing on the other side of the base. 
Materials

# Schedule
Time Schedule
Week 1: (11/23-12/3)
 have a general idea of what we need to learn in order for this project to work, and have brainstormed and tried to troubleshoot. 
Week 2: (12/4-12/17)
Finish planning and start on prototype and proof
Week 3: (1/3-1/17)
Continue and hopefully finish prototype and proof, look at code a little
Week 4: (1/18-2/10)
Have a prototype made and make code to have the arm moving up and down along with opening and closing the hanger bay. 
Week 5: (2/11-2/14)
Make an engineering notebook (or continue updating throughout the project)and have images and videos as well as code and information to upload and present our project through github. 

---------------
# Arduino Code

```python
#include <Servo.h>

Servo myServo1;  // create servo object to control a servo
Servo myServo2;  // create servo object to control a servo
Servo myServo3;  // adds the servo pin to library so it can be controlled
Servo myServo4; //

int servoPin1 = 12; //pins and the breadboard and arduini that get connected by wires
int servoPin2 = 17;
int servoPin3 = 5;
int servoPin4 = 6;


void setup() {
  // initialize serial communication at 9600 bits per second:
  Serial.begin(9600);


  myServo1.attach(servoPin1);  // attaches the servo on pin 9 to the servo object
  myServo2.attach(servoPin2);  // atteches the servo on pin 2 to the servo object
  myServo3.attach(servoPin3);  // atteches the serov on pin 3 to the servo object
  myServo4.attach(servoPin4);  // attaches the servo on pin 4 to the servo object
}

void loop() {          // Potentiameter #1 (will control the spatula)
  // reads the value of the potentiometer (value between 0 and 1023)
  int analogValue1 = analogRead(A1);
  int analogValue2 = analogRead(A2);
  int analogValue3 = analogRead(A3);
  int analogValue4 = analogRead(A3);

  // scales it to use it with the servo (value between 0 and 180)
  int angle1 = map(analogValue1, 0, 1023, 0, 180);
  int angle2 = map(analogValue2, 0, 1111, 0, 180);
  int angle3 = map(analogValue3, 0, 8923, 0, 180);
  int angle4 = map(analogValue4, 0, 2786, 0, 180);




  // sets the servo position according to the scaled value

  myServo1.write(angle1);
  myServo2.write(angle2);
  myServo3.write(angle3);
  myServo4.write(angle4);

  // print out the value`
  Serial.print("1  Analog: ");
  Serial.print(analogValue1);
  Serial.print(", Angle: ");
  Serial.println(angle1);
  delay(100);

  Serial.print("2  Analog: ");
  Serial.print(analogValue2);
  Serial.print(", Angle: ");
  Serial.println(angle2);

  Serial.print("3  Analog: ");
  Serial.print(analogValue3);
  Serial.print(", Angle: ");
  Serial.println(angle3);

  Serial.print("4  Analog: ");
  Serial.print(analogValue4);
  Serial.print(", Angle: ");
  Serial.println(angle4);
}

```

# Onshape Parts
1) In this picture you can see the many different parts in the making. Some of the shapes were imported from the public library in onshape and others were handmade by Ellen Lynch.
2) This photo is compiled of all of the parts that will be included in our assembly
<img src="https://github.com/aniyahmoore28/Sandwhich3000/blob/main/Images/Capture%20sandwhich%20300(1).PNG" width="250" />

---------------
# Base
1) This stand will hold the upper half of the robot along with the servos, bolts, screws, and acrylic peices of the robot arms
2) Basically this is the base for our project so a lot of effort has to be put into this
3) The hole was cut to save space and be used to hold up the servos 
4) We took parts from the public github library to save time
<img src="https://github.com/aniyahmoore28/Sandwhich3000/blob/main/Images/Stand%20for%20the%20upper%20half.PNG" width="250" />

---------------
# Bread Board
1) The bread baord hold the wires that give power to the multiple potentiameters that will be hooked up
2) Without a bread board we would only be able to hook up the potentiamter 
3) The bread board holds a negitive and positive outlet that allows for multiple connections
<img src="https://github.com/aniyahmoore28/Sandwhich3000/blob/main/Images/bread%20board.PNG" width="250" />

--------------
# Battery Pack
1) The battery pack holds the batteries that will power the arm
2) We borrowed the part from the public parts studio in onshape
3) It will b drilled onto the base of out project
<img src="https://github.com/aniyahmoore28/Sandwhich3000/blob/main/Images/battery%20pack.PNG" width="250" />

--------------
# Arduino Board
1) The arduino board responds to the code it is given when it is plugged into the computer
<img src="https://github.com/aniyahmoore28/Sandwhich3000/blob/main/Images/arduino%20board.PNG" width="250" />

--------------
# Holder For Servos
1) This part will hold servos that will help the arms move
<img src="https://github.com/aniyahmoore28/Sandwhich3000/blob/main/Images/Arms.PNG" width="250" />

--------------
# Arms
1) The arms proved to be the harderst part
2) The arms will hold up the meat and bread while conducting the movements in the code
<img src="https://github.com/aniyahmoore28/Sandwhich3000/blob/main/Images/Holder%20for%20servos.PNG" width="250" />

--------------
# Overall Reflection
overall this project threw multiple curve balls at us forcing us to step out of our comfort zones to acheive our final product. We did develope scope creep early on but we were able to focus our priorities on one thing at a time. My goal was to make the code and get the potenticameter working along with the servo. I did accomplish those things. Ellens job was to create the CAD and design what our robot would look like. So far we have about 80% of our project completed, all thats left to do is finish the little bit of cad that is left and cut out our peices from acrylic. We have come so far and learned new things, i have learned that coding js a lot easier than it looks and coding for multiple things is not always a nightmare. Ellen learned how to overcome her chsllenges in CAD along with her mates , she has been working hard to create a functioning robot for our project. 

