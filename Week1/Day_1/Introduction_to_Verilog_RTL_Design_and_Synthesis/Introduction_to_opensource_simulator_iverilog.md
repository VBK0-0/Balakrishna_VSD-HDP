## Introduction to iverilog design, design and test bench:
---------------------------------------------------------------------------------------------------------------------------
- *Simulator:*
   - RTL design is checked for adherence to the specifications by simulating the design.
   - Simulator is the tool used for simulating the design.
     - iverilog is the tool used for this course.

- *Design:*
  - Design is the actual verilog code or set of verilog codes which has the intended functionality to meet with the required
    specifications.

- *Testbench:*
  - Testbench is the setup to apply stimulus(test_vectors) to the design to check its functionality.

- *How simulator works:*
  - Simulator looks for the changes on the input signals.
  - Upon change to the input the output is evaluated.
    - If no change to the input, no change to the output!
  - Simulator is looking for change in the values of input!
  <p align="center">
  <img src="https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Task2/Assets/Yosys_installed.png" 
       alt="Test Bench" width="600"/>
  </p>

- *NOTE:*
  - Design may have 1 or more primary inputs, 1 or more primary outputs.
  - TB doesn't have a primary input or primary outputs.
-  *Iverilog based simulation flow:*
  <p align="center">
  <img src="https://github.com/VBK0-0/Balakrishna_VSD-HDP/blob/main/Week1/Task2/Assets/Yosys_installed.png" 
       alt="Test Bench" width="600"/>
  </p>
