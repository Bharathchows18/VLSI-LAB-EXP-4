EXP-4

DATE:

             SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

**AIM:**
To simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters using Vivado 2023.2

**APPARATUS REQUIRED:**

vivado 2023

# PROCEDURE:

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.


LOGIC DIAGRAM

 SR FLIPFLOP:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

 VERILOG CODE:
module SR(clk,s,r,rst,q );

input s,r,clk,rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({s,r})

2'b00: q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=1'bx;

endcase

end

end

Endmodule

 Output:
![324238983-769a480e-09db-4c46-a8bb-051af3e0bd15](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/45243aaa-d907-493d-a13f-7443b3bfa287)

 JK FLIPFLOP:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

 VERILOG CODE:

module jk(j,k,clk,rst,Q);

input j,k,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)Q=0;

else

begin

case({j,k})

2'b00:Q=Q;

2'b01:Q=0;

2'b10:Q=1;

2'b11:Q=~Q;

endcase

end

end

Endmodule

 Output:

![324238944-eb5473a7-893b-4808-b86d-ccde2e90c239](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/3312233d-9ae6-4787-b002-fc064731b50f)

 T FLIPFLOP:

![301743290-7a020379-efb1-4104-85ee-439d660baa08](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/5f40064f-7491-4a52-90a0-6762ce891f55)


 VERILOG CODE:

module tff(t,clk,rst,Q);

input t,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else if(t==0)

Q=Q;

else

Q=~Q;

end

Endmodule

 Output:

![324239079-9473331d-cb54-4894-93d3-0c90a0107b8d](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/6ded158f-9696-4b37-b460-c8e9222e601d)

 D FLIPFLOP:

![301743389-dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/92d1bacc-e9e8-40ea-a324-25a474eb0e91)

 VERILOG CODE:

module dff(d,clk,rst,Q);

input d,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else

Q=d;

end

Endmodule

 Output:

![324239126-2178ca23-708b-4534-ab1b-97cdc0f0b5c9](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/2bd11870-e55b-43a9-be17-3df61daf2478)

 COUNTER:

![301743514-a1fc5f68-aafb-49a1-93d2-779529f525fa](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/b4cf50df-a052-4d6d-9bb2-b9aebd771584)

4bit UPDOWN COUNTER

![320184799-63e24e65-fd36-4605-983f-331967760c5d](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/fef31a1b-f55e-4b01-b857-81e635687992)



 VERILOG CODE:

module updown(clk,rst,updown,out);

input clk,rst,updown;

output reg[3:0]out;

always@(posedge clk)

begin

if(rst==1)

out=4'b0000;

else if(updown==1);

out=out-1;

end

endmodule

Output:

![324239202-b43edadc-0aed-461b-ab38-8c77b9c0c3ad](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/93f41368-dfbc-486f-8a47-525af2a5511e)

 MOD 10 COUNER:
 
![320184780-3556b90c-52b2-417d-84ce-472a90963995](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/d18df4cb-a444-41f4-8a5c-8aa247c14e3e)


VERILOG CODE:

module mod(clk,rst,out);

input clk,rst;

output reg[3:0]out;

always @(posedge clk)

begin

if(rst==1 | out==4'b1001)

out=4'b0000;

else

out=out+1;

end

endmodule

 Output:

![324239604-fd98cabb-9ac5-4eac-8f5a-81e29ca44c22](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/df84bdbe-05a1-4a4d-952f-c4e3ac83c89a)

RIPPLE CARRY COUNTER:

![320185341-fe056bd8-8771-4f4e-8b23-7d40e1704e9a](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/e1858e63-5bc4-4d6b-974e-e251d82154d2)

VERILOG CODE

module ripple_carry_counter(q, clk, reset);

output [3:0] q;

input clk, reset;

T_FF tff0(q[0], clk, reset);

T_FF tff1(q[1], q[0], reset);

T_FF tff2(q[2], q[1], reset);

T_FF tff3(q[3], q[2], reset);

endmodule

module T_FF(q, clk, reset);

output q;

input clk, reset;

wire d;

D_FF dff0(q, d, clk, reset);

not n1(d, q);

endmodule

module D_FF(q, d, clk, reset);

output q;

input d, clk, reset;

reg q;

always @(posedge reset or negedge clk)

if (reset)

q = 1'b0;

else

q = d;

endmodule

Output:
![324239671-93954bbc-bb8f-43d1-a6ce-a5092bceadfc](https://github.com/Bharathchows18/VLSI-LAB-EXP-4/assets/161430676/b6fde017-8c0f-4f03-847a-149c86d518e7)


 RESULT:

Thus simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters was succesfully executed and verified.
