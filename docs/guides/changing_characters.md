---
layout: index
title: Changing Characters
---

Making a character change feature is easy, but you need to understand it first. Once you understand how to make a character change feature, it will be easy. This feature also takes some time.

NOTE: As of Quest 5.4, Quest has full support for changing characters, so this is now obsolete.

Switching
---------

First of all we need to know how to make a switching feature. Here are the steps to make one:

1. Make some objects that you can switch to. Remember that the player is not an object you can switch to. For this guide, we’ll make three objects: a human, a bear and an eagle. Put the character you start out with (the human in this case) as a scenery object.

2. In the ‘game’ object, make an attribute called ‘character’ and set it to an integer. Set the value as 1. Alternatively, you can set the attirbute for the player.

3. Make a command called ‘switch’. You can give it other names like ‘change’, ‘change character’, etc.

The Script
----------

For the script of the ‘switch’ command, do this:

First, check if the attribute ‘game.character’ (choose ‘expression’ and not ‘object’ and then type ‘game’) equals to 1. If it comes true then print a message like “You play as the bear.” Then make game.character into game.character + 1. After that set bear.scenery to true and human.scenery into false.

Now make an Else If script. Make it check if the attribute game.character is 2. If it is true, copy whatever was written above and paste it here. Change the print message into “You play as the eagle”, make bear.scenery to false and make eagle.scenery to true.

Finally for the Else script, paste the same thing, only make the print message to “You play as the human”, change game.character to game.character – 2 and finally eagle.scenery to false and human.scenery to true.

Test out the game. Do you get the wanted message when you type switch? Do the objects turn to scenery or not? If they don’t, check your script. If they do, then continue!

Different Abilities
-------------------

We’ll give different abilities for the characters.

Human: He knows how to use keys and unlock doors.

Bear: He has immense strength.

Eagle: He can fly.

With these abilities, we’ll make a small puzzle. There will be a box with a key inside, which is the key to the winning door. Only the bear can open the door, only the eagle can take the key and only the human can use the key on the door.

Opening the Box
---------------

1. Make a new object. Call it ‘box’ and make it a closed container.

2. Edit the ‘open’ script. Change the message that happens when you open it. Make it “You try to open it” Edit the script like this:

Check if game.character equals to 2. If it comes true, then print a message like “You open the box with great strength.” For the Else script, print a message like “You can’t open it, you’re too weak.” Then close the box.

Taking the Key
--------------

1. Make an object. Call it ‘key’ and put it inside the box.

2. Edit the Inventory tab of the key. Make it take able and run a script (not Default behavior).

The script should check if game.character equals to 3 and if it does, it should print a message like “You fly up and take the key.” Move the key to the player. If it comes false then print something like “It’s too high, you can’t reach it.” Then move the key to the box.

Winning the Game
----------------

1. Make the last object. Call it ‘door’.

2. Edit the key’s Use/Give tab. Using it on the door:

Check if the game.character is equal to 1. If it is, then print a message “You unlock the door. You win!” and finish the game. If it comes false, print a message like “You don’t know how to use that”.

You just made a character changing one-room game!

Movement
--------

What if you’re creating a multi-room game with a switch character feature? Well, here it is:

Edit a library command. Edit the library command ‘go’. You need to copy it first, then only you can edit it. Here is what you have to add:

In the end of the script, there will be a ‘Set variable’ command, which is ‘Set player.parent to exit.to’. After that, add a script which checks the game.character and thus moves the correct character to player.parent. (You must have understood how to do that now). Add a new room and exit and test if it works.

Switching in another Room
-------------------------

Try switching in the other room. It will appear very confusing. So how can we prevent that? This is how:

Edit the ‘switch’ command and cut all the scripts the first If (Not the Else If and Else!) has. Make another If inside that and check if the bear is visible. For the ‘Then’ in that script, paste whatever you had cut before. Add an ‘Else’ script. Paste the same thing inside that, but add another script which moves the player to where the bear is. (bear.parent). Do this for the Else If and Else scripts too.

Congrats! You made a character changing multi room game!
