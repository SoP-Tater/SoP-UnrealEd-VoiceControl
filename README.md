# -=SoP=- UnrealEd Voice Control

**User Manual**

[**Download Latest Version**](https://github.com/SoP-Tater/SoP-UnrealEd-VoiceControl/releases/latest)

---

## Contents

1. Introduction and Usage Overview
2. Installation and Launching Voice Control
3. Getting Started
4. Configuration
5. Hotkeys and Aliases
6. Brush Builders and Properties
7. Movement and Clipping
8. Distance Measurement
9. Real-Time Preview
 10. Command Reference
 11. Troubleshooting

## 1. Introduction And Usage Overview

Welcome to -=SoP=- UnrealEd Voice Control, a voice-operated companion
application designed for the Unreal Tournament 99 editor (UnrealEd).

This program allows you to perform many of your everyday mapping tasks simply
by speaking commands, reducing the need to navigate menus, click toolbar
buttons, and remember numerous keyboard shortcuts.

Voice Control works alongside UnrealEd without replacing its standard controls
or changing the way the editor normally functions. You can continue to use
your mouse and keyboard as you always have.

Some of the features include:

- Voice-controlled toolbar and menu commands.
- Brush creation and builder property adjustments.
- Actor and brush selection.
- Browser and properties window management.
- Brush movement, rotation, and clipping.
- Viewport real-time preview control.
- Distance measurement using two reference points.
- Customizable voice commands, hotkeys, and aliases.
- Online speech recognition with offline fallback.

One of the key features of Voice Control is its ability to be personalized.
You can assign your own spoken phrases to existing commands, making them
easier to remember, pronounce, and recognize.

The goal of this program is not to replace the traditional way of mapping,
but to make mapping easier, faster, and more enjoyable.

### Brief Usage Overview

Once UnrealEd is launched with Voice Control, a microphone button is available
on the editor toolbar. Voice Control can be configured to listen continuously
or only when activated. Simply speak a supported command, and the program
will perform the corresponding operation within UnrealEd.

For example:

```text
"Build cube"             Activates the Cube Builder.
"Build cube properties"  Opens the Cube Builder properties.
"Height 512"             Sets the height of the cube.
"Width 256"              Sets the width of the cube.
"Breadth 128"            Sets the breadth of the cube.
"Close"                  Closes the properties window.
"Add"                    Adds the brush to your map.
"Save"                   Saves your map.
```

When changing builder properties by voice, the red builder brush updates
dynamically with each successful property change. This allows you to see the
results immediately in the editor viewports without having to click Build.
You can continue adjusting individual dimensions until the brush meets your
requirements.

The on-screen status display provides feedback on microphone activity,
recognized commands, and command execution.

All supported commands are listed in the supplied SoP_VoiceHotkeys.txt file.
This file also allows you to customize commands and settings without modifying
the program itself.

To temporarily pause or resume voice recognition in continuous mode, click
the microphone icon on the UnrealEd toolbar or use your assigned microphone
hotkey. Voice recognition may continue when you switch to another
application, so pause it manually when needed.

## 2. Installation And Launching Voice Control

### Version Compatibility

Voice Control was developed and extensively tested using UnrealEd 469f, with
limited testing performed on versions 469d and 469e.

Compatibility with other versions of UnrealEd has not been verified. Users
are encouraged to report any compatibility issues they encounter.

### Distribution Package

The package contains the following files:

```text
UnrealEd_With_VoiceControl.exe    UnrealEd Voice Control launcher
SoP_UnrealEd_VoiceControl.exe     Voice Control application
SoP_UnrealEd_ToolIDs.csv          Toolbar command mappings
SoP_VoiceHotkeys.txt              Settings, hotkeys, aliases, command list
SoP_VoiceControl_ReadMe.txt       This user manual
```

### Installation

Close UnrealEd before installing. Extract the supplied files into your Unreal
Tournament System folder, where UnrealEd.exe and UnrealEd.ini are located.
Keep the supplied program files together.

### Launching Unrealed

To use Voice Control, start UnrealEd using UnrealEd_With_VoiceControl.exe
instead of UnrealEd.exe.

The launcher starts UnrealEd and initializes Voice Control automatically.
A microphone icon will appear on the editor toolbar, along with the Voice
Control status display.

Voice Control runs in the background while UnrealEd is open and automatically
shuts down when you close the editor.

If you wish to use UnrealEd without Voice Control, simply launch UnrealEd.exe
as you normally would.

## 3. Getting Started

### Microphone Controls

The microphone icon on the UnrealEd toolbar controls voice recognition.
There are two operating modes:

```text
Always On: The microphone continuously listens for spoken commands until
           paused. Click the icon again to resume listening.
```

```text
Manual:    Activate the microphone whenever you wish to issue a command.
           Certain workflows, such as builder properties, may keep
           recognition active while in use.
```

The operating mode can be configured in SoP_VoiceHotkeys.txt. You can also
assign a keyboard hotkey to control the microphone without clicking the icon.

Voice recognition may continue when UnrealEd is not the active application.
Use the microphone icon or your assigned microphone hotkey to pause recognition
before switching applications, and resume it manually when needed.

Voice recognition accuracy will vary depending on your microphone, its
settings, and your surrounding environment. You may need to adjust your
microphone settings and speaking volume for reliable command recognition.

### Status Display

The Voice Control status display provides feedback on three items:

- Microphone status: Whether the microphone is listening or stopped.
- Last: The last recognized spoken phrase.
- Status: The result of the command.

This display is particularly useful when troubleshooting speech recognition
or creating personalized aliases.

The status display can be repositioned by clicking and dragging it to a
convenient location. Its position is automatically saved and restored the
next time you launch Voice Control.

## 4. Configuration

Voice Control uses SoP_VoiceHotkeys.txt to store its settings, keyboard
shortcuts, and personalized voice commands. This file can be edited using
Notepad or any standard text editor.

### Settings

The [Settings] section contains the following options:

SpeechDelay=750

```text
Determines how long the program waits for silence before processing a
spoken command. The value is in milliseconds (500 to 2000). Increasing
this value allows longer pauses while speaking. Decreasing it provides
a quicker response but may cut off commands prematurely.
```

AlwaysOn=true

```text
true  - Continuous voice recognition.
false - Manually activated voice recognition.
```

MicToggleHotkey=F9

```text
Example keyboard shortcut for controlling the microphone. Choose a shortcut
that does not conflict with any existing UnrealEd or Voice Control hotkey.
Conflicting shortcuts may trigger unintended editor commands.
```

RightMargin and BottomOffset

```text
These values control the saved position of the Voice Control status display
and are automatically updated when you reposition it.
```

### Comments

Any line beginning with a # character is treated as a comment and ignored by
Voice Control. Comments can be used to organize sections, provide instructions,
or temporarily disable an assignment. Commenting out a built-in command's
reference line does not disable the built-in command itself.

### Applying Changes

After making changes, save SoP_VoiceHotkeys.txt.

- If UnrealEd is closed: Your changes will automatically take effect the
```text
  next time you launch Voice Control.
```

- If UnrealEd is open: Simply say "Reload commands" to apply and test your
```text
  changes immediately without restarting the editor.
```

## 5. Hotkeys And Aliases

### Hotkeys

Voice Control allows spoken commands to activate UnrealEd keyboard shortcuts.
For example:

```text
  undo=ctrl+z
  duplicate=ctrl+d
  delete=delete
```

The spoken command appears to the left of the equals sign, and the associated
keyboard shortcut appears to the right.

If you use a different UnrealEd keyboard scheme or customized shortcuts, you
can change these assignments accordingly.

You can also add your own voice commands for UnrealEd keyboard shortcuts that
are not already listed. Simply enter your desired spoken phrase to the left
of the equals sign and the corresponding keyboard shortcut to the right.

For example:

```text
  my command=ctrl+shift+k
```

This example assumes you have assigned Ctrl+Shift+K to the desired operation
in UnrealEd. Voice Control sends the shortcut; it does not create the UnrealEd
key binding itself.

### Built-In Commands

Commands with nothing to the left of the equals sign are already supported by
Voice Control. For example:

```text
  =build cube
  =build cylinder
  =build sphere
```

These commands can be spoken exactly as listed without any additional
configuration. The blank-left entries serve as a command reference.

### Creating Aliases

An alias allows you to assign your own spoken phrase to an existing command.
For example:

```text
  cube=build cube
  ball=build sphere
  stairs=build linear stairs
```

You can now simply say "Cube", "Ball", or "Stairs" instead of the full command.

Aliases are also useful for correcting speech recognition errors. If speech
recognition consistently interprets "Torus" as "Taurus", you can add:

```text
  torus=build torus
  taurus=build torus
```

Both spoken phrases will now perform the same operation.

Multiple aliases can be assigned to the same command. Avoid assigning the
same alias to different commands within the global command list or within
the same builder-specific alias section. The same alias may be reused in
different builder-specific sections.

See Applying Changes in Section 4 for instructions on reloading your changes.

## 6. Brush Builders And Properties

### Brush Builders

All supported brush builders can be activated by speaking their assigned
commands. For example:

```text
  "Build cube"
  "Build cylinder"
  "Build spiral stairs"
```

If you have assigned aliases to these commands, you can simply speak the
alias instead.

### Opening Builder Properties

To open a builder's properties window, speak the full builder command followed
by "Properties". For example:

```text
  "Build cube properties"
  "Build cylinder properties"
  "Build spiral stairs properties"
```

If you have assigned aliases in SoP_VoiceHotkeys.txt, such as:

```text
  cube=build cube
  cylinder=build cylinder
  spiral stairs=build spiral stairs
```

You can simply say:

```text
  "Cube properties"
  "Cylinder properties"
  "Spiral stairs properties"
```

There is no need to create a separate alias for the properties command.
Voice Control automatically recognizes your builder alias when followed
by the word "Properties".

### Changing Properties

Once the properties window is open, speak the property name followed by its
desired value. For example, in Cube Properties:

```text
  "Height 512"
  "Width 256"
  "Breadth 128"
```


You can also speak the property name, pause, and then speak the desired value
separately.

When speaking numerical values, always check the status display to ensure
the number was recognized correctly. Speech recognition may interpret
certain numbers as times, dates, or other numerical formats. For example,
512 may be interpreted as 5:12.

For more reliable recognition, particularly with three-digit or larger
numbers, try speaking each digit individually.

```text
  "Height five one two"
  "Width two five six"
  "Breadth one two eight"
```

This can help prevent incorrect numerical interpretations and unintended
changes to the builder brush.

The red builder brush updates dynamically with each successful property
change. There is no need to click Build after each adjustment.

### Properties Window Focus

Voice Control recognizes property commands according to the currently active
builder properties window.

Clicking outside the properties window suspends its property-specific commands.
Clicking back into the window restores them without having to repeat the
command to open it.

Switching to another supported builder's properties window automatically
switches to that builder's supported property commands.

### Builder-Specific Aliases

Property aliases can be assigned individually to each supported builder.
This allows the same spoken word to perform different functions depending on
which builder's properties window is active.

For example, you may prefer to use X, Y, and Z instead of Width, Breadth, and
Height. You can place the following section at the end of the text file:

```text
  [Aliases:Cube]
  x=width
  y=breadth
  z=height
```

These aliases apply only to Cube Properties. You can now say "X 256", for
example. Choose the alias-to-property assignments that suit your workflow.
You can reuse X, Y, and Z in other builder-specific sections, even when
they represent different properties.

For another builder, create a separate [Aliases:...] section using its
builder name without the leading word "build", such as [Aliases:Torus].
Only supported properties can be assigned within each builder's alias section.
Place global hotkeys and builder command aliases outside these sections.

### Reset And Close

```text
"Reset" - Restores the builder's default property values.
"Close" - Closes the properties window.
```

A complete list of supported builders and their available property commands
can be found in SoP_VoiceHotkeys.txt. Tarquin Extrude can be activated by
voice, but its individual properties are not voice-controlled.

## 7. Movement And Clipping

### Movement

Voice Control allows you to move brushes and actors without manually holding
down the Ctrl or Shift keys.

```text
"Drag"    - Holds the Ctrl key.
"Move"    - Holds the Shift key.
"Release" - Releases the held key.
```

Once a movement command is activated, use your mouse as you normally would
in UnrealEd. Say "Release" when finished.

Example: Moving a brush

1. Select the desired brush.
2. Say "Drag".
3. Hold the left mouse button and move the mouse to reposition the brush.
4. Say "Release" when finished.

Example: Moving a brush along with the viewport camera

1. Select the desired brush.
2. Say "Move".
3. Hold the left mouse button and move the mouse to reposition the brush.
4. Say "Release" when finished.

The "Drag" and "Move" commands can also be used to rotate selected brushes
and actors. Simply use the right mouse button instead of the left mouse
button. There is no need to issue a separate rotation command. Say "Release"
when finished.

### Brush Clipping

The following commands are available for brush clipping:

```text
"Clip marker"             Activates clipping mode. Ctrl is handled automatically
                          when placing markers with the right mouse button.
"Flip marker"             Reverses the clipping direction.
"Clip selected"           Clips the selected brushes.
"Split selected"          Splits the selected brushes.
"Delete clipping markers" Removes the clipping markers.
"Release"                 Releases the held key, clears clipping markers,
                          and returns to Camera Movement mode.
```

Example: Clipping a brush

1. Select the brush you wish to clip.
2. Say "Clip marker".
3. Place your clipping markers using the right mouse button.
4. Say "Flip marker" if the clipping direction needs to be reversed.
5. Say "Clip selected".
6. Say "Release" to return to normal editing.

Example: Splitting a brush

Follow the same procedure as clipping a brush, but say "Split selected"
instead of "Clip selected". This retains both sections of the brush.

Voice Control does not change the way UnrealEd performs movement or clipping
operations. It simply eliminates the need to manually activate the associated
tools and hold down modifier keys.

## 8. Distance Measurement

Voice Control includes a distance measurement tool that allows you to measure
between two points in your map without creating measurement actors.

### Measurement Commands

```text
"Measure A"       Prepares the first measurement point.
"Measure B"       Prepares the second measurement point.
"Release measure" Clears the measurement markers and display.
```

### Taking A Measurement

1. Say "Measure A".
2. Click the desired starting location in a viewport.
3. Say "Measure B".
4. Click the desired ending location.

Once both points have been placed, the total straight-line distance between
them is automatically calculated and displayed in Unreal units. A green line
connects the two measurement markers for visual reference.

### Working With Measurements

The measurement markers remain in their assigned locations as you pan and
zoom within the viewports.

You can continue editing your map while the measurement remains displayed.
You can also reposition either measurement point by repeating its associated
voice command and clicking a new location.

When finished, say "Release measure" to clear the measurement.

The measurement tool does not add any actors to your map or modify existing
geometry.

## 9. Real-Time Preview

Say "Real time" to simultaneously toggle real-time preview in all four editor
viewports.

Each viewport's current real-time setting is reversed. If a viewport's
real-time preview is enabled, it will be disabled, and vice versa.

There is no need to activate each viewport individually.

## 10. Command Reference

A list of supported voice commands is included in the supplied
SoP_VoiceHotkeys.txt file.

Commands are organized by function, making it easy to locate specific
operations, keyboard shortcuts, brush builders, and their associated property
commands.

We recommend keeping this file available for reference while becoming familiar
with Voice Control.

## 11. Troubleshooting

### Microphone Not Responding

- Make sure your microphone is connected and working.
- Verify that the correct microphone is selected as your default Windows
```text
  recording device.
```
- Check that Windows allows applications to access your microphone.
- Make sure Voice Control is listening and has not been paused.
- Make sure UnrealEd is the active application.

### Commands Are Not Recognized Correctly

- Check your microphone volume and sensitivity.
- Reduce background noise, including music and other conversations.
- Adjust SpeechDelay if commands are being cut off prematurely.
- Check the Last field in the status display to see what was recognized.

If a particular word is consistently misunderstood, create an alias using
the word that Voice Control recognizes.

### Commands Are Recognized But Do Not Work

- Verify that the command is supported and listed in SoP_VoiceHotkeys.txt.
- Check that the assigned keyboard shortcut matches your UnrealEd settings.
- Check for duplicate or conflicting aliases.
- Make sure UnrealEd is the active application when issuing commands.
- When adjusting builder properties, make sure the appropriate properties
```text
  window is active.
```

### Changes To The Text File Are Not Working

- Make sure you have saved SoP_VoiceHotkeys.txt.
- If UnrealEd is running, say "Reload commands".
- Verify that your assignments follow the correct syntax.
- Make sure the assignment is not preceded by a # character.

### Online Recognition Is Unavailable

Voice Control uses online speech recognition as its primary recognition method.
If the online service is unavailable, it can fall back to Windows speech
recognition. Recognition accuracy may differ between the two methods.

### Reporting A Problem

When reporting a problem, please include:

- Your UnrealEd version.
- The command you were attempting to use.
- What you expected to happen.
- What actually happened.
- The corresponding Voice Control log file, if available.

This information will help identify and resolve the problem. Review any logs
for personal information before sharing them publicly.

