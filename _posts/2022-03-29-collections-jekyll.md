---
layout: post
title: "Organizing and adding pages using collections in Jekyll"
comments: true
description: "Description"
keywords: "Jekyll, collections, site"
---

I want to improve my site by adding two separate pages. One of the pages looks similar to my index page, but contains posts of projects i want to do in the future and other inspiration. The second page orders all my posts based on categories. 

I studied my current repository and looked at how my index page behaved. I added a folder called "_future_projects" and made a test-post. 

![Screenshot01](/assets/images/2022-03-29-collections-jekyll/screenshot01.jpg)

Then i made a future.html file in my root and copied the content of index.html. I replaced the "post" with "future_projects" 

![Screenshot02](/assets/images/2022-03-29-collections-jekyll/screenshot02.jpg)

This didn't do much. Since this sentence is not HTML, but probably Markdown or Jekyll code, i googled "how to create similar folder as _posts in Jekyll site. [This stackoverflow](https://stackoverflow.com/questions/45260783/jekyll-create-another-folder-with-similar-functionality-of-posts) page referred me to [the Jekyll documentation page about Collections](https://jekyllrb.com/docs/collections/). 

I had to declare a collection in my _config.yml file called "future_projects". I wanted a listed view of the future projects pages, so i also had to put output: true

![Screenshot03](/assets/images/2022-03-29-collections-jekyll/screenshot03.png)

Now i could see a similar list as seen on my index page, but with pages saved in my _future_projects folder!