# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![Screenshot 2024-05-08 133920](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/923b3087-b308-48d6-aa6f-4bd2e396ee09)


 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![Screenshot 2024-05-08 133926](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/9a79ae28-ae5f-4949-b872-6c7e1865b80c)


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![Screenshot 2024-05-08 133939](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/dd6a5ac8-e795-49f6-8b1b-74c30ba8db56)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![Screenshot 2024-05-08 133944](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/aeebe26f-3fee-47f3-9705-586fc65f375d)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

/* write all the steps invloved */
1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by:N.BHARATH RegisterNumber:212223230030
*/module SRFLIPFLOP(q, q_bar, s,r, clk, reset);//SR Flip Flop Behavioral Level using ‘case’ 
 input s,r,clk, reset;
 output reg q;
 output q_bar;

 always@(posedge clk) begin // for synchronous reset
   if(!reset)       q <= 0;
   else 
 begin
     case({s,r})       
          2'b00: q <= q;		  
       2'b01: q <= 1'b0;
       2'b10: q <= 1'b1;		 
       2'b11: q <= 1'bx;                     
     endcase
   end
 end
 assign q_bar = ~q;
endmodule//


**RTL LOGIC FOR FLIPFLOPS**
![1de](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/84cabfb4-3a2e-4ebe-80e3-9f115b64cc62)


**TIMING DIGRAMS FOR FLIP FLOPS**
![ed2](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/21d97ec3-5dbb-4073-9e00-bc5238d05514)


**RESULTS**
Thus the program to implement a SR flipflop using verilog and validating their functionality using their functional tables is successfully completed.


