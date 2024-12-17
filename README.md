# Nathanj's Fancy Flicker
Tool made to help **practicing Dropshoot** based Fancy Flying techniques in the video game ***Journey***.

Tracks the right stick movements, indicates when it is time to flick and shows how you flicked.

Visit [this link](https://nathanj29.github.io/NathanjFancyFlicker/) to use the tool.



## Why flicking
When Fancy Flying, the longer you dive, the stronger the boost can be. However, the maximum boost energy you can charge becomes higher with steeper camera angles (= aiming more down, or up in reverse).

When performing a **Dropshoot** (running on the ground), the camera naturally tends to flatten on its own over time, which can easily weaken the boost.

To maintain a steep camera angle over prolonged periods of time for a great boost, it is important to flick the right stick (camera) at specific intervals, to keep full control over it.



## How to flick ?
Giving any kind of vertical input to the camera is a flick !

A flick needs to be performed every 3 seconds at least, otherwise the camera will flatten abruptly during the dropshoot.

Performing a flick will almost always flatten the camera a little, so be mindful of performing it well and only when needed (don't overdo it !)

The best kind of flicks are the ones which barely move the right stick out of the vertical axis deadzone (corresponds to a vertical pressure just over or equal to 29.690%), and then go back into the deadzone quickly.

Flicks can either be performed up or down, and both appear as efficient.

This image shows the vertical axis deadzone in green, and the area that allows vertical camera movements in blue.
Move the right stick in and out of the blue areas to perform a flick.
The blue arrows suggest several flicking methods to practice depending on circumstances and preferences.

![right stick flicking possibilities](https://github.com/user-attachments/assets/008a07b2-b6af-410f-805b-368deb7b8be9)

Note it is possible to move the right stick out of the external circle representing the expected range of motion from a stick: Usually games will force too strong stick outputs back onto this outer circle, but *Journey* only does it for the left stick. This means it is possible to maintain 100% sideways pressure on the camera stick while also moving the camera up or down slightly in-game.



## Features
* Tracks the right stick inputs by using the browser API
* Displays a 3 second countdown that resets by leaving the deadzone, and starts counting down anytime the right stick moves back into the vertical axis deadzone (green area)
* Shows a meter bar on the right side that represents these 3 seconds.
* The outer square edges get colored flashes when there is 1.5 and 0.5 seconds left on the countdown. The first one indicates half the countdown is gone, and the second one says that it is time you flick.
* Measures the framerate the tool is running at to better adjust the right stick trail length and give more precision to the colored flashes.
* Colored expanding circles appear at the peak position reached by the right stick upon flicking. Look at them to know how well you perform.
* Possibility of practicing flicking with this tool even without playing the game !



## How to use?
Just open the link in any browser (some offer better framerate stability than others).

Move the right stick out of the vertical axis deadzone (green area) to both "awaken" the tool and setup the countdown/meter bar.

The measured framerate stabilizes after 130 frames are loaded (about 4 seconds at 30 FPS, 2 seconds at 60 FPS)

Alternatively, add the tool to OBS:



## Adding the tool to OBS
It can be added as a browser source to stream/record your practice session, or just play from the preview window with it.

Here is the link to add https://nathanj29.github.io/NathanjFancyFlicker/

Dimensions of the source: 1102 (width) x 1032 (height). You can crop the 35 (transparent) pixels on the left side of the source after.



## Known limitations
* The tool is more accurate with higher framerate. **Expect it to sometimes fail showing you successfully flicked when using it at 30 FPS**: it is possible the right stick moves out of the deadzone only in-between 2 frames and thus doesn't reset the 3 seconds countdown, even though it technically did in the game itself. This issue happens only for extremely quick flicks that barely move out of the deadzone, and they are more rare at 60 fps.
* Colored flash timing and trail length were adjusted based on 30 60 and 120 FPS values. If your monitor has a super high refresh rate, expect a trail longer than usual or flashes occuring a little earlier than designed for.
* If you open the tool on a browser that runs it at an inconsistent framerate, it is possible the tool will fail to reset the 3 seconds timer from time to time: e.g. if the framerate drops below 61 FPS while the monitor's refresh rate is set higher than 60 Hz, or if the framerate drops below 31 FPS on a 60Hz monitor.



## Credits
Loggivan for discovering the 3 seconds countdown existance and that vertical pressure (not horizontal like we thought !) is tied to making flicking work !

Chat GPT for helping to code everything.
