---
layout: index
title: Using timers and turn scripts
---

In a previous section, we made a bee fly into the kitchen after the player opened a window. We'll now make that bee a bit more annoying as it flies around the kitchen – every 20 seconds, it will buzz past the player.

To do this, we will use a timer. This timer will only be activated when the player opens the window in the kitchen. When the timer is activated, every 20 seconds it will print the message "The bee buzzes past you. Pesky bee". This message will only be printed if the player is in the kitchen.

First, let's set up the timer. After we have done this, we will add the script command to activate it at the right time.

Setting up the Timer
--------------------

In the Windows desktop version, add the timer by right-clicking the tree, or using the Add menu. In the web version, select "Timers" from the tree and click Add.

Enter the name "bee timer".

The timer editor will now be displayed. The Interval specifies how often the timer fires – in this case, we want it to fire every 20 seconds, so enter "20". Leave the box "Start timer when the game begins" unticked.

For the timer script, add a "print a message" command to display "The bee buzzes past you. Pesky bee."

![](TimerBee1.png "TimerBee1.png")

Activating the Timer
--------------------

Go back to the "window" object and edit the script that runs when the bee enters the kitchen - this will be the "Else" script if you've followed the tutorial so far. Add a command after the "move object" command - from the Timers category, choose "Enable timer". Select "bee timer" from the list.

Launch the game, go to the kitchen and open the window. Wait for a while and verify that the message is printed every 20 seconds.

Now go north to the lounge. You'll see that we still get the message about the bee flying around. Woops! That bee is only in the kitchen. We'll need to update the timer script so that it only prints the message if the player is in the kitchen.

You've already seen how to do this - an "if" command can check "player is in room". So add a check to the "bee timer" script - if the player is in the kitchen, print the message. If not, then do nothing.

![](TimerBee2.png "TimerBee2.png")

Creating a turn counter
-----------------------

In this section, we'll look at running a script after each turn in the game - **turn scripts**

Here's how we’re going to do it:

-   we'll store the number of turns a player has taken in an attribute called "turns" on the player object
-   this attribute will be added to the list of status attributes, so it is always displayed on-screen
-   we'll create a turn script which will increase the "turns" attribute after each turn
-   so, every time the player takes a turn, the number is increased and the display is automatically updated

### Setting up the turn counter

We have already discussed status attributes, so this should be easy... In the desktop version, select the "player" object and go to the Attributes tab. Add a new attribute, "turns", and make this an integer. 

To turn this into a status attribute, we need to add it to the Status Attributes list at the top of the screen, so click Add there and add "turns" to the list. We can leave the second part blank, as the default is fine.

![](Turncounter1.png "Turncounter1.png")

If you are doing this on the web version, it will, again, be tricky; you need to set it up like this:

![](turns.png "turns.png")

If you launch the game now, you should see the status variable displayed on the right-hand side of the Quest window. We've not yet added the script to increase the value of this though, so it will always say “Turns: 0” no matter how many turns we take. Let's add this script now.

### Increasing the turn counter after each turn

A turn script can apply to a specific room, or it can apply to the entire game. To make a turn script apply for just one room, you simply need to create it in that room. If you create a turn script outside of a room, it will apply to the entire game. For the desktop version, right-click the tree menu or use the Add button to create a turn script. You can drag it to the "Objects" label at the top of the tree to move it outside of all rooms.

Alternatively, go to the Scripts tab of a room (for a turn script for that room only) or the Scripts tab of the game object (for a turn script that applies to the entire game), and at the bottom you will see a section for turn scripts. In this case, we want the game object. Just click Add to create a new turn script.

You can optionally specify a name for your turn script. You can use this if you want to be able to switch your turn script on and off using script commands, in a similar way to how we switched a timer on and off in the previous section. You can leave the name blank for this turn script, as this will always be running.

Make sure the "Enabled when the game begins" box is ticked.

We're going to add a script command which will increase the value of the player's "turns" attribute by 1 each time it is called.

To do this, add the "Set a variable or attribute" command.

In the left box, type:

     player.turns

Then in the box on the right, type

     player.turns + 1

This will add 1 each time the script is called.

![](Turnscript.png "Turnscript.png")

Launch the game now and verify that whenever you type a command, the "Turns" value is automatically updated.

[Next: Using lockable containers](using_lockable_containers.html)