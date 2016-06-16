---
layout: post
title:  "My many phases."
date:   2016-06-16 00:33:37 +0000
---

```
class Blog
require 'nokogiri'
require 'open-uri'

  def greeting
    "Hey, my name is William Mena and welcome to my blog!"
    "Warning: My blogs usually turn into a rant."
    ask_topic
    rant
  end

  def ask_topic
    #topics will vary. Enter more questions.
    puts "Why did you join software development?"
  end

  def rant
    doc = Nokogiri::HTML(open(my_blog))
    p = Post.new
    p.title = doc.css('h1')
    p.content = doc.css('div.entry p').text
    puts p.title
    puts p.contents
  end


end

class Post

attr_accessor :title, :content

@@all = []

  def initialize
    @@all << self
  end

end

```

Why software development? Well through my many phases, the art of code never failed to intruige me. In the beginning of my college career, still in my high school mentality, my first major was computer engineering. Something I entered while still unsure of what I wanted to do with my life but following what my parents thought was the best route for me. Turns out in the classes I was really interested in, I did really well. The rest, well I had to switch majors and stop wasting money and time dropping out of classes. The programming classes and building small electronics are what I remember the most about my experience and I remembered truley enjoying my time there. But due to my streak of bad grades in other classes I had to search around for another major. I dabbled around with certain majors but ended up in 'Entertainment Technology' which would end up (hopefully) turning into a film program. Since I've been making videos with my friends since around 14, it took me until my 2nd-3rd year in college to realize, wait, I'm actually good at editing video's and maybe I can turn this into a career. Enough time in entertainment technology has shown me that what my major was preparing me for was work in the theatre world which I had no interest in doing. It would take too long to turn into a film program. All they had was one video editing class, a bunch of electives that I could have taken from Graphic Design, Engineering or Art majors. So with my interest in digital creation I ended up taking some Graphic Design classes that peaked my interest and ended up doing really well and loved the experience. I would be a much different person without that one graphic design class. Nonethe less with my lack of video classes I transfered all the way up to Buffalo University to persue an out of the city experience and a Film Major. But what I didn't realize was that the film department up there was very experimental and artsy. It has it's pros and cons. One of my favorite classes up there was experimental technology. The first 3rd of that class was wearable technology. That's when we started messing around with lillypad arduinos and my love for programming came all the way back. I forgot how much I loved technology, programming, building hardware. My final project for that section was a [hat with RGB LED's](https://youtu.be/VgWgMEP4_0o) and I coded it to present a certain pattern and future plan was to connect it to a button to cycle through a desired pattern out of my array of patterns. It really just opened my eyes again and ever since then I've been trying to persue more knowledge of programming even though I wanted to graduate with film. I wanted to find some way to make my love for film/motion graphics and programming all work in some type of way or at least still work (in some part) in all those fields.

What I learned about myself from school was that I need to be hands on though. I need to create something and see what I'm creating. I did great and really commited to my projects when I was hands on and just working on my stuff. When we tried to find the theory behind certain things, I tended to doze off and not fully commit. (I know, I'm horrible) I just felt like even though I understood all this theory, it never really affected my work significantly. It made me think a little more about viewing other projects but never really about my work. But either way I thought it was a lot of fluff withut much practice. What I like about bootcamps is that there can be some theory but you will begin practicing your theories right then and there or you can see how these formulas relate to code. Nothing like in my film theory where I have 4 months of reading a book to help me determine if the curtain is blue because the character feels sad and torn.

I've been told I love coding due to my love for puzzles. Usually you can catch me with this mornings newspaper trying to solve that days (or yestursdays :( )Sudoku puzzle frustrated because I can't get that one number which will basically line up the rest of the puzzle. I love all types of puzzles or challenges. That sense of accomplishment/satisfaction that comes with hours of dedication to complete this puzzle is something I love. So far I've had certain codes crash on me repetively but I've enjoyed just roughing it out, putting together all these bits and pieces of information I've learned to accomplish all these code. I'm not sure if it's the learning style of a bootcamp that has really convinced me I love code, sometimes even more than video editing (but lets wait until I start working to see if that remains true lol), the constant amount of information we're receiving and utilizing quickly, or if it's just being able to learn, create and take part in a world that I never thought I would do well in. I'm really just loving my experience and I truly think this is where I was meant to be. 

**//** Learn. Love. Code.

<iframe src="//giphy.com/embed/1C8bHHJturSx2" width="480" height="259" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
<iframe src="//giphy.com/embed/eCqFYAVjjDksg" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
