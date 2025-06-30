# Nathanj's Fancy Flicker
Tool made to help **practicing Dropshoot** based Fancy Flying techniques in the video game ***Journey***.

Tracks the right stick movements, indicates when it is time to flick and shows how you flicked.

Visit [this link](https://nathanj29.github.io/FancyFlicker/) to use the tool.



## Why flicking ?
When Fancy Flying, the longer you dive, the stronger the boost can be. However, the maximum boost energy you can charge becomes higher with steeper camera angles (= aiming more down, or up in reverse).

When performing a **Dropshoot** (running on the ground), the camera naturally tends to flatten on its own over time, which can easily weaken the boost.

To maintain a steep camera angle over prolonged periods of time for a great boost, it is important to flick the right stick (camera) at specific intervals, to keep full control over it.



## How to flick ?
Giving any kind of vertical input to the camera is a flick !

A flick needs to be performed every 3 seconds at least, otherwise the camera will flatten abruptly during the dropshoot.

Performing a flick will almost always flatten the camera a little, so be mindful of performing it well and only when needed (don't overdo it !)

The best kind of flicks are the ones which barely move the right stick out of the vertical axis deadzone (corresponds to a vertical pressure just over or equal to 29.690%), and then go back in it quickly.

Flicks can either be performed up or down, and both appear as efficient.

This image below shows the vertical axis deadzone in green (no vertical camera movement). The pressure areas that translate into vertical camera movements in-game are in blue.
Move the right stick in and out of any blue area to perform a flick.
Blue arrows suggest several flicking methods you can practice depending on circumstances and preferences.

![right stick flicking possibilities](https://i.imgur.com/hF563yj.png)



## Features of the Fancy Flicker
* Shows the 3 right stick **deadzone types**, upon loading the tool.
* Tracks the right stick inputs by using the browser API.
* **Shows the right stick coordinates** in the bottom left corner.
* Displays a **3 second countdown** that resets to 3 by exiting the vertical axis deadzone (green color), and starts counting down whenever the right stick goes back in it.
* Shows a **meter bar** on the right side that represents these 3 seconds.
* The outer square edges get **colored flashes** when there is 1.5 and 0.5 seconds left on the countdown. The first one indicates half the countdown is gone, and the second one says that it is time to consider flicking.
* Measures the framerate the tool is running at to better adjust the right stick trail length and give more precision to the colored flashes.
* **Cyan expanding circles** appear at the peak position reached by the right stick upon flicking. Look at them to know how well you perform.
* Possibility of practicing flicking with this tool even without playing the game !
* Indicates when you apply the minimal pressure recognized in-game (see "Golden lines" section)
* You can **zoom in and out** by resizing the browser window, doing ctrl + mouse wheel, or doing ctrl and the + or - key.



## How to use the Fancy Flicker?
Just open the link in any browser (some offer better framerate stability than others).

Move the right stick out of the vertical axis deadzone (green area) to setup the countdown/meter bar and start flicking.

The measured framerate stabilizes after 130 frames are loaded (about 4 seconds at 30 FPS, 2 seconds at 60 FPS)

Alternatively, add the tool to OBS:



## Adding the tool to OBS
It can be added as a browser source to stream/record your practice session, or just play from the preview window with it.

Here is the link to add https://nathanj29.github.io/NathanjFancyFlicker/

Dimensions of the source: 1067 (width) x 1032 (height).


## Camera speed limitations
Depending on your controller, or how worn out the sticks are it may be possible that upon using this tool you can move the right stick out of the **dotted line, which represents a mapping of the expected range of motion** _Journey_ considers for the sticks.
This dotted line becomes a circle when not considering the vertical and horizontal axis deadzones.

Usually games will force too strong stick inputs back onto this dotted line, which is adjusted based on the size of the game's horizontal and vertical axis deadzones. Quite often the deadzones aren't nearly as huge as the ones _Journey_ applies, which explains why _Journey_ may be expecting slightly too big stick range of motion for your controller.

_Journey_ for whatever reason only applies clamping to the left stick, for pressure values exceeding this boundary. This means with the right stick it is possible on most controllers to maintain 100% sideways pressure on the camera while also moving it a little up or down in-game ! With a stick worn out enough it also becomes possible to obtain faster than normal camera movements in diagonals ! A brand new stick on the other hand probably won't let you get much close to this dotted line threshold when applying diagonal pressure ; resulting in slightly lower camera speed. Technically, playing without the plastic cover top of your controller should allow for even faster diagonal camera movements in theory (I haven't tried it yet, but maybe you could even expect having 100% vertical and horizontal camera speed at the same time !).



## Golden lines
2 golden lines are displayed on the tool. Entering a golden line or moving past it with the stick and reaching the blue colored background is considered being outside the vertical axis deadzone.

_Journey_ recognizes only 90 possible stick pressure points (outside of 0% pressure, whenever the stick is in the deadzone). These pressure points are scaled from the raw stick input used for this tool. The golden lines correspond to **the minimal vertical pressure range the game acknowledges**, which return an in-game camera pressure of 0,00000186%.
The true stick pressure to apply for this ranges from between 29.690% to 30.470%.

The in-game pressure value returned when the stick is in a golden line is so low that if applied **the camera won't move at all in-game**. Yet _Journey_ still considers it to be a pressure different than 0%. As a result, if you manage to maintain this pressure for prolonged periods of time the camera will never flatten. This can be especially useful for slow circle dropshoot. This pressure range is so precise however that it can't be a reliable option to count on it working every time from just muscle memory!



## Known limitations
* The right stick position updates more frequently when the tool runs at a higher framerate. **Expect it to sometimes fail showing you successfully flicked when using it at 30 FPS**: it is possible the right stick moves out of the deadzone only in-between 2 frames and thus doesn't reset the 3 seconds countdown, even though it technically did in the game itself. This issue happens only for extremely quick flicks that barely move out of the deadzone, and they are more rare at 60 fps.
* Colored flash timing and trail length were adjusted based on 30, 60 and 120 FPS values. If your monitor has a super high refresh rate, expect a trail longer than usual or flashes occuring a little earlier than designed for.
* If you open the tool on a browser that runs it at an inconsistent framerate, it is possible the tool will fail to reset the 3 seconds timer from time to time: e.g. if the framerate suddenly drops below 61 FPS, or below 31 FPS.



## Credits
Loggivan for discovering the 3 seconds countdown existance and that vertical pressure (not horizontal like we thought !) is tied to making flicking work !

ChatGPT and ClaudeAI for helping to code everything.
