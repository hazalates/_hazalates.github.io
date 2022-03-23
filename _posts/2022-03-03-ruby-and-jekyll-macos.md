---
layout: post
title: "Getting started with Ruby & Jekyll on MacOS"
comments: true
description: "Ruby & Jekyll on MacOS"
keywords: "Ruby, Jekyll, SSG, MacOS, Apple Sillicon, GIT, GitHub"
---

Setting up Github
Make an account on Github

#### Installing Ruby & Jekyll

###### Installing Command line tools & Ruby 

###### Follow https://mac.install.guide/ruby/1.html through “Configure Git on Mac” - Skip generate SSH key steps

Check if MacOS is updated - update if needed

Creating ~/.zshrc in homefolder 

    touch .zshrc

Install Homebrew (it will install command line tools)

    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)”

Adding homebrew to $PATH

Copy commands provided by homebrew

Configure GIT 

    Git config —global user.name “Naam Naam”
    Git config —global user.email naam@mail.com

Set SDKROOT (see https://jekyllrb.com/docs/installation/macos/)

    export SDKROOT=$(xcrun --show-sdk-path)

###### Skip to Install Ruby with Homebrew (https://mac.install.guide/ruby/13.html)

###### Install Ruby

    Brew install ruby

Edit ~/.zshrc, set $PATH

    if [ -d "/opt/homebrew/opt/ruby/bin" ]; then
    	  export PATH=/opt/homebrew/opt/ruby/bin:$PATH
     export PATH=`gem environment gemdir`/bin:$PATH
    fi

#### Install Jekyll

###### Install RubyGems, GCC and Make

RubyGems

    gem update --system

GCC

    brew install gcc

Make

    brew install make

###### Install Jekyll and Bundler

    gem install --user-install bundler jekyll

Add Gem direction to $PATH

    echo 'export PATH="$HOME/.gem/ruby/X.X.0/bin:$PATH"' >> ~/.zshrc


#### Setting up Github pages 

###### See (https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll)

1. Make new repository on GitHub “hazalates.github.io"

1. Make parent folder Github site  ~/documents/Github_Site

1. Initialize empty Git repository in ~/documents/Github_Site/WaagDoc

1. Create Jekyll site in repository

1. Edit Gem file 

    1. added # to gem “jekyll”
    1. removed # from gem “github_pages” and set version to 225  
    
            Bundle install

1. Edit _config.yml 

1. Test site - error

**Error:**

    bundler: failed to load command: jekyll (/opt/homebrew/lib/ruby/gems/3.1.0/bin/jekyll)
    /opt/homebrew/lib/ruby/gems/3.1.0/gems/jekyll-3.9.0/lib/jekyll/commands/serve/servlet.rb:3:in `require': cannot load such file -- webrick (LoadError)
 
**Solution:**
    
    bundle add webrick

**What is it:**

Webrick is missing. Webrick is not included anymore in Ruby 3.0 - thus we need to add in mannualy 

1. Test site - site is running

1. Commit site

 **Error:**

    (use "git add <file>..." to include in what will be committed)
        ../.DS_Store

 **Solution:**

Delete current file 

    Git rm —-cached .DS_Store 

Add .DS_Store to .gitignore file

**What is it:**

.DS_Store is a file automaticaly created my Mac when opening a file in Finder. It stores information about thumbnails.

1. Add repository op github.com as a remote 

1. Push site to github

**Now we have a super simple site! - Next: Personalise site with theme!**

> **Frequently used command cheatsheet:**
>
> cd _change directory_
>
> mkdir _make directory_
>
> git init _creates repository_
>
> Jekyll new —skip-bundle . _creates new Jekyll site in repo_
>
> Bundle exec Jekyll serve _builds site and serves at http://localhost:4000/_
>
> -—livereload _Updates changes live when serving website_
>
> git add . _adds every change to commit_
>
> git commit -m ‘naam commit’ _commits changes_
>
> git remote ad https://github.com/hazalates/hazalates.github.io.git
>
> git push -u origin master _push changes_
>
> bundle update _update all gems_ 