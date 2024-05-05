### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**
1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: Prasannalakshmi G
RegisterNumber: 212222240075

```
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```
*/

**RTL LOGIC UP COUNTER**


![326229071-6b246d22-f62d-4320-8cd5-6dc5b5e8f78b](https://github.com/Prasannalakshmiganesan/SYNCHRONOUS-UP-COUNTER/assets/118610231/5507efd9-4e62-41c9-813d-84104089103b)

**TIMING DIAGRAM FOR IP COUNTER**


![326229080-d7147d3f-1592-4030-a02f-052be4ab63fe](https://github.com/Prasannalakshmiganesan/SYNCHRONOUS-UP-COUNTER/assets/118610231/dd88bdf9-5950-4e0b-baa4-e7475708c4f5)

**TRUTH TABLE**


![326229088-1de417dc-e76d-41fe-9582-3b31d2e7d159](https://github.com/Prasannalakshmiganesan/SYNCHRONOUS-UP-COUNTER/assets/118610231/90099ff2-49c5-48b2-9e04-28a4d2058fee)

**RESULTS**
Hence a 4 bit synchronous up counter is implemented correctly
