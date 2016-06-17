---
layout: post
title:  "My first CLI Gem: food_ideas"
date:   2016-06-15 22:13:59 -0400
---

<iframe src="//giphy.com/embed/VeBeB9rR524RW" width="480" height="200" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

So this is my first ruby gem. The idea behind this gem is to have it help you decide on what you would like to eat. It will prompt you to enter up to 5 ingredients and it will spit back at you a list of recipes you may want to try out. More results will be presented on the list in the future. The idea came from me being undecisive of what I wanted to eat since I pretty much eat the same thing every day (quick food has been a routine for me lately). So I wanted something new but wasn't really craving anything, so I thought, this can be my first program. I've thought about making an application like this for a while now and this seemed like the perfect moment. 

## Walkthrough
To install this wonderful application, all you have to do is enter 'gem install food_ideas' into your terminal. 

When you run the gem, you will be greeted and given instructions on what to do to retreive the recipes. 

![intro](http://i.imgur.com/19VVRCG.png)

You then have the option either search recipes for up to 5 ingredients. You can enter one or 5. If you have less then 5 recipes, you have to type 'go'. But once you enter the 5 ingredients, the program will then search for the recipes. Once searching for recipes, you will be presented with "This may take a few seconds. Please wait.". Once inside you will be presented with a list of 5 recipes. If any peak your interest, you type in the number to the left of the recipe and you will be presented with more information about the recipe. You will be presented with a description of the meal and and the estimated amount of time it will take to cook the recipe. More information I'm considering implementing are serving sizes and in the future, calories per meal. If no description is present, you will be given a message saying there aren't any descriptions available at the moment.

![description](http://i.imgur.com/16VZjJp.png)

If you look at the last line in the picture above, you can see some more options to continue navigating through the gem. Once inside a recipe you can enter the lines 'list' to see the recipe list again or 'exit' to leave this set of recipes. If you type 'url', a direct link to the recipe will open in your browser!

If you enter 'exit' you will be asked if you would like to enter a new set of ingredients for more recipes. If you do, enter 'y'. If you want to continue to exit out of the gem you can type 'n'. 

![goodbye](http://i.imgur.com/K0TAr94.png)

This gem currently scrapes (using nokogiri and open-uri) the 'foodnetwork' to retrieve recipes. With plans on adding 'allrecipes' next and other worthy websites. Continued ideas below.


## My concerns, ideas and so on

So my initial idea was to have a food (scheduler?) planning application. In the long run, that's what it will be but for the most part it's a gem that gives recipes based on the ingredients of your choosing (or like I had in my mind, ingredients I have in my fridge). Overall still proud of what I’ve done even since I believed this project was well above my skill level. I had to relearn scraping for the Student Scraper final project but so far I’ve realized I’m pretty good with scraping so far. I’ve run into weirder websites that are a bit more complicated to scrape from but nothing too complex yet. 

This idea came to me randomly when I was at home undeceive of what I wanted to eat, even though I had a ton of ingredients at home. It’s an application that I thought was going to be pretty helpful to me and at least partially original. But when I was looking for websites to scrape I found out that the food network basically has their own version of this. You enter what ever ingredients at the top of the page and it displays recipes from their own database. So I implemented the same idea. I noticed that in their url when it searches for ingredients, the url has been pretty consistent. The beginning of the url starts with "http://www.foodnetwork.com/search/search-results.recipes.html?searchTerm=“ and it ends with "&form=global&_charset_=UTF-8”. Inside is just the words that you inserted into the search bar separated with a ‘+’. Which is pretty easy to do when you have an array of words (.join) or even a string of all the ingredients (.gsub). So making the urls were pretty easy instead of trying to figure out how to actually type inside the search bar through the CLI.

The two websites I had in mind to scrape were food network and allrecipes. Food network was easy to scrape. Not a complex structure but allrecipes seemed a bit more abstract in their html code. In foodnetwork, up to 10 recipes were displayed on each page. On allrecipes I couldn’t find a limit of recipes per page. But that wasn’t the problem. Foodnetwork had all the same structures for each recipe while allrecipe displayed them in a different manner. The site had 4 columns and in each of these 4 columns, the recipes were scattered around. Certain sections had more than others. The problem I thought of though was that since there was no defined amount of recipes per column, I wasn’t sure if my code would crash at one point because it doesn’t know when to stop looking or unsure of what would happen if no recipes are found. Honestly the structure just intimidated me since I've never seen anything like it. After the ton of scraping I did on foodnetwork, looking through the HTML of allrecipes became a lot less intimidating and I do plan on incorporating it into the code and scraping from two sites. Now I just have to decide how I'll make them run together.

Other features I would like to implement is the original idea of a food scheduler depending on calorie count but foodnetwork doesn’t include calories per meal so might have to scrape different sites and use the one’s that do implement it. Or depending on how bad I want to add the feature, I can probably scrape each recipe’s ingredients, convert the number into an integer and have the name search into a website that has single item calorie counts. But it might be complicated due to in each ingredient it probably mentions something along the lines of “10 diced carrots” which would probably make it harder to search for specific ingredients. The search might confuse diced as an ingredient and carrots as a form of cutting.

So for a very basic food scheduler, I’m thinking I can implement something that picks 3 different recipes for breakfast, lunch and dinner per day. Or 15 for 5 days and display it for the current week or a specified week. Making sure each recipe is different. Since results will probably repeat once the person has already eaten that meal, I might implement a giant array that contains all the eaten meals for that specific person and make sure it doesn't return any recipe that is already contained in that array. (Which means I’ll need to implement profiles per user and find out how to save that information locally.)

