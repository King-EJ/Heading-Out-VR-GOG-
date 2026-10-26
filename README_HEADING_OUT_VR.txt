HEADING OUT VR  -  VR mod for "Heading Out" (Unity 2022.3.62f2, IL2CPP x64, URP)
================================================================================

Version 0.1.13 (test build).

CHANGES
-------
v0.1.13
- Clear view while driving: the big floating screen (with the grey behind the HUD) is no longer shown while you
  drive - only the HUD parts by your hands, cut out like the icons ([HandHUD] HandsOnly, VR menu "Only the hand HUD
  while driving"). Menus, map, cut-scenes still use the big screen.
- Tape / clock / percentage (top-left of the game's screen) float above the left-hand HUD; the fear meter (top
  middle) floats above the right-hand HUD. Size / place / how much of the screen each part takes: VR menu > Hand HUD.
- No more facing backwards: after a re-centre (also the automatic one when driving starts) the view's direction is
  worked out again from the car, so you face forward in the car.
- The log lists the big HUD pictures while driving (to find what makes the grey).
v0.1.12
- The game didn't start with 0.1.11: skipping the game's render effects for the flat camera crashed its renderer.
  That part is removed. The flat camera is still blanked the pre-0.1.5 way (draws nothing, black background), with
  Cinemachine getting its layers back during its update.
v0.1.11
- The grey background behind the HUD is gone at its source: since 0.1.5 the flat game camera was blanked by
  cutting its draw distance, and the game's own render effects still painted a grey background over it. Now it is
  blanked like before 0.1.5 (nothing drawn, black background = see-through), and the game's render effects are
  skipped for it - while the camera system (Cinemachine) still gets the camera's layers during its own update, so
  steering / gas / brake keep working.
- The lag from 0.1.10 is gone (its per-pixel background guessing is removed).
v0.1.10
- Grey screen / grey hand panels: the game's screen behind its HUD comes out light grey instead of black (the
  0.1.9 guess didn't fix that), and the see-through screen only drops black. Now the mod finds the screen's
  background colour each frame (the colour most of the screen has) and keys exactly that out, whatever it is - so
  the big screen is see-through again and only the HUD shows. The log says "the game's screen background is ...".
- Hand HUD back to see-through (with the dark plate behind it), now that dark icons are kept too.
v0.1.9
- Grey boxes around the icons / on the screen: the flat game camera (whose picture carries the HUD) ran the game's
  post effects over its black background and turned it grey - so the see-through screen and the hand panels showed
  grey boxes. Post effects are now off on that flat camera (the headset picture keeps them).
- Solid screen also on the game's 2D screens (the map, run summary, comic encounters, menus) - not only videos /
  comic panels. Before, you saw the empty 3D world through them.
v0.1.8
- 1st / 3rd person toggle: hold the right stick click while driving (or VR menu > View > "Switch 1st / 3rd
  person"). Third person is a camera behind the car that swings round smoothly when the car turns; set its
  distance, height and smoothing in the VR menu ([View] ChaseDistance / ChaseHeight / ChaseSteadiness).
  "toggle goes to the game's own camera" switches to the game's camera views instead.
- Hand HUD: each corner takes more of the screen (40% wide, 45% high) so the icons aren't cut off. Still cut?
  Raise that hand's "screen part width / height" in the VR menu > Hand HUD.
v0.1.7
- Fear effect off: the game's fear / focus screen effects (the dark vignette, the splash overlay in the middle,
  the eyes-closing effect) are kept switched off - VR menu > Picture "No fear / focus screen effects"
  ([Camera] NoFearEffect).
- Hand HUD: the panels are solid now, so dark icons (gauges etc.) show too - the see-through picture dropped the
  dark parts ([HandHUD] Solid). Each corner also takes a bit more of the screen's height (36%). If an icon is
  still missing, make that hand's "screen part width / height" bigger in the VR menu.
- Cut-scenes (videos and comic panels): the VR screen is solid instead of see-through
  ([UI] SolidInCutscenes, VR menu "Solid screen in cut-scenes").
v0.1.6
- Hand HUD the right way up: it showed the top of the game's screen and moved down when you moved your hands up
  (the screen picture was drawn upside down into the eye pictures). Now the bottom-left / bottom-right icons are by
  your hands and follow them ([Camera] OverlayFlipFix, on).
- Includes the 0.1.5 fix (steering / gas / brake while driving).
v0.1.5
- Found why nothing worked while driving (with any controller): the mod switched off all the layers of the flat
  game camera to save speed, and Cinemachine (the game's camera system) only drives a camera whose layers include
  its virtual cameras. So the game's camera never moved, its "start of stage" shot never finished, and the game
  kept the car on autopilot - ignoring steering, gas and brake. The flat camera is now blanked by cutting its draw
  distance instead, so the game's camera works normally (and the game camera view can follow it again).
v0.1.4
- Controls: 0.1.3 hooked every device onto the game's player at once, which left the game stuck on "keyboard"
  and nothing worked while driving. Now the mod no longer forces anything: the game uses whichever you are using -
  the VR controllers, your Xbox controller, or keyboard / mouse - like it does by itself ([Input] FollowDevice;
  if the game's own switching is off, the mod does the switching).
- Hand HUD: a see-through dark plate behind each hand panel so you can find it and the icons stand out
  (VR menu "Dark plate behind the hand HUD" / [HandHUD] DarkBacking). The log showed the panels were drawn by
  your hands (just below your view unless you raise the controllers) - if you still can't see them, tell me what
  you see by your hands.
- (Good news from your log: the cockpit view now sits at the driver's head and moves with the car.)
v0.1.3
- Your Xbox controller, keyboard and mouse work again together with the VR controllers: the mod used to switch
  the game's input over to the VR controllers alone (and kept fighting the game over it, which also made the VR
  controllers unreliable). Now the game listens to all of them at the same time ([Input] AllDevicesTogether).
- Right stick click: a short click is the game's R3 (Tempo) again; HOLD it to switch cockpit / game camera view.
- Hand HUD while driving: the icons in the bottom-left corner of the game's screen float by your left controller,
  the bottom-right ones by your right controller. VR settings menu > "Hand HUD (driving)": on / off, size,
  left / right, down / up, back / forward, and how much of each screen corner is taken ([HandHUD] in the config).
v0.1.2
- Your log showed the game's camera object never moves (it stayed at the same spot while your car drove 1 km),
  and the mod was reading the stage flags from a switched-off camera controller, so it never thought you were
  driving. Now:
  * Driving = your car is there and the game isn't paused. The cockpit view sits at the driver's head and moves
    with the car - it no longer needs the game's camera at all.
  * Game camera view: when the game's camera isn't near your car, the mod uses its own camera behind the car
    ([View] ChaseDistance / ChaseHeight).
  * Stage start / end shots only count when the game's camera is really at your car.
- The log now says exactly where the game's camera and Cinemachine are each few seconds (please send it again).
v0.1.1
- The view now follows the car: the mod thought the game was paused the whole time (it read the wrong "pause"
  flag), so it treated driving as a menu and kept you in one spot (it only jumped when the camera moved far).
  That also put you under the ground (grass in the sky, white below the horizon).
- Cockpit: you sit at the driver's head (the game's driver model), and his head is hidden (shadow stays) -
  VR menu "Hide the driver's head" / [View] HideDriverHead.
- With your car around but not driving (stage start / end shots), the view follows the game's camera smoothly.
- More in the log (positions, the game's camera rig, why it thinks you're driving or not).
v0.1.0
- First version: stereo VR with head tracking, cockpit view and game-camera view, the VR controllers as an Xbox
  controller, menus / HUD on a floating screen, and gyro steering (option).

WHAT IT DOES
------------
* Stereo VR through OpenXR (SteamVR, Meta/Oculus Link, Virtual Desktop, WMR...).
* Cockpit view (default): you sit in the driver's seat (where the game's own Inside camera is) and turn and tilt
  with the car; look around freely with your head.
  Game camera view: you are where the game's current camera is (change its views with the game's camera button)
  and turn with the car.
  Switch while driving: hold the right stick click.
