---
layout: post
title:  "Oh man has it been a while... Sinatra Assessment"
date:   2016-11-03 23:39:08 -0400
---

###### draft


Hey Guys!


![several_months_later](https://littlemisskeri.files.wordpress.com/2015/06/several_monthes_later-_.png)


OK I'm Back! [Warning: Towards the end I use the word Follow a lot, may get confusing. 'follow'.count = 83]

Well it's been months since my last blog post. A lot has changed in my life since then. My heads a lot clearer and I'm getting back into rhythm. But you're here for my Sinatra Project. It was was definitely a fun project, met my requirements and then implemented a feature that I think is really cool but took me a while to even grasp the concept. I'll share with you guys my findings and maybe you'll understand it much better than I can so you can implement it into your next project. But if you must know what it is, it's a follow feature. A way to "follow" someone like twitter or a facebook "friend" type of connection. But we'll get to that later.

# What is my app and what does it do?!
WELL... For my Sinatra Assessment project I decided to make another recipe related app (It's my last one, I promise). Except this one I believe is much cooler. I called it has_many_recipes and it's an application where you can create and submit recipes for everyone to see. So that mean's you can also view other peoples recipes who have logged in and created recipes them selves. All the recipes are categorized by a 'category' tag, which basically defines if the recipe is for meant to be eaten for breakfast, lunch, midnight snack, desert or what ever else you can think of.

![home page](http://i.imgur.com/z0ISvH9.jpg)


The app has features for users who are logged in and also for those logged off. So for both type of users you can view all the recipe categories, a seperate list with all the recipes created and also a list for all the users currently signed up. The users who are logged on have a couple more features but lets get a little more into the logged off features.

### /categories
Here is where you can view all the recipes under their specified category. Currently I have every recipe being displayed next to the category name. All the recipes names are links to their specific page and each category link will take you to a page displaying all the recipies for that specific category. 

But as the site grows, I'm going to implement in the categories page that only a specific number of recipe names will be displayed so the categories page doesn't get too overcrowded. That leads to the user having to select the specific category for more recipes to choose from. 

### /recipes
Well this is just a list of all the recipes that have been created so far. It felt pretty nessesary when I was building it so I'm keeping it. I think it will be more significant when I add the feature to limit the number of recipes on the categories page still leaving it here.

#### A Recipe View
So the recipe will show the Recipe name, the person who created the recipe. Serving size which is currently defined as a string (used to be an integer) so you can keep the number for your recipe or you can add the string of '2 small children' or '3 football players'.

Cook time is also a string so you won't be limited to a minute or hour parameter. There is also an ingredients section which will display all of the current recipes ingredients and then a directions section showing you the direcitions which we can all guess what goes in there.

### /users
list of all the current user's registered to the site with links to their specific profile.

#### User Profile
Here is a page dedicated to one of the great people who decided to help me embark in this journey or creating has_many_recipes. My good friend Food Network Scrapert's profile page. Here you can see that this page has a bio section, if the user decides to fill it in. The purpose I see for the bio is describing the person and probably what type of food the specific user likes to make, if there is a certain style that the person follows when cooking. Here you can also see all the recipes the user created with a small preview of the recipe. The preview shows the cook time for the meal and a preview of the ingredients used. For the full recipe, you can click on the recipe's title. 

# 'Logged on' features
Alright. Now that we got past the main features of the page we can have a look at the features we get when we sign up. 
<#-- Picture to 'test' homepage -->
Here you should notice 4 things aside from the simple layout. 

### Random Recipe
You can probably guess by the header but what this feature does is that as soon as you log in, it gives you a random recipe from the master list in our app. The purpose of this was to give you something new to try if you're ever feeling adventurous in the food department. 

### Follow List & Your Feed
Below your random recipe there is a section dedicated to follow list. As a new user, what should be displayed is a message along the lines of 'you aren't following anyone' and 'no one is following you'. Your feed should be empty as well because you aren't following anyone. But we'll get to the follow section very soon, I promise. Once I start explaining the specifics, it might get very lengthy.

### Menu
Now that you're logged in, you get a quick drop down menu. Here you will be able to access your personal (1) profile page. When signing up you are given an option to fill in bio data. Once you view your personal profile page, you will be given the option to edit this bio to your liking. Another item from the dropdown menu is your (2) Follower list. Here you can view all the users you are following and all the users following you. The menu also gives you an option create a (3) new recipe. It takes you to a form where you can fill in all the data required and give the recipe a category for it to be listed under. If the category you want to use isn't listed, you can create one directly in the form. The drop down meny also lets you (4) log out of your account. 

# Follow or the art of Following
<iframe src="//giphy.com/embed/CkqpoOOS0BCQU?html5=true" width="480" height="201" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

OR

<iframe src="//giphy.com/embed/n4oKYFlAcv2AU?html5=true" width="480" height="269" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>


I know, I know. Finally. We're here. Here it is. The moment we've all been waiting for. Please be like Starlord and not Michael Scott. I hope this is interesting to look through and I'm not sure if this is covered later on in the curriculum so I'm sorry if I butcher this horribly. 

So now that we are logged in, we have access to a follow feature. The way we can follow someone is through their profile. Now that you are logged in, you can see a follow button. Once you click this button you will receive a notification saying you're following this user. For the sake of this excercise I'm going to follow 3 users. Now when we go back to our home page a couple things change.

### Feed & Follow List

We now have content in our feed :D . The Way I set up our feed is that the application will display all the users you follow alongside of the last recipe they created for the website. The recipe will be a preview, similar to the one of 'random recipe' but more characters will be visible. Now you might also notice that the text under follow list has changed. It now mentions how many followers you have or how many people are following you. If you click the follow list title, it will take you to the follow list page.

### Making followers actually work

So the create a friend section. While I was creating and following resources to create this I was pretty confused and could only partially explain what I was doing. I think the reason for my confusion, at least part of the reason, was because of my naming conventions. They were really similar when I started to create the followers section but I decided to keep the name shorter for my model class names and other names used here. So as we may know at this point in time in the curriculum, when we want to associate certain models to another, we need to create a 'joins table'. So that should be a given at this point. I wanted to make the ‘followers' association, and then the ‘following' association after. So what I mean by this is create the part of the relationship where you can see a person's ‘followers' and then afterwards be able to use the same table to see who the user is ‘following'

When starting to make the followers relationship, the first couple of associations I made in my user class we’re 

``` 
has_many :followers_association, :class_name => "Follower"
has_many :followers, :through => :followers_association, :source => :follower 
```

:followers_associations would be each instance of the user/follower relationship or each column in that relationship’s table. In the couple example’s I’ve seen for this type of association, there wasn’t a need for defining :class_name early on, but for my code to work we needed to define it. When looking through the activerecord guides, the definition for :class_name is this, 

> If the name of the other model cannot be derived from the association name, you can use the :class_name option to supply the model name. 

Which is also similar to the definition for :source, which is something I defined as well at the end of the 2nd line. When ever the model name cannot be auto detected from the association name, we have to define it. I can’t tell you how activerecord can auto detect the names, but I can tell you that it didn’t work in my code so I had to define :class_name. In the examples I’ve seen, the association has the same name as the class you want to define, so if that's the case you probably wouldn't need to define :class_name. 

With my code at that point in time, it seemed like a good idea to just call my relationship, followers_association as opposed to what my first idea was, ‘followers’ which would have probably lead to even more confusing. When it comes to defining :source, it seems it’s more of a safety precaution to always define it.

But back to going through the associations. We can see on the 2nd line, we defined has_many :followers, through our followers_association with a source of the follower model. And with these 2 first lines we pretty much have one side of the follower relationship working. What would need to be done next is create methods that would create the ‘follower’ relationship so you don't have to hardcode it each time. Something similar to what I did below. When we do 'any_user.followers', we get back an array. If the User has followers, then each Follower will appear in this array. If we create a new User or the user doesn't have any followers, 'any_user.followers' will come back empty. This next section was made more so for experimentation in terminal, not for final usage in the app.

```
current_profile_being_viewed = p
current_user = u
p.followers << u
p.save
```
So once we get this code to save, we'll be defining the user_id section of a Follower instance.
```
#<Follower:0x007f8859a23378 id: 1, user_id: 1, follower_id: nil>

```

This next code will define the follower_id which will complete the follower association.

```
  has_many :following_association, :class_name => "Follower", :foreign_key => "follower_id"
  has_many :following, :through => :following_association, :source => :user
```
Very similar to the first 2 lines but some differences. I personally defined the association as following_association to keep it similar to the has_many :following that I want to use later on in my app but in the resources which I'll link below, for the inverse association (or the 2nd set of lines) he defined the association by using the same name as previously used but inserted the string 'inverse' in front of it. Example would be `:inverse_followers_association`. 

We still have to define the class_name as ‘Follower’ since this new association isn’t auto-detectable. We then we have to define the :foreign_key we want to write to, or read when calling. We then next define has_many :followers, through the previous association and define the source as a :user. I’ll be completely honest here, I’m not entirely sure why we define this one as :user while the 'followers' association is defined as the :follower class, I just know it works so I’ll pass that along.

I do think though, it’s a way to ‘trick’ the association because if you can recall, in the Follower class, we mention that the Follower class belongs_to a :user and a :follower, but the follower line has a :class_name of “User”. So it belongs to a follower that follows the User Model. So I call or believe this may be a trick since we’re associating a model to the same model, but under an alias. 

But this is pretty much all you need to make the following association work. You just have to figure out your own way to associate each user. I like to use the shovel method and then save afterwards but there are a number of ways to build these associations. 

Something I would definitely change if I was earlier on would be the naming conventions I used. Instead of Follower class, I believe I should have called it ‘Relationship’ so there would be more separation from has_many :followers and has_many :following. With the added separation I think it would have been easier for me to comprehend the associations and relationships I was defining much earlier on. Less confusion with a new feature, the better.



### Resources
[RailsCast: 163-self-referential-association](http://railscasts.com/episodes/163-self-referential-association)
[My Repo](https://github.com/WilliamMena/sinatra-assessment-has_many_recipes)

