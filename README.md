----------------Here is what i have done in this game--------


---Stick Bee - A Stick-Man Adventure Game
---Stick Bee is a simple yet engaging stick-man game where the player controls a character to cross platforms by building sticks of appropriate length. The player scores points for successful crossings and gets bonus points for hitting a "perfect area" on the next platform. The game resets upon failure and displays a high score for competitive fun.

--------------------Technologies Used---------------------------
-HTML5 Canvas: For rendering the game's visuals.
-JavaScript: For game logic and interactivity.
-CSS: For styling the webpage and elements like buttons.

--------------------------How the Game Works----------------------------------
--Game Loop:
The game runs in a continuous loop using the requestAnimationFrame method, ensuring smooth animations.
--Core Phases:
-Waiting: Initial state; waiting for player input.
-Stretching: Player holds down the mouse to stretch the stick.
-Turning: Stick falls down, connecting the platform.
-Walking: The stick-man walks across the stick.
-Transitioning: Screen scrolls to the next platform.
-Falling: Player falls if the stick is too short or too long.


---------Scoring:
One point for a successful crossing.
Bonus points for hitting the "perfect area."
-------------------Game Components-------------------
Variables
Below is a breakdown of the variables that i have used in the game:

Game State and Configuration
----phase:
Defines the current phase of the game.
{{Possible values: "waiting", "stretching", "turning", "walking", "transitioning", "falling"}}.

--lastTimestamp:
Tracks the timestamp of the previous animation frame for consistent animations.

--score:
Player's current score.

Displayed on-screen and incremented based on successful crossings.
sceneOffset:
Tracks the offset of the scene for scrolling the background during transitions.

Hero (Player)
heroX:
Horizontal position of the stick-man (changes as it walks across sticks).

heroY:
Vertical position of the stick-man (used for the falling animation).

heroWidth and heroHeight:
Dimensions of the stick-man character (17x30 pixels).

Platforms
platforms:
Array of platform objects. Each platform has:
x: Horizontal position.
w: Width of the platform.
Sticks
sticks:
Array of stick objects, where each stick has:
x: Horizontal position where the stick starts.
length: Length of the stick (increases during the stretching phase).
rotation: Angle of the stick (rotates during the turning phase).
Background Elements
trees:
Array of tree objects for decorative background elements. Each tree has:

x: Position of the tree on the hill.
color: The color of the tree's crown.
Hill Variables:

hill1BaseHeight, hill2BaseHeight: Baseline heights for the hills.
hill1Amplitude, hill2Amplitude: Amplitude of the sinusoidal wave defining the hills.
hill1Stretch, hill2Stretch: Stretch factors controlling hill width.
Game Configuration
Canvas Settings:

canvasWidth and canvasHeight: Dimensions of the game canvas.
Canvas is set to occupy the full screen (window.innerWidth and window.innerHeight).
Gameplay Settings:

stretchingSpeed, turningSpeed, walkingSpeed, transitioningSpeed, fallingSpeed: Control the speed of animations in different phases.
perfectAreaSize: Size of the "perfect area" on each platform for bonus points.



-----------------------Core Game Functions-----------------------------------

1. resetGame()
Resets all game variables and prepares the game for a new round.
2. generatePlatform()
Adds new platforms to the game at random intervals and widths.
3. generateTree()
Adds trees to the background at random positions.
4. animate(timestamp)
The main game loop function, called by requestAnimationFrame.
Updates the game state based on the current phase and redraws the canvas.
5. thePlatformTheStickHits()
Determines if the stick hits the next platform and checks for a perfect hit.
6. draw()
Clears the canvas and redraws all game components, including:
Background elements (hills and trees).
Platforms.
Stick-man.
Sticks.


--------------------------------------Event Listeners------------------------------------
keydown:
Listens for the space key to restart the game.
mousedown:
Starts the stretching phase.
mouseup:
Ends the stretching phase and transitions to the turning phase.
resize:
Adjusts the canvas size dynamically on window resize.
