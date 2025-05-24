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
### 🧱 [Day 1 Theory]
In this workshop, we are working on a task that involves creating a TCL script-based tool (TCL box). This tool takes a CSV file as input and processes it to generate timing analysis results, as illustrated in the figure below :- 
![1p1](https://github.com/user-attachments/assets/af8aa8a8-873e-4bc8-b48e-b614e05807e9)

The flow to create the TCL toolbox is as below :-<br>
![1p3_1](https://github.com/user-attachments/assets/d308c74e-7b29-42e3-874e-dc13301d9317)

  <li><strong> [Subtask_1] is to pass the following csv file as input</li><br>

  ![1p4](https://github.com/user-attachments/assets/70aa13e3-3319-4118-9a94-0a90dd18b3d3)

  <li><strong> [Subtask_2] Convert csv to format[1] (which is input1 to yosys)</li><br>

  ![1p6](https://github.com/user-attachments/assets/28baaa98-b01d-4cc8-9192-56fd0495c673)

  <li><strong> [Subtask_3] Convert design constraint file to sdc (which is input2 to yosys)</li><br>

  ![1p8](https://github.com/user-attachments/assets/7cbd1f6c-0425-40b1-bee2-0f398e0e3ad1)

  <li><strong> [SubTask_4] Convert the previous outputs to format[2] (which is input to timing tool)</li><br>
  
  ![1p10](https://github.com/user-attachments/assets/ecfd162a-ab0f-41cf-b136-d3a3abed563f)


### 🧱 [Day 1 Labs]

Creating a shell script cover which will take the input as csv & pass it to tcl script<br> 

```
chmod -R 777 Csv2TimeSpec
```

**Case 1** : when user doesnt not provide any aruguments<br> 

![1p14](https://github.com/user-attachments/assets/4ff84a39-8553-45f0-80f6-7e44d07b9a40)
![1p15](https://github.com/user-attachments/assets/8851c9a9-e948-491e-90ac-cb0a4876961f)

**Case 2** : when user provides the wrong csv file as input <br>

![1p16](https://github.com/user-attachments/assets/78524af7-3809-43a7-93e0-27d3747923b6)
![1p17](https://github.com/user-attachments/assets/a5d880f0-4da0-4505-9a41-1ac56d855a77)

**Case 3** : when user provides correct csv , the csv contents are stored in variables<br> 

![1p18](https://github.com/user-attachments/assets/a2a6995c-f138-414b-a33f-6f928534ff05)
![1p19](https://github.com/user-attachments/assets/bd942bd2-6544-416b-a81d-f4cf4cc7be6b)


```
📌 [Quick Notes]
$#argv // this is count of arguments
$argv  // this is variable 
```


### 🧱 [Day 2]

In order to convert all the inputs to format[1] & SDC , following are the sub steps involved :-<br>

![2p6](https://github.com/user-attachments/assets/793e5991-f90a-42ac-9baa-0e63c85fe5c3)

**SubStep 1.1** : Create Variables<br>

![2p7](https://github.com/user-attachments/assets/a5cc9026-0b66-45a2-b6e4-81d0fffe8eb2)

**SubStep 1.1** : Create Variables :: csv2matrix -> matrix2array -> variables created <br>

![2p8](https://github.com/user-attachments/assets/d3ff8cb5-e63d-49ea-b8ec-33d23b94eb6b)
![2p9](https://github.com/user-attachments/assets/22a00ef0-fd85-4424-8d01-92899dd9c148)

**SubStep 1.1** : Create Variables :: get the rows & columns of the csv <br>

![2p10](https://github.com/user-attachments/assets/07d76005-8965-4d04-a6d8-890dcd9d1300)
![2p11](https://github.com/user-attachments/assets/ce81b201-f774-48cd-a170-8cf149e28828)
![2p12](https://github.com/user-attachments/assets/2b54206b-3515-4a77-955e-22e520d52463)
![2p13](https://github.com/user-attachments/assets/f2679705-f550-40eb-84e6-ce5a16bdd881)

**SubStep 1.1** : Create Variables :: variables created <br>

![2p14](https://github.com/user-attachments/assets/7de92d97-08d7-4921-bab8-3e17b92d31e4)

**SubStep 1.1 LAB** : Create Variables :: call the tcl file inside the shell script <br>

![2p15_LAB](https://github.com/user-attachments/assets/e4657c39-f8c1-4329-aac0-ee9abf44bdfb)

**SubStep 1.1 LAB** : Create Variables :: code (as explain in above theory path)  <br>

![2p16_LAB](https://github.com/user-attachments/assets/8f8de2ef-8061-4c35-99ab-d7ef694bca91)

**SubStep 1.1 LAB** : Create Variables :: call the csv file as below  <br>

![2p17_LAB](https://github.com/user-attachments/assets/97565ea7-3479-40e4-8411-793d777c1b7c)

**SubStep 1.1 LAB** : Created Variables <br>

![2p18_LAB](https://github.com/user-attachments/assets/9c3cb694-699f-4a78-9524-25336a572802)

**SubStep 1.2 LAB** : Checking if directories & files exists or not <br>

![2p19](https://github.com/user-attachments/assets/8c8c1ffd-6794-4156-aa4e-11e9ec0b2b89)

**SubStep 1.2 LAB** : Checking for directory o/p <br>

![2p20](https://github.com/user-attachments/assets/05ff9c0e-04bd-4e01-bf03-0a5e8b2bb603)

**SubStep 1.2 LAB** : Checking for file <br>

![2p22](https://github.com/user-attachments/assets/c953e3fc-6a0c-47be-81c8-cfc1ccfc6604)

**SubStep 1.2 LAB** : Code (as explain in above theory path) <br>

![2p23_LAB](https://github.com/user-attachments/assets/cc7fefa8-8351-4902-93ae-7d95fc4243ec)

**SubStep 1.2 LAB** : as we see all files are checked as below <br>

![2p24_LAB](https://github.com/user-attachments/assets/4d966d3e-2296-40ac-a469-19abb29b9de6)

**SubStep 1.2 LAB** : remove the o/p directory <br>

![2p25_LAB](https://github.com/user-attachments/assets/533c850c-6875-4ed2-8e4d-e9f36de1a367)

**SubStep 1.2 LAB** : o/p directory is shows error that it is not present & has been created<br>

![2p26_LAB](https://github.com/user-attachments/assets/1419f542-fc26-4df0-b20b-caec3d0161e2)

**SubStep 1.2 LAB** : modify the csv for negative check<br>

![2p28_LAB](https://github.com/user-attachments/assets/d9c7dc52-0013-43c8-98b1-757415837480)

**SubStep 1.2 LAB** : as we can see , if stdcell is not found then code is existed out <br>

![2p27_LAB](https://github.com/user-attachments/assets/71df21e0-765b-4e8d-8a84-9ada431d20ed)


