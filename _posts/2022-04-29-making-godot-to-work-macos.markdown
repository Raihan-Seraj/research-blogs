---
layout: post
title: A never ending journey of getting Godot to work with MacOS
date: 2022-04-29 2:15:20 +0500
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: godot-macos.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Troubleshooting, Godot, Game Engine]
usemathjax: true
---


## Prologue
Recently I had the chance to work with Godot, an opensource game engine platform. The platform is used to create a simulator where I was required to make some minor changes to make it suitable
for the type of problems I am considering. Having some prior experience working with Unity, I thought 
making minor changes in the project with Godot will be quite straightforward. 


## The primary issue

I followed the basic first step of trying to open the project file using Godot v-3.3.2. There are two ways to import existing project in  Godot 
1. By uploading the zip file of the project in the import manager.
2. By pointing the import manager to the project.godot file.

Both processes of automatic import failed from my case. Starting from v-3.0, godot shifted towards a new file system architecture which apparently should have made the import process easy. However this was not the case in practice. certain files of the projects were imported and the rest of them were blank. I managed to figure out a naive way to create a new project and then copy and paste the resources and files from the existing ones. This somehow worked for me, although compilation of the project and exporting the HTML5 file resulted is a blank screen. I was running MacOS 12.3.1 Monterey, and upon searching the web whether such issues with os versions exists, I ran out of luck. I had the impression of doing something terribly incorrect since it appears that I am the only one with this particular issue. The project handed over to me was initially compiled using a windows machine. I was adamant that it was not an OS issue since Godot documentation does not specifically mention that the project import and compilation are OS dependant. 

## Towards reaching a solution
After spending weeks to find the root of the problem, I finally decided to download and install each of the different versions of Godot and try to import and compile the project. I realized that starting from Godot v-3.1, the import issue seemed to be fixed for MacOS, which again resurfaced in later versions 3.3.2. This was quite surprising. Starting from v-4.0, the automatic import issue seemed to be fixed but starting from v-4.0, Godot discontinued the export of the project as an HTML5, which was necessary for the type of system I was working on. Finally I could manage to find a single version Godot v-3.1.2 which seemed to 
work. 

## Summary 
If you are using MacOS and want to work on an existing project in Godot you can consider the following:

* Godot 3.1.2 allows you to export your project as HTML5. It also fixes the issue with import manager. 
* Godot v-4.0 and above does not have HTML5 support, but fixes the issue with project import manager.
* All of these seem to work with MacOS 12.3.1 (Monterey), however I have not tested them with other versions of MacOS.  



<!-- Suppose we are optimizing a supervised training algorithm where we have access to the true label of the dataset. Let $$y^{(i)}$$ be the true label for the $$i^{th}$$ training example. For simplicity let us assume that the data set have a two dimensional feature space represented by $$x_1, x_2$$ where $$(x_1, x_2)\in \mathbb{R}$$. The learning algorithm is associated with a hypothesis where we assume the nature of the underlying function that represents the true value. For instance if we consider the hypothesis to be linear then we assume that the estimate of the true label $$y_{pred}$$ is some linear function of the features $$x_1,x_2$$. given by  $$\begin{equation}y_{pred}^{(i)}=\theta_1^(i)x_1+\theta_2x_2+\theta_3\end{equation}$$  -->

<!-- ![I and My friends]({{site.baseurl}}/assets/img/we-in-rest.jpg) -->

