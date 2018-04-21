---
date: "2018-04-16T21:26:01-05:00"
title: "Documentation"
authors: []
categories:
  - Dev
tags:
  - hugo
  - web
draft: true
---

This post contains documentation for the setup of this blog. Hopefully this site will be so stable that I'll totally forget how I set it up when I come back years from now to make a change...

## Setup the development environment
Create the directory structure.

    mkdir ~/Documents/Developer/mattkopecki.github.com
    cd ~/Documents/Developer/mattkopecki.github.com
    mkdir site

## Install Hugo
    brew install hugo
    hugo version

## Create the Github repository
I already had a github repo set up for a user/organization page.

This site is hosted in the repository named `mattkopecki.github.com` at the address https://github.com/mattkopecki/mattkopecki.github.com

You have to follow this repo scheme. Make it public, do not add a README file, a .gitignore or a license file. The `master` branch is the branch where generated pages are hosted, you don’t want any non mandatory files there.

## Initiate repository branches
Push the first commit on the `master` branch to create it. Generated pages will be pushed on this branch.

    cd site
    git init
    git remote add origin git@github.com:mattkopecki/mattkopecki.github.com.git
    git commit --allow-empty -m "Start the public branch"
    git push -u origin master

Create the `source` branch. Website source code will be pushed on this branch.
The `source` branch has to have a .gitignore file to avoid committing generated or temporary files. I used the online tool gitignore.io to generate a .gitignore file that ignores the proper files for OS X, my text editor, and Hugo in one curl command.

    git checkout --orphan source
    curl -L -s -o .gitignore https://www.gitignore.io/api/osx%2Chugo%2Csublimetext
    git add .gitignore
    git commit -m "added gitignore file"
    git push origin source

Verify that the .gitignore file generated at the previous step contains the line /public/. If the line does not exist add it and commit this change.

    cat .gitignore | grep public
    /public/

Use the git worktree feature to checkout the `master` branch to the ignored public sub-folder.
Why? By default, Hugo generates the site in the public folder. Having the `master` branch mapped to the public folder makes it possible to easily chain site generation and publication steps without moving around files.

    rm -rf public
    git worktree add -B master public origin/master

## Configure and generate the site
Create a new empty site tree.

    git checkout source
    ./hugo new site . --force
    git add config.toml archetypes/default.md
    git commit -m "Add fresh empty site"
    git push origin source

Add a Hugo theme. This site currently uses the minimo theme because it’s clean/minimalist, it supports categories/tags, renders correctly on desktop and mobile phones, and has built-in hooks to add custom Javascript and CSS.

    git submodule add https://github.com/MunifTanjim/minimo themes/minimo
    git submodule init
    git submodule update
    cp themes/minimo/exampleSite/config.toml .

Modify the config.toml configuration file of the site and commit the changes.

    git add config.toml .gitmodules themes/minimo 
    git commit -m "Add minimo theme"
    git push origin source

Test the site with the `-D` flag to see draft posts shown.

    hugo server -D

If you open your web browser and you visit the address http://localhost:1313/ the site should load even if there is no content for the moment.

## Github page custom domain
Create a file named CNAME that only contains the domain name. Add this file to the local copy of master in the static folder to have it deployed on each website generation.

    git add static/CNAME
    git commit -m "Add CNAME file in static folder"
    git push origin source

## Add the first post
Replace the Hugo default template by the theme default template and generate the first post skeleton.

    cp themes/minimo/archetypes/default.md archetypes/default.md
    hugo new post/first-post.md

Edit the content/post/first-post.md file. There is only the front matter right after the generation. Below the last line of the front matter, the one with the 3 dashes --- is where you add the content of the post. The format used is Markdown.

## Publish the site with the new post
To publish the site in one command, use the publish_to_master.sh script at the root of the repository.

Commit any changes and then run the script to publish the site.

    git add * 
    git commit -m "commit message"
    git push origin source
    ./publish_to_master.sh

