# Terminal 8-bit Adder

A browser-based interactive model of a minimal 8-bit execution flow.

## Overview

This tool simulates a simple computation process where two 8-bit values are loaded, processed through an ALU, and written to an output register.

The execution is broken into explicit micro-steps and visualized in real time.

All logic runs directly in the browser.

## How it works

### 1. Input and load

Two values (0–255) are provided and loaded into internal registers:

- Register A
- Register B

Values are constrained to 8-bit range.

---

### 2. Execution model

The computation is executed as a sequence of discrete micro-steps:

- fetch a → load A into ALU input
- fetch b → load B into ALU input
- exec add → perform addition
- write c → write result to output register
- halt → stop execution

Each step updates internal state and is reflected in the UI.

---

### 3. ALU behavior

The ALU performs:

A + B

Results are handled as 8-bit values:

- If result ≤ 255 → stored directly
- If result > 255 → overflow occurs:
  - carry = 1
  - result wraps modulo 256

---

### 4. State representation

The tool exposes internal state explicitly:

- Registers (A, B, ALU, C)
- Carry flag
- Current step
- Active bus
- Execution log

All values are shown in both decimal and binary form.

---

### 5. Execution modes

- Step → advances one micro-step at a time
- Run → executes full sequence automatically
- Reset → clears state
- Example → loads predefined values

---

## What this is useful for

- Understanding how computation is broken into state transitions
- Visualizing how registers and ALU interact
- Seeing how overflow and carry behave in fixed-width arithmetic
- Moving from abstract arithmetic to actual execution flow

---

## Files

- index.html

## Usage

Open `index.html` in a browser.

Enter two values and execute using step or run.

## Notes

- Values are limited to 8-bit (0–255)
- Overflow is handled using modulo 256 arithmetic
- This is a simplified model intended for visualization

## Status

Experimental
