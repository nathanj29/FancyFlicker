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
* Indicates when you apply the minimal pressure recognized in-game (see "Gold lines" section)
* You can **zoom in and out** by resizing the browser window, doing ctrl + mouse wheel, or doing ctrl and the + or - key.



## How to use the Fancy Flicker?
Just open the link in any browser (some offer better framerate stability than others).

Move the right stick out of the vertical axis deadzone (green area) to setup the countdown/meter bar and start flicking.

The measured framerate stabilizes after 130 frames are loaded (about 4 seconds at 30 FPS, 2 seconds at 60 FPS)

Alternatively, add the tool to OBS:



## Adding the tool to OBS
It can be added as a browser source to stream/record your practice session, or just play from the preview window with it.

Here is the link to add https://nathanj29.github.io/FancyFlicker/

Dimensions of the source: 1067 (width) x 1032 (height).



## Gold lines
![gold lines](https://i.imgur.com/qELaaE0.png)

2 gold lines are displayed on the tool. Entering a gold line or moving past it with the right stick and reaching the blue colored background is considered being outside the vertical axis deadzone.

_Journey_ recognizes 90 possible stick pressure points (outside of 0% in-game pressure, measured whenever the stick is in the deadzone). These pressure points are scaled from the raw stick input used for this tool: each are spaced by 0.781% with one another, but they don't recessarily return in-game pressure spaced equally ! The gold lines correspond to **the minimal vertical pressure range the game acknowledges**, which return an in-game camera pressure of 0,00000186%.
The true stick pressure to apply for this ranges from between 29.690% to 30.470%.

The 0,00000186% pressure value returned in-game is so low that if applied **the camera won't move at all**. Yet _Journey_ still considers it to be a pressure different to 0%. As a result, if you manage to maintain this pressure for prolonged periods of time the camera will never flatten. This can be especially useful for slow circle dropshoot. This pressure range is so precise however that it can't be a reliable option to count on it working every time from just muscle memory!



## Camera limitations
### Diagonal deviation
Square mode (or standard mode) is the mode based on which most controllers rely on for sticks inputs: the sticks move in the shape of a circle physically, but the signal they transmit is in the shape of a square, with pressure ranging from between -1 to 1 for the vertical (Y) and horizontal (X) axis (each measured independently).

The resulting signal received has a maximal magnitude of 1, if purely on the horizontal or vertical axis. For diagonals however the combined pressure of both axis physically contained inside of a circle often translates into a maximal magnitude reaching beyond 1 ! (More or less, depending on the controller itself, the controller brand, and how worn out the sticks you are using are.)
The combined maximal magnitudes for every directions therefore take the shape of a square with rounded corners ; which you can test for your controller on [this website](https://hardwaretester.com/gamepad) by clicking "Test circularity".

![circularity test on my controller](https://i.imgur.com/C4HxBP7.png)

This image above shows the circularity of my left and right sticks (xbox series controller): Notice how the top left and top right parts of my left stick have a stronger deviation due to the plastic of the stick being worn out from overuse...

This mechanic of having stronger diagonal input possibilities is called the « Average error » (or circularity error/radial deviation): it is completely normal to have it to some degree (8 to 14% deviation is typical for most controller brands).

### Journey's cross-shaped deadzone consequences
When a game processes raw stick inputs, it often ensures inputs with a magnitude bigger than 1 are corrected by clamping their pressure value back over the circumference of a circle with a magnitude of 1. This helps preventing too strong inputs that would otherwise lead to faster diagonal movements or unusual camera speed. Note having some degree of radial deviation is what ensures you can always reach this magnitude of 1 for every input directions !

On PC, _Journey_ with its stick input processing logic however completely bypasses the ridiculously huge horizontal and vertical axis deadzones ; acting as if a game-processed pressure of 0% started at 29.689% raw stick input, for either axis.
This leads to the "magnitude = 1" representation no longer lying on the circumference of a circle, but instead on **an extended square with rounded corners**, where the arching starts at the edges of the horizontal and vertical axis deadzones: This shape corresponds to the **gold dashed line** you can view on the following image, and **it corresponds to a magnitude of 1 for every input directions based on _Journey_'s mapping** (or to put it simply: the expected range of motion to reach for _Journey_) !

![clamping explained](https://i.imgur.com/Dzn3XNZ.png)

This gold dashed line shape is a problem for diagonal inputs because even with some stick radial deviation, most controller brands won't be able to reach it fully in every directions ! (At least not without a custom re-calibration of pressure sensitivity, or worn out sticks.) For the camera this could lead to a speed issue, however for some reason on PC **_Journey_ doesn't even apply clamping at all to the right stick's pressure positions with a magnitude exceeding 1 !** (but the left stick does apply it correctly.) This means playing with a right stick that has a really strong radial deviation involves it being possible to move the camera abnormally fast (yet nowhere near as fast as with a mouse of course).

For most controllers it should remain possible to maintain 100% sideways pressure on the camera while also moving it a little up or down in-game (just peaking out of the vertical axis deadzone) ! If you were to succeed in giving a raw input of (X=1, Y=1), the right stick would give a camera speed corresponding to the maximal magnitude of 1.41 ! The camera would then be moving at 1.41 times its theoretical max speed. This can result in some controllers being more advantageous than others for _Journey_.

I have a theory clamping was removed by the PC porting team solely for the right stick, to allow for quicker mouse movements...

### PlayStation right stick clamping?
It is highly probable the reason why PlayStation versions of _Journey_ have slow camera speed in diagonals is due to clamping working (almost) as intended. If you were to move the camera fully sideways and then making it move slightly up or down in-game you would instantly notice it slowing down in speed significantly however ! The reason I believe to be behind this is that _Journey_ doesn't apply clamping to the right stick the way it's supposed to: instead of clamping pressure values over the gold dotted line from the image above, it instead clamps these right stick values over the shape of a perfect circle (acting as if the right stick horizontal and vertical axis deadzones didn't exist, even though they do)! A circular clamping pattern can't account for the deadzones of _Journey_, which means it also clamps down pressure values with a magnitude inferior to 1! Hence why diagonal right stick inputs aren't convenient to use at all on PlayStation... Right stick camera control was added late during development of the game (it used to be purely Sixaxis at first), so it is hard to know whether this slower diagonal camera speed could be a mistake or intended.

Keep in mind that for PlayStation, instead of using diagonal right stick inputs you can combine the use of the right stick (purely on the X or Y axis), with Sixaxis on the opposite axis at the same time (by moving the controller) ! This allows to reach speeds than can even exceed PC controller camera speed. 



## Known limitations
* The right stick position updates more frequently when the tool runs at a higher framerate. **Expect it to sometimes fail showing you successfully flicked when using it at 30 FPS**: it is possible the right stick moves out of the deadzone only in-between 2 frames and thus doesn't reset the 3 seconds countdown, even though it technically did in the game itself. This issue happens only for extremely quick flicks that barely move out of the deadzone, and they are more rare at 60 fps.
* Colored flash timing and trail length were adjusted based on 30, 60 and 120 FPS values. If your monitor has a super high refresh rate, expect a trail longer than usual or flashes occuring a little earlier than designed for.
* If you open the tool on a browser that runs it at an inconsistent framerate, it is possible the tool will fail to reset the 3 seconds timer from time to time: e.g. if the framerate suddenly drops below 61 FPS, or below 31 FPS.



## Credits
Loggivan for discovering the 3 seconds countdown existance and that vertical pressure (not horizontal like we thought !) is tied to making flicking work !

ChatGPT and ClaudeAI for helping to code everything.

This [french article](https://www.cowcotland.com/articles/4639/marre-des-manettes-pourries-comment-bien-choisir-sa-manette-partie-1-les-joysticks.html) for explaining a lot about how stick input works, and how games handle them. It also helped making the clamping mechanic of the tool work perfectly as intended.
