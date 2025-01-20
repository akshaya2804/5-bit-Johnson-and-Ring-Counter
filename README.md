5 BIT JOHNSON AND RING COUNTER

Overview

This Verilog module implements two types of counters:

Johnson Counter: A counter that cycles through a sequence of states by shifting and inverting the feedback.

Ring Counter: A counter that cycles through a sequence of states by shifting a single 1 around the register.

Both counters operate based on the positive edge of the clock (clk_in) or reset (reset_in).

Module Details

Inputs

clk_in: The clock input signal. The counters update their states on the positive edge of this signal.
reset_in: The reset signal. When active, it initializes the counters to their default states.

Outputs

johnson_count (5-bit register): The output state of the Johnson counter.
ring_count (5-bit register): The output state of the Ring counter.

Functional Description

Johnson Counter

Initial State: When reset_in is active, johnson_count is set to 5'b00000.

State Transition: On every positive edge of clk_in, the counter shifts left by one bit, and the inverted MSB (~johnson_count[4]) is fed into the LSB.

Sequence: The counter cycles through a total of 2n states, where n is the number of bits (in this case, 10 states).

Ring Counter

Initial State: When reset_iModule Details

Inputs

clk_in: The clock input signal. The counters update their states on the positive edge of this signal.

reset_in: The reset signal. When active, it initializes the counters to their default states.

Outputs

johnson_count (5-bit register): The output state of the Johnson counter.

ring_count (5-bit register): The output state of the Ring counter.

n is active, ring_count is set to 5'b00001.

State Transition: On every positive edge of clk_in, the counter shifts left by one bit, and the MSB (ring_count[4]) is fed into the LSB.

Sequence: The counter cycles through exactly n states, where n is the number of bits (in this case, 5 states).

Simulation

To simulate this module:

Create a testbench that provides the clk_in and reset_in signals.

Observe the outputs johnson_count and ring_count over several clock cycles.

Verify that:

johnson_count follows the Johnson sequence.

ring_count follows the Ring sequence.

