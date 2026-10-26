# Heading-Out-VR-GOG-
VR Mof for Heading Out


HEADING OUT VR  -  VR mod for "Heading Out" (Unity 2022.3.62f2, IL2CPP x64, URP)
================================================================================

Version 0.1.13 (test build on Quest 3 VDXR "GOG version").



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
1. unzip into the game folder (merge / overwrite).
2. Start your VR runtime first, then the game. If the headset stays black, add the launch option
   -force-d3d11 (Steam: right-click the game > Properties > Launch options).

CONTROLS (an Xbox controller)
-----------------------------
Right trigger ..... RT (gas) 

Left trigger ...... LT (brake)

Left stick ........ steer  

Right stick ....... right stick (looking around isn't needed)

Right stick click . R3 (Tempo); HOLD it = switch 1st / 3rd person

X + Y together .... Start (pause)     

A + B together .... Back / View

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

**test build**
