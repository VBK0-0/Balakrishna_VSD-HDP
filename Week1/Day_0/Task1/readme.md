*Digital VLSI SoC Design and Planning Flow Summary*
----------------------------------------------------------------------------------------------------
- Stage O0 / O1 – Chip Modeling
- Inputs: GCC (compiler), C-model specifications.
- Outputs: Behavioral model of the chip.
- Testbench: Written in C language.
- Objective: Verify functional specifications at high level.

Stage O2 – RTL Architecture

- Representation: Hardware is modeled as RTL (Verilog).
- Soft copy of hardware created.
- Inputs: Specs from O1.
- Outputs: Verified RTL design against C-model.
- SoC design flow: Begins with processor, peripherals, IPs.

Stage O3 – SoC Integration
- Components Integrated:
- Processor
- Peripherals / IPs
- Gate-level netlist (post-synthesis)
- Synthesized RTL macros
- Analog IPs
- SoC Integration: Brings all blocks together with GPIOs.
- Backend Flow: Floorplanning, placement, CTS (clock tree synthesis), routing → GDSII.
- Verification: DRC (Design Rule Check), LVS (Layout vs Schematic).

Stage O4 – Final SoC Product

- Frequency Range: 100 MHz to 130 MHz.
- Peripherals integrated for functionality.
- Testbench still in C language (valid across all stages).
- Validation: O1 = O2 = O3 = O4 (consistency maintained).
- Applications:
  - iWatch
  - Arduino boards
  - TV panels
  - AC applications

Key Takeaway

The process shows stepwise refinement from high-level specification (C model) 
→ RTL design (Verilog) → SoC integration (with peripherals, macros, IPs) → final silicon-ready chip (GDSII). 

At every stage, testbench remains in C, ensuring equivalence of functionality across the design flow.
