---
layout: post
title:      "Script Splitter - A bit more in depth - Future Implementations"
date:       2018-01-08 06:16:32 +0000
permalink:  script_splitter_-_a_bit_more_in_depth_-_future_implementations
---


<iframe width="560" height="315" src="https://www.youtube.com/embed/WS0wsVj7NLg" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>


So my application isn't too complex but it's definitely solving a problem in my life. Or at least helping me deal with one. Creating captions or subtitles for my video projects. 

How you ask?! At its core, my application accepts a body of text, and splits it by word into an array. It then accepts a number, which will be provided by the user, to determine how many characters the captions being creating should have. The reason why we need the amount of characters is because you want your text to properly fit on the video frame. Specifically inside of the 'title-safe area' or just the 'safe area' which is something we don't have to worry too too much about now a days but it's still best practice. Back in the day due to the various tv sizes and now a days due to the various phone sizes. The safe area is an area in the frame where the editor would put information so it doesn't get cut off on any of these different video screens. 


![Title safe area](http://community.avid.com/cfs-filesystemfile.ashx/__key/CommunityServer.Components.PostAttachments/00.00.03.45.63/Title-Safe.jpg)

So you don't want text to go outside of the smallest rectangle. But yeah.
The body of text would be split by word. Then create an empty string. Given the number of characters the user specifies or the default number, I would push in words into that string. I would calculate the number of characters already inside of the string and add the number of characters in the word that's going to be pushed in. If the number is less than or equal to the specified character restraint, then the word would be pushed into the string. Once the added numbers reach over the limit, the string would be pushed into the array and a new string would be created. And just continue the loop until the array that was made from the body of text finishes. It could be a pretty fun hackerrank challenge. 

So aside from that I have the typical React/Redux set up. I have a store that holds the state of my whole application. A state for the form. And state for the scripts that come in from the API. At this moment, since my subtitles are just list items, I split the text on the client side. Soon so I can start creating my caption files for importing into video editing software, I will create a caption/subtitle model into the API and split the text on the server side. When I implement that, I will also give the text some more properties like 'completed' so you know if you have already implemented this caption into your video. Another property I want to implement is 'timecode' which will be very beneficial to the exporting of the caption file. Since the file will need to know the times each caption has to be placed. 

I'm thinking of ways to give the captions some kind of default timing but that will still require the user to give the application a runtime of the whole video. So let's say that the whole video is 5 minutes long and there are 200 captions. I was thinking of splitting the captions into equal amounts that would add up to the 5 minutes. 5 minutes are 300 seconds. 300 divided by 200 equals 1.5. So I would then create each caption to be 1 and a half seconds long. Which sounds simple but then you run into things like how many frames the video was shot in. Most common being 24 frames but you still want to be safe all around. But the more the user gives, the better the results. 

As for Reducers and Actions. I only created 3 reducers/action files. One for the script. One for the preview that you receive on the home page. And one for the form. The form has actions for resetting the form and saving the state of it. The preview renders the actual preview and also resets as well which accompanies the form being reset. And then the main script action/reducer does most of the heavy lifting. It retrieves all of the scripts from the API. It sends post requests to the API to save the scripts. It also deletes the scripts after pressing the delete button on the scripts show page.

I also added some minimal CSS to make the page not look too boring. But that's pretty much it. My final project. I'm pretty happy with the application since I've been dying to build something that actually solves a real world problem and I'm really excited to continue working on this project way after graduating. I feel it can be really useful to people, even in its current state. Very niche, but the niche is right up my ally.
 


