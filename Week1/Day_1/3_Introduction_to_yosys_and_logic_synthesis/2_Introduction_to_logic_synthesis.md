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
      
![yosys](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/yosys.png)

#### Read liberty files
     read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1V80.lib
  
![Read_liberty_files](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Read_liberty_files.png)

#### Read verilog files
     read_verilog good_mux.v
     
![Read_verilog_file](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Read_verilog_file.png)


#### Run synthesis on top level module
      synth -top good_mux
      
![run_synth_on_top_level_module](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/run_synth_on_top_level_module.png)

![]()

#### logic optimization using ABC algorithm
     abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1V80.lib
     
![Logic_optimization_using_ABC_algorithm](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Logic_optimization_using_ABC_algorithm_1.png)

![Reintegrating_ABC_results](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Reintegrating_ABC_results.png)

### Use command to view the design 
![Show_command](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Show_command.png)

![show_design](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/show_design_1.png)


#### Write netlist file
     write_verilog good_mux_netlist.v
     !gvim good_mux_netlist.v
![write_netlist_file](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/write_netlist_file.png)

#### Write precise netlist file
     write_verilog -noattr good_mux_netlist.v
     !gvim good_mux_netlist.v
     
![Write_precise_netlist_file](https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Day_1/3_Introduction_to_yosys_and_logic_synthesis/Assets/Write_precise_netlist_file.png)
