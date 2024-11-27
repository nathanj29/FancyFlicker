# Nathanj's Right Stick Flicking Overlay
Tool made to help **practicing Dropshoot** based Fancy Flying techniques in the video game *Journey*. Tracks the right stick movements, indicates when it is time to flick and shows how you flicked. 


## Why and how to flick
Maintaining a camera angle down over a prolonged period of time is important to achieve charging a lot of boost energy..........
To prevent the camera from flattening in *Journey* a flick needs to be performed every 3 seconds at least, otherwise it will flatten abruptly.
Performing a flick will almost always flatten the camera a little, so be mindful of performing it well.

The best kind of flicks are the ones which barely move the right stick out of the vertical axis deadzone (pressure just over or equal to 29.690%), and goes back in the deadzone quickly.
Flicks can either be performed up or down, and both appear as efficient.

This background image shows the vertical axis deadzone in green, and the area that allows vertical camera movements in blue (> or = 29.690%)
Move the right stick in and out of the blue areas to perform a flick.

![BackgroundVerticalDeadzone](https://github.com/user-attachments/assets/2afd876a-2f3d-4fc0-8a60-3ffcac9b7a6b)

Note it is possible to move the right stick out of the external circle representing the expected range of motion from a stick: Usually games will force too strong inputs back onto this outer circle, but *Journey* only does it for the left stick. This means it is possible to maintain 100% sideways pressure on the camera stick while also moving the camera up or down slightly in-game.


## Features
*Tracks the right stick inputs by using Windows API
*Shows the 3 second countdown that occurs anytime the right stick moves back into the vertical axis deadzone
*Shows a meter bar on the right side that represents these 3 seconds.
*The outer square edges get colored flashes when there is 1.5 and 0.5 seconds left on the countdown. The first one indicates half the countdown is gone, and the second one says that it is time you flick.
*Colored expanding circles appear at the peak position reached by the right stick upon flicking. Look at them to know how well you perform.


## How to use?
Make a right stick input to "awaken" the tool, then use it.


## Adding the tool in OBS
It can be added as a browser source to stream/record your practice session, or just play from the preview window with it.
Dimensions of the source: 1102 (width) x 1032 (height). You can crop the 35 (transparent) pixels on the left side of the source after.


## Credits
Loggivan for finding out about the 3 second timer and that vertical pressure is tied to making flicks work !
Chat GPT for helping to code everything.
