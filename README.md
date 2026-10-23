# AITune Controller

Controller firmware for **AITune**, a music game developed during the Sosho-Sai Hackathon on October 12, 2024.

This repository contains the Arduino controller code. The game itself is not included.

## Hardware and Development Environment

- Arduino Uno
- 5 switches (red, yellow, white, green, and blue)
- 2 potentiometers (left and right)
- PlatformIO with the Arduino framework

## Pin Assignments

| Component | Pin |
| --- | --- |
| Red switch | D2 |
| Yellow switch | D3 |
| White switch | D4 |
| Green switch | D5 |
| Blue switch | D6 |
| Left potentiometer | A0 |
| Right potentiometer | A1 |

The firmware treats HIGH as a pressed switch. Original wiring photos and diagrams are not available; the pin assignments above are based on the source code.

## Serial Communication

The controller sends a line at **115200 bps** when a switch state or a scaled potentiometer value changes.

```text
buttons|left|right
```

- Buttons: comma-separated letters (`R`, `Y`, `W`, `G`, `B`), or `NONE` when no switches are pressed.
- Left and right: potentiometer readings scaled to integers from 0 to 100.

Example:

```text
R,G|42|85
```

## Build and Upload

Open this project in PlatformIO, connect an Arduino Uno, and use **Build** and **Upload** with the `uno` environment.
