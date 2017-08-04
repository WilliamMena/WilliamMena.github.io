---
layout: post
title:  "Javascript added to roommate_assistant. My rails final project."
date:   2017-08-04 01:26:18 -0400
---


I have to admit. Doing this project definitely gave me a better understanding of JavaScript. I went into it thinking I would get through it pretty quick but it took me longer than expected. 

`<warning>This post is more of me talking about my grievances while doing the project and learning some stuff along the way..</warning>`

The main problem I had was working with document.ready. I always had the idea that document.ready would always start or run when a page is loaded. Either when first entering the website or clicking a link to navigate elsewhere. Which is true. Depending on your environment. This is when I discovered something in rails that was never covered before in our lectures. Basic info but nice to know. So rails, whenever you auto-generate a project, (rails generate scaffold or what ever you actually use) it automatically inserts a line of code into your header. 

`<%= javascript_include_tag 'application', 'data-turbolinks-track' => true %>`

Hone onto the data-turbolinks-track. What this does is it makes each page we’re navigating to, much faster. The way it does it, or the simplified version that I understand, is that it changes what we view in the DOM instead of giving it a full page load. It still calls the next url and it changes our url in our window, but it changes our DOM html. If you've reached this part of the curriculum then you've encountered AJAX already. Rails seems to use something just like this when the line in the header is present. Meaning that document.ready will always run when the whole page is loaded. But since the DOM is just being adjusted, the ‘document’ isn't technically reloading again. It's just being modified each time you navigate through a page. Which is why document.ready will only run once. Before knowing this, it caused a bunch of my buttons and other event listeners to not work when moving to different views due to the events being called on the first initial page, where the items it's supposed to be called on don't exist. Then the DOM changes when I change views, and my objects that I want to have these events attached to exist, but since I ran my events in document.ready and it popped when it first loaded, they won't get rerun or attached to the buttons I would like to. It's just a problem I didn't really have a solution too until a good amount of experimentation. A line in our header wasn't a place I thought to check to fix my JavaScript events.

One other grievance I had while doing this project is how handlebars and the chrome terminal don’t really work together. At least in my situation I realized in the terminal, if we go through the handlebars procedure, getting the template, compiling it, registering partials if necessary. If we go through the process, save a template with data and then but a debugger right after, the variable with the saved template after data has been fed to it, won’t really work. At least in my experience, it didn’t work all that well. And as a strong lover of binding.pry back in ruby, I’m a big fan of calling and running things in debugger to see what exact values I will be getting for each function or variable, before even letting my app fully run. After even more experimentation, I eventually just let my code run and push these templates into the DOM and it would work fine. But before this moment, in my stage of confusion as to why it would append the template with certain data undefined, I would try and call the data or even just the return variable in debugger. Because you are currently in debugger (and in my example, retrieving the template and compiling it outside of the current scope), I receive errors saying it doesn’t understand what object I am inserting or calling with my template. When the app freezes to work with debugger, it somehow understands the templates less. But if you retrieve/compile/runTemplate in the terminal, you will see a properly filled in template with your new data. Moral of the half story, when working with handlebars, don’t solely rely on debugger to call functions and see what will be retrieved. Sometimes, even if the code is buggy, pretty badly written, sometimes even if you’re not sure what will happen, just let it run.

I see myself using AJAX and Javascript a lot more on my projects. Now with the knowledge I’ve gained from this, I’m less intimidated by this magical language. If I didn’t need to get through the curriculum, I already see even more fixes to my project, like making ‘live’ edit forms. So once you click edit on, les say a chore, instead of taking to a new page, we can replace the location of the test with an input box for the new one, all without loading a new page. This and more things come to mind.

But for an in depth look at my project, here is the github URL
[GITHUB - roommate_assistant](https://github.com/WilliamMena/roommate_assistant)


