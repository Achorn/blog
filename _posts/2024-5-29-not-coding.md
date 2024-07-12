---
layout: post
title: Coding Isn't the Only Type of Work
---

Entry 03 : Sun may 29 2024

I easily forget that just because im not coding, doesnt mean I’m not working. I took some time away from three js to research more game dev. I will be using threejs to build my name but it is not a game in itself. It is a way for me to create and manipulate 3d models. The game engine state, and patters are things i will be bringing to the table.

I read the skope of game development from distribution, licensing monetization and promotion on the Mdn docs. There are also 2d tutorials and maybe they will give more insight. My next step is to refactor my code and start separating code into folders and files.

Current structure idea

game
World
Objects
Space ships
Stars
Boarder
Camera
User input
Game State? Idk what im doing

This is my idea ad i know its not perfect and there are definitely improvements that i cant see that im going to trust future josh to research and implement. But this is a good start. I can imagine my threejs lesson will have some insight but also i can learn from other tutorials. A points system could be implemented the same way in 3d the way it would be in 2d.

So yes. Some organization is better than none but also better than over-organization. Why do i have so much anxiety breaking things apart. I feel like im going to put them in the ‘wrong’. place.

And also putting them in their own files could lead to creating code thats bigger than it should. Like keeping it in the same file will force me to try to keep it small. Why do i think this way? Do other people think like this?

Things that come To mind but dont know the first place to start
Game specific patters that would be helpful for my game.

Im at my coffee shop gig right now and It’s slow so im just rambling.

What I normally do in times like this when my head is together and im realize im not too good for a quick googl - google game dev patterns

Talk to you late
——— entry 3 part 2 ———

I started refactoring and moving things into their own classes. Damn i remember why I hated the thought of this . Because i hate the act of it. Pulling things apart is a nasty affair and its hard to move through the refactoring and placing classes that depend on each other. There’s not much testing right now because it either works or it doesnt work. So im about more than halfway

Ive been following the structure of threejs journey lesson 26 structure for bigger projects. And while it isnt game focused, it has some good architecture and patterns.

We have a singleton game where all other classes that call the game get access to the one game. Because when a class is created, it checks to see if one already exists. And if it does then it just becomes a reference to the original. This is working by allowing all the children of game class call a game class of their own which in turn creates a reference to the parent game class

If this isnt making sense to you. Don’t worry, it took me years to figure out why this pattern matters until i saw it used for something i care about. Like a game class and all its children having easy access to it. There’s only one game after all.

We have a notify-er class which i just picked strait from my threejs tutor. This is used by the timer and maybe also the debugger for when they are updated they can let everyone whos listening to them updated things related to time and bugging.

We also have a utility folder which holds tool classes like time, debug, and something else.

We have a wold folder which holds all the environments and objects we will be seeing on the canvas.

And i stopped before i could add the first thing i would see to check if everything’s working or not. I added all the utils, the game class, the world class. We will see tomorrow if i am able to see some stars in the sky.

Also dude add the orbit controls to the camera while youre debugging. It will make it easier.

So thats day three. Im in the dark and moving my entire house into a bigger shell to breath. And we will carefully move everything back.

Questions

Best way to have camera interact and attach to player ship. Does game handle that? Does world handle that? Do i need a separate controller for linking camera and ship?

Do i have an options of available ships to follow to move the camera around??? Variable. Selected camera object. Array of available camera objects

Anyway. I made refactored progress and had a sense of when to take a break and not get overloaded. Didnt chase the dragon of ‘its almost done i can sense the horizon is close’ mentality.

What to do after the refactor….. idk.

Add some controls?
Yeah… add some controls
In its own class! Maybe mobile first then controller….

I refactored it and everything is in its place.. for now.. feels good to have a codebase with more space. Still have the worry of not knowing where everything is but i would still have that in one file with thousands of lines….

Im also reading a book about video game architecture and patters to avoid any big pitfalls in the near future. Just keep moving forward. Im scared and thats ok.
