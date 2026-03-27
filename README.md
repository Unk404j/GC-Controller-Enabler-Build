# Switch2 Controller Tool (WIP)

Experimental Windows tool for testing **Nintendo Switch 2 controller USB/HID behavior** and optionally emulating an Xbox 360 controller.

> ⚠️ Work in progress.
> Current development is focused on the **Switch 2 Pro Controller over USB**, but the project is still incomplete.

---

## Current Status

This project is currently in a transitional state.

What works to some extent:

* USB initialization
* HID input reading
* live input visualization
* optional Xbox 360 emulation through ViGEm

What is still incomplete or incorrect:

* the UI still uses the **old GameCube layout**
* button mapping is still incomplete
* **Select / Minus / Back is not mapped correctly yet**
* controller-specific abstractions are not implemented
* input scaling and calibration may still be off

---

## Scope

Right now this project is mainly a:

* reverse engineering playground
* HID parsing test tool
* controller mapping prototype

It is **not** a polished end-user tool.

---

## Current Target

Main device currently being tested:

* **Nintendo Switch 2 Pro Controller (USB)**

The project started from a GameCube-controller-oriented fork and parts of that original UI / logic are still present.

---

## How it currently works

Current pipeline:

1. Open USB device
2. Send minimal initialization commands
3. Read input through HID
4. Parse buttons / sticks / triggers using the current assumed layout
5. Show activity in the UI
6. Optionally forward input to a virtual Xbox 360 controller

---

## Known Issues

* UI is still GameCube-based and does not match the current target controller
* Select / Minus / Back is not mapped yet
* some button labels may still reflect the older layout
* HID format assumptions may still be wrong in places
* analog scaling is still experimental
* USB init sequence is likely incomplete
* code structure is still being refactored

---

## Features

* USB init
* HID read loop
* input visualization
* trigger calibration
* Xbox 360 emulation via ViGEm

---

## Requirements

* .NET 8 Desktop Runtime (x64)
* ViGEmBus Driver

---

## Build

```bash
dotnet build WinFormsApp1/WinFormsApp1.csproj -c Release
```

---

## Usage

1. Plug the controller in via USB
2. Click **Connect**
3. Check what is detected in the UI
4. Optionally click **Emulate**

Because the UI and mapping are still in transition, what you see on screen may not fully match the physical controller yet.

---

## Development Notes

This repository is currently focused on:

* validating the Switch 2 Pro USB/HID flow
* fixing button mappings
* replacing the old GameCube UI
* cleaning up the code before adding broader controller support

---

## Dependencies

* HidLibrary
* LibUsbDotNet
* Nefarius.ViGEm.Client

---

## Credits

* Accolith (original project)
* handheldlegend
* Nohzockt

---

## Disclaimer

This project is unfinished and experimental.

Use it for testing, debugging, and reverse engineering — not as a polished controller solution.
