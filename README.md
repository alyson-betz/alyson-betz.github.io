---
layout: default
title: ReadMe
permalink: /readme/
---

# How to host your Markdown resume on Github Pages using Jekyll.
--- 

## Purpose

This is a guide to hosting your own Markdown-formatted resume on GitHub pages using the static site generator Jekyll. This guide will help you learn how to make a Github account and host a site on Github pages, and how to use Jekyll to convert your Markdown resume into an html website, ready to be hosted. 

## Prerequisites
* You should have your resume formatted in Markdown before continuing on with this guide. [Here is a guide](https://daringfireball.net/projects/markdown/syntax) to Markdown syntax if you're a bit rusty on it. I use [Visual Studio Code](https://code.visualstudio.com/) to write in Markdown, but there are Markdown-specific editors including [Atom](https://atom.io/), [Typora](https://typora.io/), or [Sublime Text](https://www.sublimetext.com/) (which does more than just Markdown but is a great text editor). See [More Resources](#more-resources) below for further Markdown tutorials.
  * Markdown is a great tool because it enforces a style consistency, which is part of great documentation and resume writing.
* I'm using macOS, so that's what this guide will focus on. 

---

## Step 1: Generate a Github pages project
Git is a type of Distributed Version Control (DVC). It's one of the most used DVCs in the industry, and it's a great tool to [learn more about](#more-resources)!
1. Create a GitHub account [here](https://github.com/join).
   * If you already have one, skip this step.
2. Navigate to your Github homepage. 
3. Near the "Recent Repositories" section, there is a green button that says "New". Click this to create a new repository. 
   * ![Where to find the "New" button](/images/Screen%20Shot%202022-11-01%20at%206.56.27%20PM.png)
   * The name of your new repository _must_ be `username.github.io` where _username_ is your username on Github. 
     * For example, I would call my repo `alyson-betz.github.io`
   * Make sure this repo is public.
4. In the terminal, go to the folder where you want to store your project and clone the new repository you just made.
* To clone the new repo, run the following command:
  * `git clone https://github.com/username/username.github.io`
  * Again, replace _username_ with your Github username.
  * This puts a copy of the repo on your local computer.
5. Enter the project folder
   * `cd username.github.io`
   * It should be empty.
   * This is where you will store the site pages that are generated with Jekyll.
6. Make an initial commit to link this local folder with the repository on Github. 
* Run the following commands to do this:
  * `git commit -m "Initial commit"`
  * `git push -u origin main`

## Step 2: Generate a static site using Jekyll
Distributing a site is a more flexible way to distribute your resume to potential employers. It's much easier to fix something on your website (which you can do almost instantly) than to update a pdf and have to send it out again. Everyone who has a browser can easily see your resume with a static site, and you don't have to worry about conflicting file types.
### What is Jekyll?  
Jekyll is a static site generator. It takes Markdown files and converts them into html that can be hosted on a server. Jekyll also has themes that allow you to customize the html that is generated. You can make many different kinds of websites with Jekyll, not just resumes!
  1. Download and install Jekyll  
      * The Jekyll installation process (found [here](https://jekyllrb.com/docs/installation/macos/)) has all the steps to install Jekyll and its prerequisites (homebrew and ruby)
      * NOTE: if your Xcode is out of date, the ruby installation won't work. To update Xcode, just open it and it will auto-update. 
2.  Clone my custom Jekyll theme repository. Cloning a repository just means copying all the files from my repsitory on Github to your local computer.   
    * Run ``git clone https://github.com/alyson-betz/easy-resume.git`` to clone the repo.
    * This will create a folder called easy-resume in whatever folder you ran the ``git clone`` command.  
3. Navigate into the folder you just created. 
   * ``cd easy-resume``
   * You should see the following files in this folder: 
       * ![Files in the easy-resume folder after cloning](/images/Screen%20Shot%202022-11-01%20at%207.07.05%20PM.png)
4.  Run the following command to make sure everything is working,:
    * `bundle exec jekyll serve`
    * This command runs jekyll and builds your site with the Markdown files and themes in this folder. It also hosts the site locally.
    * You should see something like the following:
      * ![What you should see after running the jekyll command](/images/Screen%20Shot%202022-11-01%20at%207.08.58%20PM.png)
5. Go to your browser and type the following:
   * `http://localhost:4000/`
    * This is your site! It's being hosted on your local server, so no one else can see it. 
    * Now we'll look at customizing the site with your own resume instead of mine!  


## Step 3: Get your resume into the static site  
You should have your Markdown-formatted resume handy now. 
1. Delete the file 7786457-A2-resume-v1.md.  
   * In the easy-resume folder, there is a file called 7786457-A2-resume-v1.md. This is the sample resume that you saw on your local Jekyll site. 
   * Delete it, and we'll replace it with your resume. 

2. Copy your resume (MUST be a Markdown file) into the site folder.
3. Open your resume file that you just added. 
4. Add the following code to the top of your resume file (including the dashes):
```
--- 
layout: default
title: Resume  
permalink: /resume/  
---
```
   * This is Jekyll-specific code that sets some configuration variables for the page. To learn more about customizing Jekyll themes, go to the [Jekyll tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/). You don't need to learn this for this tutorial, but if you're interested in playing around with Jekyll more, I would highly recommend it. 
   * Your resume should look something like this: 
     * ![Your resume should have this header](/images/Screen%20Shot%202022-11-01%20at%207.10.10%20PM.png)

5. Rerun the following command to rebuild your site:   
   `bundle exec jekyll serve`
6. Navigate to `http://localhost:4000/` again
7. Your resume should appear!


## Step 4: Host the site created with Jekyll on Github Pages
1. Go back to the easy-resume folder with your Jekyll site inside. 
2. Copy the contents of the `_site` folder (within the easy-resume folder) into the `username.github.io` folder made in [Step 1](#step-1-generate-a-github-pages-project).
   * ![Copying the files](/images/copy.gif)
3. Push this to the repo:
   * To push to a repo, run the following commands
     * `git add .`
     * `git commit -m "Add whatever message you want here"`
     * `git push`
4. Your website should be hosted on Github now!
   * Go to `https://username.github.io`
     * Remember to subsititue _username_ with your own Github username


---
## More Resources

* [Great Markdown Tutorial](https://www.markdowntutorial.com/).  
* For more tips and tricks for writing documentation and hosting static sites, I would highly recommend reading Andrew Etter's book [Modern Technical Writing](https://www.amazon.com/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
* If you're interested in using git more, check out [this guide](https://www.hostinger.com/tutorials/basic-git-commands).


---
## Frequently Asked Questions (FAQ)
### **Why can't I just use Microsoft Word to make my resume?**  
* The default Word format (.docx) is a proprietary file format that is not easily opennable if you don't have Microsoft word. There are many Markdown file viewers, but Markdown is human readable on its own, so you don't necessarily need a Markdown reader.
* Markdown also enforces a easily readable style, which is important for a resume. Your resume should be scannable with the important parts standing out. Markdown makes this easy to do.

### **I pushed changes to Github, but the Github Pages site hasn't updated! What do I do? (This happened to me!)**
* Your browser cache might be out of date. Delete your recent history (including the cache) and go to your Github Pages website again. It should now be the updated website!  

---  
## Authors and Acknowledgements
 Thanks to my group members Vlad, Deep, and Nathan for proof-reading this assignment and giving me great feedback :)  
 I modified this theme myself from the default Jekyll theme, so thanks to me for authoring this!

