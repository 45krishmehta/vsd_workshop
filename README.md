# vsd_workshop
This repository documents my work from a 12-hour VLSI workshop by VSD Squadron. It includes Verilog-based digital design (MUX), simulation using iVerilog and GTKWave, and basic synthesis using Yosys, all set up on Oracle VM VirtualBox.
# Multiplexer (MUX)

A multiplexer (MUX) is a digital circuit that selects one input from multiple inputs and forwards it to a single output line based on the select signal.

For a 2:1 multiplexer:
- Inputs: i0, i1  
- Select line: sel  
- Output: y  

When sel = 0 → Output follows i0  
When sel = 1 → Output follows i1  

---

## 2:1 MUX Waveform

-waveform photo has been uploaded as mux_waveform.jpeg
- i0 and i1 are the inputs  
- sel is the select line  
- y is the output  

When sel = 0, output y follows i0.  
When sel = 1, output y follows i1.  

The waveform confirms correct working of the multiplexer.

## Yosys Synthesis (MUX Graph)



- i0 and i1 are the input signals  
- sel is the select line  
- y is the output  

The block labeled `$mux` represents the multiplexer logic inferred by the synthesis tool.  
Inputs A and B correspond to i0 and i1, while S represents the select signal.

This graph shows how the high-level Verilog code is converted into a hardware-level structure.  
It confirms that the design is correctly synthesized into a multiplexer component.

## Verilog Code 


```verilog
module good_mux (input i0, input i1, input sel, output reg y);

always @(*) begin
    if (sel)
        y = i1;
    else
        y = i0;
end



endmodule


## Timing Libraries (.lib)

Timing libraries (.lib files) act like a datasheet for digital circuits. They describe how fast different logic gates operate and how much delay they introduce.

They include:
- Propagation delay of gates  
- Setup and hold times  
- Power consumption  

Synthesis tools use these libraries to map Verilog code into real hardware with accurate timing. Without .lib files, the design would work in simulation but may fail in real hardware.

In simple terms, .lib ensures that the circuit works correctly at real speeds.

---

## Hierarchical vs Flat Synthesis

In hierarchical synthesis, the design is divided into smaller modules. Each module is synthesized separately, making the design easier to understand and debug.

In flat synthesis, all modules are combined into a single block. This allows better optimization and performance but makes debugging more difficult.

- Hierarchical → easier debugging  
- Flat → better optimization  

Both approaches are used depending on design requirements.

---

## Flip-Flops (Synchronous vs Asynchronous Reset)

Flip-flops are memory elements used to store data based on a clock signal.

### Asynchronous Reset



- Reset works immediately, independent of clock  
- Output changes instantly when reset is active  

### Synchronous Reset



- Reset works only on clock edge  
- Output changes only during clock transition  

### Key Difference

- Asynchronous → fast, immediate  
- Synchronous → controlled, stable  

Both types are used based on system design needs.




