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

Here is the link to add https://nathanj29.github.io/FancyFlicker/

Dimensions of the source: 1067 (width) x 1032 (height).


## Camera limitations
### Diagonal stick input behavior
Square mode (or standard mode) is the mode based on which most controllers rely on for stick inputs: the sticks move in the shape of a circle physically, but the signal they transmit to the computer is in the shape of a square, with pressure ranging from between -1 to 1 for the vertical (Y) and horizontal (X) axis (each measured independently).

The resulting signal received has a maximal magnitude of 1, if purely on the horizontal or vertical axis. For diagonals however the combined pressure of both axis contained physically inside of a circle often translates into a maximal magnitude ranging beyond 1 ! (More or less depending on the controller itself, the controller brand, and how worn out the sticks you are using are.)
The maximal stick signal returned for all directions therefore has the shape of a square with rounded corners ; which you can test for your controller on [this website](https://hardwaretester.com/gamepad) by clicking "Test circularity".

IMAGE MON STICK xbox series RIGHT NOW: notice how the top left and top right parts of my left stick has a stronger deviation due to the plastic of the stick being worn out from overuse.

This mechanic of having stronger diagonal input possibilities is called the « Average error » (or circularity error/radial deviation): it is completely normal to have it to some degree (8 to 14% deviation is the average for most controller brands).

### Journey's deadzone problem
When a game processes raw stick inputs, it often ensures the ones with a magnitude bigger than 1 are corrected by clamping their pressure value back over the outer ring of a circle with a magnitude of 1. This helps preventing too strong inputs that would lead to faster diagonal movements or unusual camera speeds. In such cases, having some degree of radial deviation ensures you can always reach this outer circle, for every input directions and with the strongest input you should be able to give !

On PC _Journey_ in its stick input processing logic however completely bypasses the horizontal and vertical axis deadzone ; acting as if the game-processed pressure of 0% started at 29.689% raw stick input, for either axis.
This leads to clamped inputs not being inscribed under the shape of a circle, but instead **an extended square with rounded corners**, where the arching starts at the edges of the horizontal and vertical axis deadzones: This shape corresponds to the **dashed line** you can view on this tool !

The dashed line shape is a problem for diagonal inputs because even with some stick radial deviation, most controller will not be able to reach it fully for every stick directions ! As a result for the right stick the camera would be moving a little more slowly than it could in theory (still way faster than on Playstation versions).

On PC for some reason the right stick doesn't apply clamping at all to stick positions with a magnitude greater than 1 (but the left stick does !). This means with a controller that has a really strong radial deviation it becomes possible to move the camera very fast: if you were to suceed in giving a raw input of (X=1, Y=1)  the right stick would give a camera speed corresponding to the magnitude of 1.41 !
I have a theory clamping was removed from the PC port to allow for quick mouse movements.


PS versions have a different clamping system ?

Unlike for the left stick, the right stick in Journey for some reason doesn't handle clamping at all !


, and it actually ensures the sticks won't slow down in diagonals in-game. Whenever pressure goes beyond games will clamp values...

Si les développeurs d’un jeu souhaite corriger cette anomalie, alors ils corrigent la réponse carrée en normalisant le vecteur (X, Y) :
ils calculent la magnitude du déplacement (√(X² + Y²)) et, si elle dépasse 1 (donc en diagonale), ils réduisent X et Y proportionnellement pour que la distance reste dans un cercle de rayon 1.


this can result in some controllers being more advantageous to other for Journey, especially given right stick applies no clamping! usually games correct or not the fact inputs can become overly strong in diagonals, but somehow Journey applies the correction only to the left stick.
the square mode allows an input magnitude reaching beyond 100%
cam faster in diagonal:

C’est aussi ce qui est exploité par de nombreux speedrunners car dans certains jeux, se déplacer en diagonale est plus rapide, c’est directement dû au fait que le joystick, ou même les entrées clavier, envoie une réponse carrée, permettant de dépasser une magnitude de 100 %.


Depending on your controller, or how worn out the sticks are it may be possible that upon using this tool you can move the right stick out of the **dashed line, which represents a mapping of the expected range of motion** _Journey_ considers for the sticks.
This dashed line becomes a circle when not considering the vertical and horizontal axis deadzones.

Usually games will force too strong stick inputs back onto this dashed line, which is adjusted based on the size of the game's horizontal and vertical axis deadzones. Quite often the deadzones aren't nearly as huge as the ones _Journey_ applies, which explains why _Journey_ may be expecting slightly too big stick range of motion for your controller.

_Journey_ for whatever reason only applies clamping to the left stick, for pressure values exceeding this boundary. This means with the right stick it is possible on most controllers to maintain 100% sideways pressure on the camera while also moving it a little up or down in-game ! With a stick worn out enough it also becomes possible to obtain faster than normal camera movements in diagonals ! A brand new stick on the other hand probably won't let you get much close to this dashed line threshold when applying diagonal pressure ; resulting in slightly lower camera speed. Technically, playing without the plastic cover top of your controller should allow for even faster diagonal camera movements in theory (I haven't tried it yet, but maybe you could even expect having 100% vertical and horizontal camera speed at the same time !).



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

This [french article](https://www.cowcotland.com/articles/4639/marre-des-manettes-pourries-comment-bien-choisir-sa-manette-partie-1-les-joysticks.html) for explaining a lot about how stick input works, and how games handle them. It also helped making the clamping mechanic of the tool work perfectly as intended.