* Hand HUD: the bottom-left HUD icons float by your left controller, the bottom-right ones by your right
  controller (size / place in the VR settings menu > Hand HUD).
* GYRO STEERING (option, off by default) - VR settings menu > Driving > "Gyro steering":
    Wheel     = hold both controllers like a steering wheel and turn it
    RightHand = roll the right controller left / right (like a Wii wheel)
    LeftHand  = the same with the left controller
  Straight ahead = how you hold the controllers when driving starts, or when you re-centre (both stick clicks,
  or "gyro: straight ahead = now" in the menu). "full lock at" = how far you turn for full steering (90 degrees
  default), "dead zone" = how much around straight ahead does nothing. The left stick still steers too
  (whichever steers more wins).
* Menus and the HUD are on a screen floating in front of you (see-through).
* The VR controllers are an Xbox controller for the game (your real Xbox controller, keyboard and mouse keep
  working too).
* Depth of field, motion blur and lens distortion are switched off (they don't work in a headset).

INSTALL
-------
1. BepInEx 6 IL2CPP (be.788) is already in the game folder - you have it.
2. Copy the BepInEx folder from this zip into the game folder (merge / overwrite).
   You should have  BepInEx\plugins\HOVR\HOVR.dll  and  BepInEx\plugins\HOVR\OpenXR.dll
3. Start your VR runtime first, then the game. If the headset stays black, add the launch option
   -force-d3d11 (Steam: right-click the game > Properties > Launch options).

CONTROLS (an Xbox controller)
-----------------------------
Right trigger ..... RT (gas)               Left trigger ...... LT (brake)
Left stick ........ steer                  Right stick ....... right stick (looking around isn't needed)
A / B ............. A / B                  X / Y ............. X / Y
Right grip ........ RB                     Left grip ......... LB
Left stick click .. L3                     Right stick click . R3 (Tempo); HOLD it = switch 1st / 3rd person
X + Y together .... Start (pause)          A + B together .... Back / View
Menus: like an Xbox controller; the right stick is also the d-pad.
Re-centre the view (and gyro straight ahead): press both stick clicks together.
VR SETTINGS MENU: hold Y + left stick click for 1.7 s (view, gyro steering, buttons, screen...).
Every button can be changed: BepInEx\config\headingout.vr.cfg, [Controls] (and [RaceControls] with
DrivingButtons = Custom).

CONFIG  -  BepInEx\config\headingout.vr.cfg (edits apply live)
---------------------------------------------------------------
[View]     View (Cockpit / GameCamera), TurnWithCar, TiltWithCar, TiltSmoothing, EyeForwardOffset, EyeSideOffset,
           HeadSmoothing, GameCameraHeight
[Driving]  GyroSteering (Off / Wheel / RightHand / LeftHand), GyroAngle, GyroDeadzone
[Camera]   EyeHeightOffset, WorldScale, RenderScale, PostProcessing, NoDepthOfField, NoMotionBlur, NoLensDistortion
[UI]       floating screen place / size / see-through

PLEASE SEND AFTER THE FIRST TEST
--------------------------------
BepInEx\LogOutput.log - it lists the game's controls, the camera views and where the driver's seat was found,
your car and the cameras. A screenshot from the headset helps a lot (especially if the view is in the wrong place).
