---
layout: post
title: Gamepad API
---

Spent a lot of time learning about the JavaScript game pad API today.

![_config.yml]({{ site.baseurl }}/images/posts/gamepad/gamepad-drawing.png)
[a doodle i made to keep track of inputs]

Moments like these make me wonder why I decided to make a game from scratch instead of using a game engine. Oh well. I like making things hard on myself.

I was able to get the game pad working and plugged most of the buttons into my input controller class. And it was pretty cool getting my cube to move around with a game pad. An issue that I hit was when trying to cycle through my menu buttons. Because the game pad api acts differently then button event listeners, The menus are impossible to use unless youre trying to get to the buttons at the very top or bottom of the menu. Pressing the down button on a game pad is continuous not incremental.

This one was a bit difficult but mostly because my face was glued to the computer for quite a while, and I needed to remind myself to take breaks when dealing with bugs.

What did I gain?

A better understand of the types of controllers.
A better understand of the JavaScript gamepad API and how to implement it into my game engine.

Part 2

I feel better. This thing happens where I go in a cave and its dark and scary and I dont know if I'm going to get to the other side… and then I take a break and get through it… ugh… this can be exhausting sometimes but also rewarding. Why was the gamepad so worrisome for me. Very vulnerable. I think I was so excited about getting a game pad connected I felt worried about failing.. anyway.

After messing around and researching some more, I found a tutorial for making custom event listeners that make the gamepad act the same way as typical keyboard events. HOWEVER. When I upload it and tried it out on my iPad.. the gamepad doesnt work now.. oh well. Another bug for another day.
[.. insert link to website I used to update my gamepad inputs]

Part 3

Wow what a day.

Took some time to debug my game and added a consol log string to my screen so I can debug on the iPad to see why it wasnt working. (Sending basically one string that updates every frame that I can access anywhere in my code. (Ok actually I should make a debug class just for putting things on the screen!!! )

Here's what I found. Every frame, I use a snapshot of the previous gamepad state to check if a button has key down event (button press = true now and button press= false in prior state) or if the button has been released (button press = false now and button press= true in prior state). Because the class doesnt keep track of that itself, you need to make your own way of handling it

What's the issue? These Events weren’t triggering because the previous gamepad state was identical to the current state.

What I then figured out is on chrome the gamepad gives you a ‘snap shot’ the current state , so if I am using a snap shot of the current state, that means it is a picture of the state a moment in time it is requested. So i can compare future ‘snap shots' with the one I just took. this works just fine on my computer

However... Other browsers give you a ‘reference’ to the gamepad state. So no matter how many times I think im getting a snapshot im actually getting a reference (picture a live video feed instead of an image from the past) so whenever I say previous gamepad state = current gamepad state and set the current gamepad state to the gamepad state theyre all pointing to the same gamepad state!

This annoyed me but after working out a solution, the previous game state is now just a collection of copies of the gamepad states button indexes and pressed state. Which is a copy and comparable to future states.

Now I can play my game on my iPad with a controller :)

next steps?

my controls are pretty clunky and need to be updated. now that we have analog sticks that smoothly transition from 0 -> 1 instead of just an on off switch like a button, i can now implement smoth movement for my ship.
