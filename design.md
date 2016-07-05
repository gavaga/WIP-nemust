# Design

This file outlines the design for the NEmuSt emulator. The project is divided into submodules intended to run parallel to the actual hardware.

## cpu

This module emulates the NES's CPU, which is a slightly modified version of the 6502 processor.

### mem

This submodule handles all communication with the CPU's memory map, which involves interfacing with peripherals through various memory maps. These memory maps are constructed separately.

## ppu

This module emulates the NES's Picture Processing Unit, controlled through mapped CPU memory.

### mem

This module emulate's the PPU memory of the NES.

### smem

This module emulates the NES's Sprite Memory, which was 256 bytes of memory specifically for sprites, independent of the CPU memory and the PPU memory.

## apu

This module emulates the Audio Processing of the NES from the CPU memory mapping.

## cart

This module emulates the functionality of the NES cartridge.

## screen

This module handles actually drawing the screen based on the ppu memory name tables and current sprite memory, attempting to emulate the original scanning functionality as closely as possible.

## periph

This module emulates external hardware, including gamepads, the light gun, and any other peripherals.

### input

This module emulates abstract input objects.

### pad

This module emulates the gamepad, providing an API that allows high-level controller-like IO to the CPU.

### gun

This module emulates the NES's light gun.

## config

This module handles static and real-time configuration for the emulator itself.

## common

This module encapsulates abstract structures and behaviours which are not specific to any single module in the program.

## state

This module holds all the information about an entire game state, and includes behaviours for saving and loading such states.
