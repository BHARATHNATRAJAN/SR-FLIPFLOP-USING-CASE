# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![Screenshot 2024-05-08 133920](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/ee7572d2-ce9c-4dae-a16b-ada0157c71a0)


 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.
![Screenshot 2024-05-08 133926](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/5dd3a740-bbe8-4f97-8b60-b218a883e260)


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![Screenshot 2024-05-08 133939](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/73a54373-7dde-497d-a520-ead2e7c105bb)


 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
![Screenshot 2024-05-08 133944](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/bcfb5cb4-7699-4154-87ba-fb4cdb3415cc)


The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**
~~~
Step 1: Open Quartus II in your laptop.
Step 2: Write code to implement SR flipflop using verilog and validating their functionality using their functional tables.
Step 3: Run compilation to check for errors.
Step 4: Open waveform output and load input values.
Step 5: Run simulation to get the output.
Step 6: Open in RTL viewers to get RTL diagram output.
~~~

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by:N.BHARATH RegisterNumber:232223230030
*/
~~~
module sr_flipflop(q, q_bar, s, r, clk, reset);
  input s, r, clk, reset;
  output reg q;
  output q_bar;

  always @(posedge clk) begin
    if (!reset) 
      q <= 1'b0;
    else begin
      case ({s, r})
        2'b01: q <= 1'b0;
        2'b10: q <= 1'b1;
        2'b11: q <= 1'bx;
        default: q <= q;
      endcase
    end
  end

  assign q_bar = ~q;
endmodule
~~~

*RTL LOGIC FOR FLIPFLOPS**

![Screenshot 2024-05-08 134430](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/00c8d993-5527-412e-8b47-987057643ccb)



**TIMING DIGRAMS FOR FLIP FLOPS**
![Screenshot 2024-05-08 134548](https://github.com/BHARATHNATRAJAN/SR-FLIPFLOP-USING-CASE/assets/147473529/3478fcd8-8af9-4435-b391-a786048e26d2)

           

**RESULTS**

Thus the program to implement a SR flipflop using verilog and validating their functionality using their functional tables is successfully completed
