---
layout: post
title: "Hello World board"
comments: true
description: "Description"
keywords: "Keywords"
---

In the previous week i've learned to mill and stuff a PCB, and how to program a PCB. Next i'll make my own Hello World board. For this i have to learn how to work with Kicad. I also have to figure out which components to use and which value the components need to have. I already have the Fab lib for Kicad installed.

I'll use this schematic supplied by Henk as a base and build on top of that:

![hello](/assets/images/2022-05-23-hello-world/hello01.png)

##### Components/BOM

The schematic contains the following components:

- ATtiny412
- Button_B35N
- LED 
- Capasitor (value unknown)
- Phototransistor_PT15-21C-TR8
- Resistor (value unknown)
- Pinheader FTDI 1x06
- Pinheader UPDI 1x03

I noticed that there is no voltage regulator in the schematic, Ben told me this is because the ATtiny runs on 5v. (The SAMD's run on 3.3v)

##### Schematics

I placed all the components in Kicad.

![hello](/assets/images/2022-05-23-hello-world/hello02.png)

Then the difficult part begun. I connected the pins i knew how to connect. 

![hello](/assets/images/2022-05-23-hello-world/hello03.png)

For the rest of the connections went to [Erwin's site](https://fabacademy.org/2021/labs/waag/students/kooi-erwin/report/week_06/) and looked at his schematic:

![hello](/assets/images/2022-05-23-hello-world/hello04.png)

The following questions arose:

- Why is there a resistor connected to 5v and pin 5 before the phototransistor?

- How do i know which pins from the µC to connect to my components?

##### Why is there a resistor?

Since the photoresistor is operating like a switch we need to use a pull up or a pull down resistor. 

As a comment in [this example](https://forum.arduino.cc/t/why-do-i-need-a-pull-down-resistor-in-the-button-example/364688) explains: 

"If there were no link between pin and 0V (GND here), the input would be floating when button is not pressed, because of the very high input impedance. The resistor gives this link needed to make sure the input is at 0V in this case. A wire would not allow the pin to be HIGH when button pressed, as it would make a short between 5V and 0V"

##### But why isn't there a resistor connected to 5v and pin 7 before the switch??

But since we saw in the last answer that we need a pull up resistor before a button to prevent the input from floating, why isn't there one before the switch on pin 7?

Again Ben to the rescue.

Ben told me that you can program the internal pull up resistor inside the µC instead of using a separate resistor. I knew arduino could do this. 

![hello](/assets/images/2022-05-23-hello-world/hello07.jpg)

The µC (in this example for the arduino, but also the ATtiny i'm using) has a lot of peripherals we can't see. We can use the internal resistor as a pull up resistor by initializing the pin where the button is connected (lets say pin2) as pinMode(2,INPUT_PULLUP);

But why do we do this for the switch and not for the photoresistor? 

Our guess is that this is because the resistance of the internal resistor is not so high, and fixed. This is fine for the button, but with the photoresistor we might need a higher resistance, and we want to be able to change this value. 

##### How do i know which pins to connect

Data sheeeet!!! 

![hello](/assets/images/2022-05-23-hello-world/hello06.jpg)

![hello](/assets/images/2022-05-23-hello-world/hello05.jpg)

But what does it all mean?

Name | Function 
--- | --- 
VCC | Power input (ATtiny412 can operate 5v)
GND | Power output
OUT (0 OUT, 1 OUT) | Logic output pin
IN (0 IN0, 0 IN1) | Logic input pin
MOSI | SPI; Master-out-slave-in
MISO | SPI; Master-in-slave-out
SCK | SPI; Serial Clock, the line that carries the clock signal.
DAC | Digital to Analog converter (DAC), used for converting digital pulses to analog signals
TXD | Serial; Transmit data (connect to RXD of other device)
RXD | Serial; Receive data (connect to TXD of other device)
SDA | I2C; The line for the master and slave to send and receive data.
SCL | I2C; Serial Clock, the line that carries the clock signal.
UPDI | Pin for UPDI, interface for external programming and on-chip debugging of µC's
CLK I | Clock In
GPIO (PA1, PA2, etc) | General Purpose Input/Output. PA1 corresponds to Pin 2 when coding)
CCL | Configurable Custom Logic

Other important things:

Spec | ATtiny412
--- | ---
Flash memory | 4096 bytes

##### Back to Kicad

Now i should be able to connect the rest of my pins.

![hello](/assets/images/2022-05-23-hello-world/hello08.png)

I used labels for the Vcc and GND to make the schematic more tidy. 


