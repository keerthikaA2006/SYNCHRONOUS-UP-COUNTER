# Ex.11: SYNCHRONOUS-UP-COUNTER
# Date:05.12.2024
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

/* write all the steps invloved */

**PROGRAM**
```
module exp11(out,clk,rstn);
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



/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:keerthika A
RegisterNumber:24900898
*/

**RTL LOGIC UP COUNTER**

![Screenshot 2024-12-06 092040](https://github.com/user-attachments/assets/69f8b758-3b39-486d-aa77-25d0fd0b05ff)

**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot 2024-12-06 092142](https://github.com/user-attachments/assets/bcf30391-c11d-496b-8dc2-8799c9f159b8)


**TRUTH TABLE**

![Screenshot 2024-12-06 092209](https://github.com/user-attachments/assets/2b79c0f1-95ac-433c-b6c0-f32719a8d9fc)

**RESULTS**

The synchronous-up-counter are the output is verified.

