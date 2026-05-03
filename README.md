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




