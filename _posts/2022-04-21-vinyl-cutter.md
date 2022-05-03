---
layout: post
title: "Vinyl Cutter"
comments: true
description: ""
keywords: ""
---

##### How to use the vinyl cutter

Ferah is showing me how to use the vinyl cutter. 

I want to make a label for my spicy kombucha. I found 2 very nice pepper SVG's [here](https://svgsilh.com/image/1990837.html). 

I downloaded the SVG's and put them on an USB. 

##### Opening the image with MODS

1. Turn on computer.

2. Put USB in computer.

3. Open terminal and navigate to the folder where the Mods script is located.

        cd mods

4. Type bash mods. Mods will open.

        bash mods

5. Right click programs - open program - cut to open the vinyl cutter environment.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl12.jpg)

6. Turn on vinyl cutter.

7. Select SVG file and open file.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl14.jpg)

8. Put threshold - somewhere between 0.1-0.9.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl15.jpg)

9. Edit size by changing units - the higher the unit, the smaller the size.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl22.jpg)

10. Press calculate.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl16.jpg)

##### Edit image in Inkscape

To make sure the image is set up correctly we can use Inkscape.

11. Open Inkscape and open file.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl11.jpg)

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl18.jpg)

To create a margin so the vinyl cutter has enough (but not too much) whitespace:

12. Go to document properties. Add 2 and press resize page (make sure you rotate if needed).

13. Lock margin.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl19.jpg)

Fill open spaces (not needed in my case):

14. Open Fill (CTRL+SHIFT+F).

15. Click on flat color.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl21.jpg)

16. Save file and open new file in Mods - After editing the image in Inkscape make sure to check all the settings in Mods (as noted above).

##### Time to start cutting

17. Pick a nice vinyl color and cut it a little bit bigger than the needed size

18. Make sure the vinyl fits between the white spaces on the cutter

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl23.jpg)

!! If its a normal sticker, keep the chosen side up! If its thermal, keep desired side down !!

19. Make sure the handle on the left backside of the cutter is down

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl24.jpg)

20. Place the sticker between the white spaces (from the back side, a little further than the wheels).

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl8.jpg)

21. Lift up handle to lock the vinyl.

22. Select sheet: choose piece and press enter.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl4.jpg)

23. Set origin by using the left and right arrow. (not possible in my case?)

###### Last things in Mods:

24. Set speed and force - speed 2, force 50 - force depends on the thickness of the material. 

25. Make sure origin matches with the origin set on the cutter.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl5.jpg)

25. Send file to cutter

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl6.jpg)

##### Errors and mistakes

!! It went completely wrong :) 

**Setting up the cutter:**

At fist i thought that the sheet setting on the vinylcutter should be set to roll. This had to be piece. Because this setting was wrong i could not move the origin on the cutter. 

**2nd problem:**

I wasn't able to resend the image to the cutter, because Mods said "waiting for file". I first had to press calculate again before i was able to resend the image. 

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl9.jpg)

**3rd problem:** 

I thought that i could use the side of the cutter to cut small pieces. This is not possible.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl8.jpg)

#### Thermo pressing

Next want to cut a design with the vinyl cutter and print it on a t-shirt. 

I first made a few sketches of what i wanted to cut. 

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl25.jpg)


Next i drew the image in Illustrator. I exported the file as a SVG file and loaded the file in Mods.

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl26.jpg)

**1st problem:**

Mods didn't recognized the SVG file. Michelle told me this had something to do with files that are exported from Illustrator and Mods not working together. 

We opened the file in Inkscape to export from there. Mods still didn't recognize the image. 

Searching through the Fabacademy page to find the solution on the page of someone who ran into the same problem, we discovered that Mods needed the width and height in the XML code of the SVG file, which illustrator doesn't include. 

        "Mods program needs specific metadata from your .svg file. When creating a .svg from Adobe Illustrator (2021), the metadata does not include 2 parameters that Mods needs to function correctly. Adding, for example, width="600px" height ="600px" to the XML metadata gives it the information that it needs to work."[1]

When opening the code of the SVG directly exported out of Illustrator, the code was not organized and difficult to read. When opening the image in Inkscape and then saving it, the code was readable and we could add the width and height to the code. 

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl29.jpg)

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl27.jpg)


**2nd problem:** 

After editing the code of the SVG, Mods still didn't recognize the image. Another search on the Fabacademy page learned me that Mods also doesn't like transparent backgrounds in the SVG. 

        "Time to export the svg files. So I used Inkscape to generate one for the traces and one for the outline. Initially I had some trouble loading it up in mods. Then I realized the svg needs to have a white (not transparent) background to allow the design to be inversed." [2]

I added a white background to all of the SVG files, after this Mods was able to load the image. 


[1] [Philip Hozier's page where we found the solution to the first problem](https://fabacademy.org/2021/labs/waag/students/philip-hozier/assignments/week3/)

[2] [Cathy Fang's page where we found the solution to the second problem](http://fab.cba.mit.edu/classes/863.21/CBA/people/catfang/hw/week4.html)

##### Heat pressing the image

After solving the conflict with mods i was able to print the image. I printed the image in 3 different parts, all with a different color. 

!! Important !! 

When using thermo vinyl put the roll upside down in the vinyl cutter.

Also, mirror the image before cutting. 

Farah profided me with the following instructions:

1. Turn on the heatpress.

2. Set the temperature to 311*F (the heatpress works with Fahrenheit instead of Celsius).

3. Put a sheet of baking parchment on the heatpress.

4. Put the t-shirt on top of the baking parchment.

5. Place the image on the t-shirt. Make sure the thermo vinyl around the image is peeled off so only the image and the plastic peel are left. Since i have 3 different parts i only place one of the parts on the t-shirt.

6. Put a sheet of baking parchment on the t-shirt (so the t-shirt has baking parchment on both sides).

7. Check if the heatpress is completely heated up to the right temperature. 

8. Set timer on 20 seconds

9. Press play on the timer and immediately press down the handle of the heatpress

10. When the timer beeps, lift handle and remove the heatpress.

11. Remove the peel from the t-shirt.

12. Repeat process with next part of the image. 

##### The result: 

![vinyl](/assets/images/2022-04-21-vinyl-cutter/vinyl28.jpg)
