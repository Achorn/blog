---
layout: post
title: Transitions
---

The curtains of the film and game industries.

![_config.yml]({{ site.baseurl }}/images/posts/curtain.png)

## Background

Sometimes, learning the etymology of something helps you get a better scope of what that something is and isn't… Want to learn about databases? Learn the history of book-keeping and how people kept physical inventories on paper. with transitions, just picture a videogame as a play. When the curtains are down, everyone and everything is being put in their place. Once the curtains are lifted, the play begins. Scene over? Bring the curtains back down for setting up the next scene. Rinse and repeat.

I feel like working on transitions is a finer detail feature and there are other broad stroke tasks I should be working on, but something called to me when I was sipping my morning coffee and I came up with a pretty cool solution for how to handle transitions in my game (or engine??). It's starting to feel like I'm building a car and eventually can replace some parts and the exterior for another type of car.. which feels great.

## The Idea

![_config.yml]({{ site.baseurl }}/images/posts/transition-class.png)

Here is a quick SketchUp of what came to me this morning. There might me others like it.. there might even be identical solutions. There are probably better ones out there. But this on is mine and I am proud of it.

Basically, I created a transition class, which can be plugged into my main game class. Then, I just let the game states call the transition class.

- what transition I want going in
- what action I want to take (change state)
- what transition I want going out

There are other bigger problems (features) I need to work out like quaternion values for better rotations of ships, cut scenes, and dialog. But maybe this is what I'm supposed to be working on right now. They’re all important in the grand scheme of things no?

Lastly.. one thing I want to handle is controlling user inputs during transitions. I dont want a user pushing something and then an event is triggered while the theoretical curtains are down. Im going to be adding a user input active Boolean into my user input class to let the transition state turn on and off the user inputs when the transition starts and ends. How fun.

## Part 2. Actually implementing the transitions.

Now that I think about it, implementing smaller parts of the game might make it easier to implement harder parts of the game.. this is the way. Let's get stronger.
