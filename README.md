# SYNCHRONOUS
# synchronous_counter
# AIM:
To implement 4 bit synchronous up counter and validate functionality.

# SOFTWARE REQUIRED:
Quartus prime

# THEORY
4 bit synchronous UP Counter

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:
<img width="652" height="387" alt="image" src="https://github.com/user-attachments/assets/7c8a05b1-c7aa-4e1a-81e8-0199a2e0cb1c" />
<img width="1068" height="510" alt="image" src="https://github.com/user-attachments/assets/cd3a3cf4-b903-4aea-bb51-0380a483df11" />
Each flip-flop in this circuit will be clocked at exactly the same time. The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.” Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse. Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time. The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed. However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

# Procedure
Open Quartus software and create a new Verilog file. Paste the code and save it. Compile the program to check for errors. Generate the RTL schematic via the RTL Viewer and save the logic diagram. Use the Waveform Editor to assign nodes for clk, rstn, and out. Simulate the design with different clk and rstn combinations to generate the timing diagram, and save the results.

# PROGRAM
```
module synchronous_up_counter (
    input  wire clk,      
    input  wire rst,      
    output reg  [2:0] q   
);

always @(posedge clk) begin
    if (rst)
        q <= 3'b000;     
    else
        q <= q + 1;       
end

endmodule
```
# Developed by: BUSHPIKA C
# RegisterNumber: 25007434
# RTL LOGIC UP COUNTER
<img width="1920" height="1080" alt="Screenshot 2025-12-16 104452" src="https://github.com/user-attachments/assets/9dabecf0-1fb4-4a6b-88d9-b489623165fd" />
# TIMING DIAGRAM FOR IP COUNTER
<img width="1068" height="572" alt="image" src="https://github.com/user-attachments/assets/ae77af88-b0c4-4e39-8f52-ab998a87cebb" />
# TRUTH TABLE
<img width="927" height="477" alt="image" src="https://github.com/user-attachments/assets/8581da37-c3cc-4ee9-be9d-21b37e11b8e5" />
# RESULTS
Thus,Program for flipflops and verified its truth table in quartus using Verilog programming.
