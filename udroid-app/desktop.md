---
description: Start Linux desktops and apps and configure touch, keyboard, and audio
---

# Desktops, applications, input, and audio

## Start an X11 desktop

1. Install XFCE, Plasma, MATE, or another X11 desktop with the distribution's
   package manager.
2. Return to the installed Linux system page and refresh it.
3. Choose the detected desktop and select **Start**.
4. Select **Display** after the desktop is running.

Use **Desktop compositing** for effects and transparency. Turn it off when a
desktop is slow or shows visual glitches. **Touch-sized interface** makes
desktop controls and the pointer easier to use on a phone.

Leave **Graphics driver** on **Automatic** unless an application needs another
available profile. Compatibility is checked per device, and experimental
profiles may be unstable.

## Linux applications

The **Apps** page lists programs that provide a standard Linux `.desktop`
entry. Install an application inside Linux, refresh the list, then select it to
launch. **Add to home screen** creates an Android launcher shortcut tied to
that application and Linux system.

## Display toolbar

The top toolbar opens the Android keyboard, mouse palette, display buttons
(**Keys**), and desktop settings. Use its arrow to collapse it and tap the
compact handle to restore it.

## Pointer and mouse

Choose a mode under **Desktop settings → Pointer**:

- **Direct:** the pointer follows your finger.
- **Trackpad:** move the pointer relative to your finger for finer control.
- **Native:** send touch points to Linux applications that support touch.

The mouse palette provides left, middle, right, and scroll controls. Tap a
mouse button to latch it and tap again to release it. Hold a button and move a
second finger over the desktop for a temporary press-and-drag. Drag the
palette by its header, or lock its position with **Lock**.

## Keyboard strip and display buttons

The two-row keyboard strip can stay visible while the Android keyboard is
closed. **Keep desktop above keyboard** moves it above the keyboard when the
keyboard opens. Disable **Show keyboard strip** under **Desktop settings →
Keyboard** to reclaim the space.

The strip contains 12 editable slots. A slot can send letters, numbers,
modifiers, arrows, function or navigation keys, supported punctuation, mouse
buttons, or scrolling. **Reset keyboard strip** restores the defaults.

**Keys** shows translucent buttons over the Linux display. Add and edit them
under **Desktop settings → Keyboard**. Choose **Arrange on display**, drag the
buttons into place, then select **Done**. Normal input cannot accidentally move
them.

| Gesture | Result |
| --- | --- |
| Tap | Press and release once. |
| Hold | Keep the key pressed until the finger lifts; multiple holds support chords and WASD diagonals. |
| Double-tap a modifier | Lock Ctrl, Alt, Shift, or Super; tap again to unlock. |

Hiding controls, changing bindings, leaving the display, or losing the
renderer releases held and locked inputs.

## Audio and microphone

**Device speaker** sends Linux audio to Android and is enabled by default.
**Device microphone** is optional and stored per Linux system. Android asks for
permission and shows its privacy indicator while the microphone is active.

Linux applications need PulseAudio-compatible client libraries. If only one
application has no sound, install its distribution's PulseAudio client or
compatibility package.
