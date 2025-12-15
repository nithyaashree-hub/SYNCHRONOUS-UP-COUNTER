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

1. Open Quartus software and create a new Verilog file. Paste the code and save it.
2. Compile the program to check for errors.
3. Generate the RTL schematic via the RTL Viewer and save the logic diagram.
4. Use the Waveform Editor to assign nodes for clk, rstn, and out.
5. Simulate the design with different clk and rstn combinations to generate the timing diagram, and save the results.


**PROGRAM**
~~~
UP COUNTER:

module day7(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule

DOWN COUNTER:

module day8(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out-1;
end
endmodule 

~~~
Developed by: RegisterNumber:25015924


**RTL LOGIC UP COUNTER**
UP COUNTER:

<img width="1920" height="1080" alt="Screenshot (105)" src="https://github.com/user-attachments/assets/e19ba7b1-ece8-4ddf-a6ec-764dec73105e" />


DOWN COUNTER:
<img width="1920" height="1080" alt="Screenshot (107)" src="https://github.com/user-attachments/assets/fbf7d8b5-ba26-4872-bd72-a63c08fff101" />

**TIMING DIAGRAM FOR IP COUNTER**
UP COUNTER:

<img width="1920" height="1080" alt="Screenshot (106)" src="https://github.com/user-attachments/assets/0a769547-c3e9-4b9d-a06a-1a3317ce0612" />


DOWN COUNTER:
<img width="1920" height="1080" alt="Screenshot (108)" src="https://github.com/user-attachments/assets/1addae8d-10f7-47d3-9f96-0ce59c769ad7" />

**TRUTH TABLE**
<img width="544" height="275" alt="image" src="https://github.com/user-attachments/assets/aa7e290a-8247-4bc3-add3-52e4df77cd97" />


**RESULTS**
Thus the Synchronous 3 bit Up counter and 3 bit Down counter are implemeted and verified.
