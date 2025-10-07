## Introduction to Logic Synthesis

Logic synthesis encompasses several key processes:

1. **Translation**: This step transforms HDL code (like Verilog) into an internal representation for further processing.
   
2. **Optimization**: The design is refined to improve area, speed, and power efficiency by simplifying gate structures.

3. **Netlist Generation**: The result is a netlist that details the gates and their interconnections, ready for implementation.

### SYNTHESIS

![synthesis](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/synthesis.png)

### Why different flavors of gate?

<img width="593" alt="Why_different_flavors_of_gate" src="https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Why_different_flavors_of_gate.png">

### Why do we need Slow cells?

![Why_we_need_slow_cells](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Why_we_need_slow_cells.png)

### Faster Cells Vs Slower Cells

<img width="583" alt="faster_cells-vs_slower_cells" src="https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/faster_cells-vs_slower_cells.png">

### Selection of cells

<img width="583" alt="selection_of_cells" src="https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/selection_of_cells.png">

### Synthesis Illustration

<img width="620" alt="Synthesis_illustration" src="https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Synthesis_illustration.png">

## Labs Using Yosys and scl180 PDKs
### steps are:
#### Invoke yosys
      yosys 
      
![1](https://github.com/user-attachments/assets/a2ec47f9-1419-4d55-ae34-d092afa909ee)

#### Read liberty files
     read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1V80.lib
  
![WhatsApp Image 2024-11-01 at 12 01 45 PM](https://github.com/user-attachments/assets/778eda84-c880-40cb-af46-05bdcc060f8c)

#### Read verilog files
     read_verilog good_mux.v
     
![WhatsApp Image 2024-11-01 at 12 01 48 PM](https://github.com/user-attachments/assets/f93cefab-4ade-4fbd-aaeb-3715cd5b7f2d)


#### Run synthesis on top level module
      synth -top good_mux
      
![WhatsApp Image 2024-11-01 at 12 01 47 PM](https://github.com/user-attachments/assets/fc73e5ec-ac01-4baf-b607-44d7f15022b2)

![WhatsApp Image 2024-11-01 at 12 01 46 PM](https://github.com/user-attachments/assets/81e5ee63-1b9b-4794-8aae-f9a8fff24954)

#### logic optimization using ABC algorithm
     abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1V80.lib
     
![WhatsApp Image 2024-11-01 at 12 01 46 PM (2)](https://github.com/user-attachments/assets/b72345ac-dcaf-41dc-8b4e-4d910ac52aa8)

![WhatsApp Image 2024-11-01 at 12 01 46 PM (1)](https://github.com/user-attachments/assets/6b5c2def-0272-4bbe-aa42-2a4dea084b1c)

### Use command to view the design 
![WhatsApp Image 2024-11-01 at 12 01 44 PM](https://github.com/user-attachments/assets/97cfb3e7-d5af-433b-b64d-9e638e47cd9e)

![WhatsApp Image 2024-11-01 at 12 01 45 PM (2)](https://github.com/user-attachments/assets/20286d52-7fd1-40f6-92cc-22618b74c456)


#### Write netlist file
     write_verilog good_mux_netlist.v
     !gvim good_mux_netlist.v
![WhatsApp Image 2024-11-01 at 12 33 22 PM (2)](https://github.com/user-attachments/assets/04704919-72a1-4d81-a7e9-15175ae911c5)

#### Write precise netlist file
     write_verilog -noattr good_mux_netlist.v
     !gvim good_mux_netlist.v
     
![WhatsApp Image 2024-11-01 at 12 01 44 PM (1)](https://github.com/user-attachments/assets/381028c3-3b6d-471a-aaba-4443e23c3705)
