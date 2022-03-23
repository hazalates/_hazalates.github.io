---
layout: post
title: "Converting images with Imagemagick"
comments: true
description: "Description"
keywords: "converting, images, imagemagick, heic, jpg"
---

To post images in my blogposts for my documentation website i have to convert the images to an usable image extension. When importing photo's i took with my phone (Iphone 11), the original extension is *.HEIC. An usable extention would be jpeg. Ideally, i want the images to have a small file size. 

![Screenshot-01](/assets/images/2022-03-21-converting-images-with-Imagemagick/screenshot-01.png)

I could convert the images using Adobe Lightroom, but this would be a rather dramatic program/workflow for such a simple task. I can do better than this. I watched the lecture about Computer-aided Design, and came across Imagemagick. Imagemagick is a lightweight command line-based software for processing images. 

To install Imagemagick i opend terminal and ran the following commands. Note: I already have Homebrew installed from installing Jekyll and Ruby  

    brew install imagemagick
    brew install ghostscript

Using [this](https://opensource.com/article/17/8/imagemagick) tutorial i tried the display command.  

    cd ~/waag/site/thinkspace/assets/images/2022-03-07-kombucha
    display *.HEIC

It should give me the only GUI of Imagemagick, instead i got an error message.  

    display: delegate library support not built-in '' (X11) @ error/display.c/DisplayImageCommand/1898.

I googled the issue and a lot of steps need to be taken to resolve this issue. Because i want save time using Imagemagick instead of spending more time setting up Imagemagick i googled for another solution. 

Apparently since macOS Monterey‌ my mac has a build-in function for converting images.

![Screenshot-02](/assets/images/2022-03-21-converting-images-with-Imagemagick/screenshot-02.png)

![Screenshot-03](/assets/images/2022-03-21-converting-images-with-Imagemagick/screenshot-03.png)

Still wanting to give Imagemagick another shot i decided to not use the GUI, but use a command instead.  

    mogrify -format jpg *.HEIC

I compared the file sized of the files converted by Mac and Imagemagick. 

![Screenshot-04](/assets/images/2022-03-21-converting-images-with-Imagemagick/screenshot-04.png)

TO DO: Trying different file size compressions with Imagemagick, since the file sized are still very big. I do want to use Imagemagick since i have more controll over the outcome. 