---
title: Desktop
layout: home
nav_order: 3
parent: "GUI"
---

# GUI Desktop
This pretty much manages everything that gets drawn on the screen.
Originally written in `C`, rewritten and documented in `C++`.

## How the desktop works
#### [`start_desktop` called] --> [Mouse position reset to (0, 0)] --> [(`vbe_clear_screen` called) Screen cleared (Set to `0x000000ff`)] --> [Starts loop]

What the loop does:
#### [Check for PS/2 Keyboard events (`key_event_t` defined, `ps2_get_key_event` called)] --> [Check for PS/2 Mouse events (`mouse_event_t` defined, `ps2_get_mouse_event` called)] --> [Redraws cursor if mouse has moved, handles button presses, etc]

## `desktop.cpp`

### Includes
Headers included in `desktop.cpp`

- `desktop.h`
- As external "C"
  - `Point.h`
  - `bindraw.h` (For drawing in binary)
  - `../drivers/ps2_keyboard.h`
  - `../drivers/ps2_mouse.h`
  - `../drivers/vbe.h`

### Functions
Functions declared in `desktop.cpp`

- `start_desktop`

## `desktop.h`

### Includes
Headers included in `desktop.h`

- `../drivers/types.h`

### Functions
- `start_desktop`

### Definitions
```h
void start_desktop();
```