# VHDL Counter Overflow Bug
This repository demonstrates a common error in VHDL code: integer overflow in a counter without proper range checks. The `buggy_counter.vhdl` file contains the buggy code, while `fixed_counter.vhdl` provides the corrected version.

## Problem
The `buggy_counter` entity uses an `integer` type for the counter.  While it's declared with a range (0 to 15),  VHDL's integer type doesn't inherently prevent overflow. If the counter reaches its maximum value (15) and the clock ticks again, unexpected behavior might occur. The simulation might show a counter value exceeding 15 or some other unpredictable result.

## Solution
The solution involves using a safer approach to handle the counter's upper limit. In `fixed_counter.vhdl`, the solution adds explicit checks to prevent the counter from exceeding its defined range. This solution ensures that the counter wraps around correctly to 0 once it reaches 15, eliminating potential overflow issues.