# Subtle Overflow in VHDL Counter

This repository demonstrates a subtle overflow issue in a simple VHDL counter.  The counter is designed to count from 0 to 15, but the reset condition within the `if-else` statement might cause unintended behavior under certain circumstances, particularly in high-frequency or asynchronous designs.

The `buggy_counter.vhd` file contains the erroneous code, while `buggy_counter_solution.vhd` provides a corrected version.

## Issue Description

The main problem is in how the counter resets.  While functionally correct for simple scenarios, the synchronous reset might introduce glitches or metastable states if the reset signal isn't perfectly synchronized with the clock. This can manifest as unpredictable behavior.

## Solution

The solution improves the reset logic to eliminate potential issues.  This might involve using a separate reset signal or modifying the counter logic to handle the reset more robustly.

## How to reproduce

1. Synthesize and simulate the code in `buggy_counter.vhd`.
2. Observe the counter's behavior, particularly focusing on transitions around the maximum count value of 15.
3. Repeat the synthesis and simulation using the corrected code from `buggy_counter_solution.vhd`.
4. Compare the results and observe the differences in behavior.

This example showcases the importance of carefully considering reset conditions in VHDL designs, particularly in timing-critical systems.