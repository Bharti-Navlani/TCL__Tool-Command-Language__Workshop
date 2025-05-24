# 🔁 TCL__Tool-Command-Language__Workshop

![Screenshot 2025-05-23 230449](https://github.com/user-attachments/assets/f0003b85-de95-4194-8205-3825a6a9e83f)

## 🔍 Workshop Overview
This 10-day hands-on workshop focused on advanced TCL scripting for automation in Synthesis, Physical Design, and STA. Topics included TCL basics, constraints<br> parsing, memory module synthesis using Yosys, and QoR analysis. Designed for students and professionals, the workshop offered practical labs and concluded with an<br> industry-grade certification from VSD.<br>

## 📚 Modules
<summary> <h3> Day 1: Introduction to TCL and VSDSYNTH Toolbox Usage </h3> </summary>
- Introduction<br>
- Sub-Task One: VSDSYNTH Toolbox usage scenarios<br>
<summary> <h3> Day 2: Variable Creation and Processing Constraints from CSV </h3> </summary>
- Sub-Task Two - From CSV to format[1] and SDC - Variable Creation<br>
- Sub-Task Two - From CSV to format[1] and SDC - Processing constraints, CSV<br>
<summary> <h3> Day 3: Processing Clock and Input Constraints </h3> </summary>
-Sub-Task Two - From CSV to format[1] and SDC - Processing clock constraints<br>
-Sub-Task Two - From CSV to format[1] and SDC - Processing input constraints<br>
<summary> <h3> Day 4: Complete Scripting and Yosys Synthesis Introduction </h3> </summary>
-Full script for download and Conclusion<br>
-Introduction to Yosys synthesis tool usage<br>
-Hierarchy check and error handling script creation for Yosys<br>
<summary> <h3> Day 5: Advanced Scripting Techniques and Quality of Results Generation </h3> </summary>
-Synthesis main file scripting and output file editing<br>
-World of 'Procs'<br>
-read_sdc proc - interpret clock generation constraints<br>
-read_sdc proc - interpret IO delays and transition constraints<br>
-Process bussed ports and configuration file creation<br>
-Quality of results (QOR) generation algorithm<br>
-Conclusion<br>

## 📦 Content
### Day 1 Theory 
In this workshop, we are working on a task that involves creating a TCL script-based tool (TCL box). This tool takes a CSV file as input and processes it to generate timing analysis results, as illustrated in the figure below :- 
![1p1](https://github.com/user-attachments/assets/af8aa8a8-873e-4bc8-b48e-b614e05807e9)

The flow to create the TCL toolbox is as below :-
![1p3_1](https://github.com/user-attachments/assets/d308c74e-7b29-42e3-874e-dc13301d9317)
[Subtask] is to pass the following csv file as input 
![1p4](https://github.com/user-attachments/assets/70aa13e3-3319-4118-9a94-0a90dd18b3d3)
[Subtask] Convert csv to format[1] (which is input1 to yosys)
![1p6](https://github.com/user-attachments/assets/28baaa98-b01d-4cc8-9192-56fd0495c673)
[Subtask] Convert design constraint file to sdc (which is input2 to yosys)
![1p8](https://github.com/user-attachments/assets/7cbd1f6c-0425-40b1-bee2-0f398e0e3ad1)
[SubTask] Convert the previous outputs to format[2] (which is input to timing tool)
![1p10](https://github.com/user-attachments/assets/ecfd162a-ab0f-41cf-b136-d3a3abed563f)

### Day 1 Lab
Creating a shell script cover which will take the input as csv & pass it to tcl script 
Case 1 : when user doesnt not provide any aruguments 
![1p14](https://github.com/user-attachments/assets/4ff84a39-8553-45f0-80f6-7e44d07b9a40)
![1p15](https://github.com/user-attachments/assets/8851c9a9-e948-491e-90ac-cb0a4876961f)
Case 2 : when user provides the wrong csv file as input 
![1p16](https://github.com/user-attachments/assets/78524af7-3809-43a7-93e0-27d3747923b6)
![1p17](https://github.com/user-attachments/assets/a5d880f0-4da0-4505-9a41-1ac56d855a77)
Case 3 : when user provides correct csv , the csv contents are stored in variables 
![1p18](https://github.com/user-attachments/assets/a2a6995c-f138-414b-a33f-6f928534ff05)
![1p19](https://github.com/user-attachments/assets/bd942bd2-6544-416b-a81d-f4cf4cc7be6b)



