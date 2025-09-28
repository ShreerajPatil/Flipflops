# Verilog Flip-Flop Implementations

This repository contains Verilog source code for fundamental digital logic circuits. The primary example is a D-type flip-flop, which serves as a basic memory element in digital systems.

This project demonstrates how to write a simple synthesizable module and an accompanying testbench to verify its functionality. It is intended for those learning digital design with Verilog.

## Flip-Flops Implemented
Based on the provided files, the repository structure focuses on documenting different flip-flop types:
*   **SR-Flipflop**
*   **D-Flipflop**
*   **JK-Flipflop**
*   **T-Flipflop**

## File Structure
The project directory is organized to hold explanations for each flip-flop type:
How to Use the Code
---

The files in this repository are provided as templates. To use them in your own projects, you will need to rename the modules to match your file names.

**Design Code**

This is the Verilog code for the D-flipflop.
```
module Code(
input d,
input clk,
output reg q,q_bar);
always @(posedge clk)
begin 
q<=d;
q_bar=~d;
end
endmodule
```
**To Use This Code:**

Replace 'Code' with the name of your Verilog file (e.g., dflipflop).

**Testbench Code**

This is the testbench used to verify the D-flipflop.
```
module Testbench();
    reg clk,d;
    wire q,q_bar;
    Code uut(d,clk,q,q_bar);
    initial
    begin
    clk=0;
    forever #50 clk = ~clk;
    end
    initial begin
    d <= 0;
    #100;
    d <= 1;
    #100;
    d <= 0;
    #100;
    d <= 1;
    #100; $finish;
    end
endmodule
```

**To Use This Testbench:**

Replace Testbench with the name of your testbench file (e.g., tb_dflipflop).

On the line Code dut(d,clk,q,q_bar);, replace Code with the module name from your design file (e.g., dflipflop). This connects the testbench to your converter module.
