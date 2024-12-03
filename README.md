# Nathanj's Right Stick Flicking Overlay
Tool made to help **practice Dropshoot** based Fancy Flying techniques in the video game ***Journey***. Tracks the right stick movements, indicates when it is time to flick and shows how you flicked.

Visit this link to use the tool: https://nathanj29.github.io/RightStickFlickingOverlay/



## Why flicking
When Fancy Flying, the longer you dive, the stronger the boost. However, the maximum boost energy you can charge becomes higher with steeper camera angles (more down, or more up in reverse).

When performing a **Dropshoot** (running on the ground), the camera naturally tends to flatten on its own over time, which can easily weaken the boost.

To maintain a steep camera angle over prolonged periods of time and obtain a great boost, it is important to flick the right stick (camera) at specific intervals, to keep full control over it.



## How to flick ?
A flick needs to be performed every 3 seconds at least, otherwise the camera will flatten abruptly.

Performing a flick will almost always flatten the camera a little, so be mindful of performing it well.

The best kind of flicks are the ones which barely move the right stick out of the vertical axis deadzone (corresponds to a vertical pressure just over or equal to 29.690%), and then go back into the deadzone quickly.

Flicks can either be performed up or down, and both appear as efficient.

This image shows the vertical axis deadzone in green, and the area that allows vertical camera movements in blue.
Move the right stick in and out of the blue areas to perform a flick.
The blue arrows suggest several flicking methods to practice depending on circumstances and preferences.

![right stick flicking possibilities](https://github.com/user-attachments/assets/008a07b2-b6af-410f-805b-368deb7b8be9)

Note it is possible to move the right stick out of the external circle representing the expected range of motion from a stick: Usually games will force too strong stick outputs back onto this outer circle, but *Journey* only does it for the left stick. This means it is possible to maintain 100% sideways pressure on the camera stick while also moving the camera up or down slightly in-game.



## Features
* Tracks the right stick inputs by using Windows API
* Shows a 3 second countdown that occurs anytime the right stick moves back into the vertical axis deadzone (green area)
* Shows a meter bar on the right side that represents these 3 seconds.
* The outer square edges get colored flashes when there is 1.5 and 0.5 seconds left on the countdown. The first one indicates half the countdown is gone, and the second one says that it is time you flick.
* Colored expanding circles appear at the peak position reached by the right stick upon flicking. Look at them to know how well you perform.
* Possibility of practicing flicking with this tool even without playing the game !



## How to use?
Just open the link in any browser.

Move the right stick out of the vertical axis deadzone (green area) to both "awaken" the tool and setup the countdown/meter bar.

Alternatively, add the tool to OBS:



## Adding the tool to OBS
It can be added as a browser source to stream/record your practice session, or just play from the preview window with it.

Here is the link to add https://nathanj29.github.io/RightStickFlickingOverlay/

Dimensions of the source: 1102 (width) x 1032 (height). You can crop the 35 (transparent) pixels on the left side of the source after.



## Known limitations
* The tool is more accurate with higher framerate. **Expect it to sometimes fail showing you successfully flicked when using OBS at 30fps**: it is possible the right stick moves out of the deadzone only in-between 2 OBS frames and thus doesn't reset the 3 seconds countdown, even though it technically did in the game itself. This issue happens only for extremely quick flicks that barely move out of the deadzone, and they are more rare at 60 fps.
* The trail behind the right stick movements becomes longer with lower FPS and shorter at higher FPS. It can be adjusted by downloading the html file, opening it (for example in notepad++), and modifying line 275 `if (previousPositions.length > 15) previousPositions.splice(15);`: higher numbers than 15 will make the trail longer, and vice versa. You can then open this html link in a browser or add it as a local browser source in OBS...



## Credits
Loggivan for finding out about the 3 seconds countdown and that vertical pressure (not horizontal like we thought !) is tied to making flicking work !

Chat GPT for helping to code everything.
