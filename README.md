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



The waveform have been uploaded in file section

- The signals i0 and i1 are the inputs  
- sel is the select line  
- y is the output  

When sel = 0, the output y follows input i0.  
When sel = 1, the output y follows input i1.  

From the waveform, it can be observed that the output correctly switches between i0 and i1 based on the value of sel, confirming the correct working of the multiplexer.
