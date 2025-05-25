🔁 TCL__Tool-Command-Language__Workshop

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
### 🧱 [Day 1]
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


**Initial Shell Script** : Creating a shell script cover which will take the input as csv & pass it to tcl script<br> 

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

**SubStep 2.1** : Create Variables<br>

![2p7](https://github.com/user-attachments/assets/a5cc9026-0b66-45a2-b6e4-81d0fffe8eb2)

**SubStep 2.1** : Create Variables :: csv2matrix -> matrix2array -> variables created <br>

![2p8](https://github.com/user-attachments/assets/d3ff8cb5-e63d-49ea-b8ec-33d23b94eb6b)
![2p9](https://github.com/user-attachments/assets/22a00ef0-fd85-4424-8d01-92899dd9c148)

**SubStep 2.1** : Create Variables :: get the rows & columns of the csv <br>

![2p10](https://github.com/user-attachments/assets/07d76005-8965-4d04-a6d8-890dcd9d1300)
![2p11](https://github.com/user-attachments/assets/ce81b201-f774-48cd-a170-8cf149e28828)
![2p12](https://github.com/user-attachments/assets/2b54206b-3515-4a77-955e-22e520d52463)
![2p13](https://github.com/user-attachments/assets/f2679705-f550-40eb-84e6-ce5a16bdd881)

**SubStep 2.1** : Create Variables :: variables created <br>

![2p14](https://github.com/user-attachments/assets/7de92d97-08d7-4921-bab8-3e17b92d31e4)

**SubStep 2.1 LAB** : Create Variables :: call the tcl file inside the shell script <br>

![2p15_LAB](https://github.com/user-attachments/assets/e4657c39-f8c1-4329-aac0-ee9abf44bdfb)

**SubStep 2.1 LAB** : Create Variables :: code (as explain in above theory path)  <br>

![2p16_LAB](https://github.com/user-attachments/assets/8f8de2ef-8061-4c35-99ab-d7ef694bca91)

**SubStep 2.1 LAB** : Create Variables :: call the csv file as below  <br>

![2p17_LAB](https://github.com/user-attachments/assets/97565ea7-3479-40e4-8411-793d777c1b7c)

**SubStep 2.1 LAB** : Created Variables <br>

![2p18_LAB](https://github.com/user-attachments/assets/9c3cb694-699f-4a78-9524-25336a572802)

**SubStep 2.2** : Checking if directories & files exists or not <br>

![2p19](https://github.com/user-attachments/assets/8c8c1ffd-6794-4156-aa4e-11e9ec0b2b89)

**SubStep 2.2** : Checking for directory o/p <br>

![2p20](https://github.com/user-attachments/assets/05ff9c0e-04bd-4e01-bf03-0a5e8b2bb603)

**SubStep 2.2** : Checking for file <br>

![2p22](https://github.com/user-attachments/assets/c953e3fc-6a0c-47be-81c8-cfc1ccfc6604)

**SubStep 2.2 LAB** : Code (as explain in above theory path) <br>

![2p23_LAB](https://github.com/user-attachments/assets/cc7fefa8-8351-4902-93ae-7d95fc4243ec)

**SubStep 2.2 LAB** : as we see all files are checked as below <br>

![2p24_LAB](https://github.com/user-attachments/assets/4d966d3e-2296-40ac-a469-19abb29b9de6)

**SubStep 2.2 LAB** : remove the o/p directory <br>

![2p25_LAB](https://github.com/user-attachments/assets/533c850c-6875-4ed2-8e4d-e9f36de1a367)

**SubStep 2.2 LAB** : o/p directory is shows error that it is not present & has been created<br>

![2p26_LAB](https://github.com/user-attachments/assets/1419f542-fc26-4df0-b20b-caec3d0161e2)

**SubStep 2.2 LAB** : modify the csv for negative check<br>

![2p27_LAB](https://github.com/user-attachments/assets/71df21e0-765b-4e8d-8a84-9ada431d20ed)

**SubStep 2.2 LAB** : as we can see , if stdcell is not found then code is existed out <br>

![2p28_LAB](https://github.com/user-attachments/assets/d9c7dc52-0013-43c8-98b1-757415837480)

**SubStep 2.3** : read the constraint file from csv -> sdc <br>

![2p29](https://github.com/user-attachments/assets/552a05d2-0bc3-4292-98f6-a262beb8db06)

**SubStep 2.3** : following task to be done for constraint file from csv -> sdc <br>

![2p30](https://github.com/user-attachments/assets/c105e216-6bc4-4312-96fd-1034d1964502)

**SubStep 2.3** : Getting all the "CLOCK" related variables in the csv <br>

![2p31](https://github.com/user-attachments/assets/b8f5db75-0515-4b30-84f7-9087f5676e2f)

**SubStep 2.3** : Getting all the "INPUTS" related variables in the csv <br>

![2p32](https://github.com/user-attachments/assets/ebdf3475-4390-4b55-8c50-9f3d76c1631b)

**SubStep 2.3** : Getting all the "OUTPUT" related variables in the csv <br>

![2p33](https://github.com/user-attachments/assets/24c868fc-e934-41ab-a172-f5eedf81ae2d)

**SubStep 2.3** : Expected output values <br>

![2p34](https://github.com/user-attachments/assets/16f986cf-720f-4eff-84ea-80bf4e5bfd2c)

**SubStep 2.3 LAB** : code to get "CLOCKS"/"INPUTS"/"OUTPUTS" constraints values <br>

![2p35_LAB](https://github.com/user-attachments/assets/e1822db0-b3d6-42e9-b9ce-1ea6da75c747)

**SubStep 2.3 LAB** : output of the code as expected <br>

![2p36_LAB](https://github.com/user-attachments/assets/e1a4eaf3-7c15-4c9f-a205-bd334873bb3b)

```
📌 [Quick Notes]
package require csv // required package for csv
csv::read2matrix $f m, auto // csv is read to a matrix & stored in "m" & "auto" helps to get quick rows & column as following
set c [ m columns]
set r [ m rows] 

package require struct::matrix  // required package for matrix

m link my_arr // coverts matrix to array 
```

### 🧱 [Day 3]

**SubStep 3.1** : get clock latency & put that in sdc format <br>

![3p1](https://github.com/user-attachments/assets/5a39063d-99bf-40de-a50c-f11383ee7ee5)

**SubStep 3.1** : get location of all clk latency by search between are rectangle then put that in sdc format <br>

![3p2](https://github.com/user-attachments/assets/3b0318fc-07cb-4980-bde3-7f81fc253c88)

**SubStep 3.1** : "search rect" between the clock start & input start - 1 to get all the clock latency <br>

![3p3](https://github.com/user-attachments/assets/bfcabd6c-af64-4f79-a870-e9618aabbfad)
![3p4](https://github.com/user-attachments/assets/e5c8478c-4b20-45cd-89dd-d4f06364b440)
![3p5](https://github.com/user-attachments/assets/d2a1d984-13ee-414a-9689-f56769626e3f)
![3p6](https://github.com/user-attachments/assets/6897f848-0d57-4e52-a393-ed600c24bde8)
![3p7](https://github.com/user-attachments/assets/7ab05cde-0ec1-4f7d-b206-ebb9f788d3da)

**SubStep 3.1** : following is the expected output for clock latency <br>

![3p8](https://github.com/user-attachments/assets/85f60a0d-1870-46f0-a775-d563f9abb8d5)

**SubStep 3.1** : following method is applied to get the waveform required for sdc<br>

![3p9](https://github.com/user-attachments/assets/5934edf8-506c-4b98-81e0-035f3ac6fdf8)

**SubStep 3.1** : following is the expected o/p for 1 of the clock<br>

![3p10](https://github.com/user-attachments/assets/6fb5f542-4723-4b8f-ada7-2e40ca2843f1)

**SubStep 3.1 LAB** : following is the code (as explained in theroy above) <br>

![3p11_LAB](https://github.com/user-attachments/assets/a3f99746-406a-4558-adbd-b50dd72b6b2d)

**SubStep 3.1 LAB** : output as expected <br>

![3p12_LAB](https://github.com/user-attachments/assets/f8c8df91-2a47-424c-ab42-a9893e9af8da)

**SubStep 3.1 LAB** : output as expected in sdc <br>

![3p13_LAB](https://github.com/user-attachments/assets/5fd83591-8b4a-4715-b28c-61f52947d5cf)

**SubStep 3.2 LAB** : similar to clock getting all inputs -> values -> sdc format<br>
                  here we also need to take care if input is bus then we have keep * in sdc for it<br>

![3p14](https://github.com/user-attachments/assets/0c1a4913-78a1-474a-b765-20b42b1689e4)

**SubStep 3.2** : following method is used for "INPUTS" <br>

![3p15](https://github.com/user-attachments/assets/0a8d9771-2248-4b93-af43-99ee4713fcaa)
![3p16](https://github.com/user-attachments/assets/7857cef7-40b3-4151-b3b2-0dc75c09e82c)
![3p17](https://github.com/user-attachments/assets/7bd77f1c-8724-4c50-af8f-64721895be66)

**SubStep 3.2 LAB** : following is the code (as explained in theroy above) <br>

![3p18_LAB](https://github.com/user-attachments/assets/16527eda-9aaa-4a89-a404-40bf931bee41)

**SubStep 3.2 LAB** : output for inputs delays & skew start location <br>

![3p19_LAB](https://github.com/user-attachments/assets/23ef54f7-1aa5-4b81-8552-5e01c12ed666)

**SubStep 3.2 LAB** : code to check if input is bussed or not <br>
                  the input is taken as pattern & searched with keyword "input" then we check<br>
                  if lenght is 3 bit or 2 bits based on which busses or not bussed is decided
                 
![3p20_LAB](https://github.com/user-attachments/assets/10005a52-dbd3-4f06-95e6-e48f53555c43)

**SubStep 3.2 LAB** : following output confirms the working for code as expected<br>

![3p21_LAB](https://github.com/user-attachments/assets/1ce4fdf8-8a9f-4a9f-afe0-a36bc80a580f)

**SubStep 3.2 LAB** : quick check for all bussed inputs <br>

![3p22_LAB](https://github.com/user-attachments/assets/8bbc30a1-6685-4a39-9cc8-214abb7d25ad)

**SubStep 3.2** : getting all input constraints values <br>

![3p23](https://github.com/user-attachments/assets/3920e980-a0b1-4df8-b248-b632c9777726)
![3p24](https://github.com/user-attachments/assets/ad738e1c-fab3-480f-91dc-cf48063974f7)
![3p25](https://github.com/user-attachments/assets/43f1c64d-9a73-4260-872d-c04868f087f1)

**SubStep 3.2 LAB** : code as explained above <br>

![3p26_LAB](https://github.com/user-attachments/assets/b9b48601-8501-4ed3-8690-aeb39d6d818b)

**SubStep 3.2 LAB** : bussed or not checked <br>

![3p27_LAB](https://github.com/user-attachments/assets/4aa80533-95db-433e-8fcb-69ac11ff26f2)

**SubStep 3.2 LAB** : sdc updated for inputs <br>

![3p28_LAB](https://github.com/user-attachments/assets/67cd5806-90a1-4b4f-af79-a7b5e2c500dc)

```
📌 [Quick Notes]
search rect c,r c,r // searches region can be specify like this

expr { } //any math operation can be done in tcl with this

puts -nonewline $file "xyz" //this is use to put the content in a file

lsort -unique // for sorting & unification 
```

### 🧱 [Day 4]

**SubStep 4.1** : getting all output delay start location, code will be similar as we have done for INPUTS <br>

![4p1](https://github.com/user-attachments/assets/3f05fe09-9ea7-4f59-9b6d-7b89a5d943c0)
![4p2](https://github.com/user-attachments/assets/4dc419f0-cfde-4f09-8fa9-c4d16a97d588)

**SubStep 4.1** : following is the script written for same followed by output from the script 

![4p3_LAB](https://github.com/user-attachments/assets/91a896a1-842f-4b9d-89b0-9ce1fdaa8279)
![4p4_LAB](https://github.com/user-attachments/assets/abd04e54-800d-46d8-ab32-71fd692287e5)

**SubStep 4.1** : here we are getting the output from the netlist 

![4p5_LAB](https://github.com/user-attachments/assets/ec0a35c9-3884-425a-9935-80f98b6bcdd3)

**SubStep 4.1** : following shows that if port is found in netlist with "output" then it is taken to further loops other else loop is skipped

![4p6_LAB](https://github.com/user-attachments/assets/49f38522-5db8-47dd-b06d-51c6491e39ef)

**SubStep 4.1** : checking if output is busses & by taking the values from csv - updating the sdc for output constraints 

![4p7_LAB](https://github.com/user-attachments/assets/c3465a7f-1fb1-43fc-aede-f7366a1462f7)

**SubStep 4.1** : following shows output width 

![4p9_LAB](https://github.com/user-attachments/assets/589b3ad4-1a49-4fde-a65c-1a2cbe2ffa30)

**SubStep 4.1** : following is the SDC snapshot for output constraints 

![4p10_LAB](https://github.com/user-attachments/assets/b1c2cec0-df3b-4271-8d88-832be03d02fe)

**SubStep 4.2** : For synthesis of the design , we are using YOSYS tool , for which input is RTL -> YOSYS -> SYN NETLIST 

![4p11](https://github.com/user-attachments/assets/243a8d25-eb69-475a-85bf-02e9a858afc6)

**SubStep 4.2** : following is example of working of memory 

![4p12](https://github.com/user-attachments/assets/15ddbfa2-3b03-4e79-a01a-b1ccaf9beace)
![4p13](https://github.com/user-attachments/assets/39053a3f-356f-4e30-a0b0-e8a83317148b)

**SubStep 4.2** : following is RTL code for memory 

![4p14](https://github.com/user-attachments/assets/7b2621ed-c083-42a4-b12b-651ad117a636)

**SubStep 4.2** : following is example of working of memory while checking with synthesized design 

![4p15](https://github.com/user-attachments/assets/37d0f567-66f6-49c2-99ad-3930f05328a6)
![4p16](https://github.com/user-attachments/assets/2c19d037-0d68-4b8a-873d-4777721f5a76)

**SubStep 4.2** : in order to perform synthesis , all rtl files , std files are given as input to yosys tool as show below :- 

![4p17](https://github.com/user-attachments/assets/bc3474e3-1a9f-47f6-b12c-dbdcd31fbf25)

**SubStep 4.2** : automating the process of creating the above input file required by YOSYS 

![4p18](https://github.com/user-attachments/assets/6f5c89d9-387d-4775-88b3-33b0b6eca444)

**SubStep 4.2** : from previous script , following output is expected :- 

![4p19](https://github.com/user-attachments/assets/22feb8fc-0c39-48e9-b367-bcf624b3d12a)

**SubStep 4.2** : following is guide how we are doing the hierarchy check using "catch" command of tcl :- 

![4p20](https://github.com/user-attachments/assets/cda0c6c9-c60d-468f-bd86-174ae9d9ebec)

**SubStep 4.2** : created input for YOSYS  :- 

![4p21_LAB](https://github.com/user-attachments/assets/24e1c817-172b-4427-a585-76d8adbda34c)

**SubStep 4.2** : after running the script , it PASS !! as error flag is 0 

![4p22_LAB](https://github.com/user-attachments/assets/543e84a8-e271-40eb-a4b0-3d71e2c4867c)

**SubStep 4.2** : to check the script quality , modify one of the RTL file 

![4p23_LAB](https://github.com/user-attachments/assets/3db20f19-d720-49d2-9803-dd318b8b6af0)

**SubStep 4.2** : as we can see check FAILs on modified part , hence script is working fine 

![4p24_LAB](https://github.com/user-attachments/assets/8d8182c5-74cd-4fe9-bd7c-157967b3c6eb)

**SubStep 4.2** : created script to perform hierarchy check :- 

![4p26_LAB](https://github.com/user-attachments/assets/0833225a-2ac9-4194-a2df-039d4f06279d)

**SubStep 4.2** : hierarchy check PASS!! :-

![4p27_LAB](https://github.com/user-attachments/assets/5e728842-2bdf-42b4-8380-9c9fc2881913)

**SubStep 4.2** : to check the script quality , modify one of the RTL file (same as before)

![4p28_LAB](https://github.com/user-attachments/assets/15a784c1-4368-4950-8a8e-c87b0e2614ba)

**SubStep 4.2** : as we can see check hierarchy checks FAILs on modified part , hence script is working fine 

![4p29_LAB](https://github.com/user-attachments/assets/3c3edb10-3632-4abd-ba41-7bc95e87a42a)

**SubStep 4.2** : explaination of automation for input file for YOSYS 

![4p30](https://github.com/user-attachments/assets/fed2d7c3-f62c-429c-814e-8e01bf21f05d)

**SubStep 4.2** : following script is use to run YOSYS for synthesis 

![4p31](https://github.com/user-attachments/assets/1bcb5ba9-ead3-445b-8cae-c818aecdb2b8)

```
📌 [Quick Notes]
catch command // used to check error

exec // inside tcl , if we want to run anything on shell then we can use this 
```


### 🧱 [Day 5]

**SubStep 5.1 LAB** : creating the script for synthesis & running the script (with negative check)

![5p2_LAB](https://github.com/user-attachments/assets/9ba35c72-b804-4ce6-8224-f4e18ad9c74e)
![5p4_LAB](https://github.com/user-attachments/assets/f5cab405-e1b6-4779-b479-14f5a3fac0b9)

**SubStep 5.1 LAB** : after running the synthesis , we can see for missing module hierarchy as well as synthesis FAILs!!

![5p1_LAB](https://github.com/user-attachments/assets/27b44d96-dd64-4a2c-ae61-a156f1b6ff64)

**SubStep 5.1 LAB** : reverted back the original file & then checked synthesis has PASS !!

![5p3_LAB](https://github.com/user-attachments/assets/6e34ae58-6e77-4c1f-b8c3-ae35d18e06c8)

**SubStep 5.2** : following the next target , the o/p of YOSYS tool is refined & with SDC it is given as input to timing tool 

![5p5](https://github.com/user-attachments/assets/68daf283-1ac2-4d96-9e14-cf1aaa5a8c82)

**SubStep 5.2** : following the info & script for refinement of format[1]

![5p6](https://github.com/user-attachments/assets/fa59ab80-563b-4486-810d-6cf1aada826b)
![5p7_LAB](https://github.com/user-attachments/assets/576c5c0a-cb30-4a10-9d51-b3ab8499bc60)

**SubStep 5.2 LAB** : writting the script for refinement 

![5p8_LAB](https://github.com/user-attachments/assets/d381dfc5-c3a9-4853-8acb-ebec93ca28c7)

**SubStep 5.2 LAB** : refinement has been done & final netlist is syn netlist 

![5p9_LAB](https://github.com/user-attachments/assets/c2b61250-4352-412a-9018-63c757f517fb)

**SubStep 5.2 LAB** : in following snapshot , we can see the difference between refined & original netlist 

![5p10_LAB](https://github.com/user-attachments/assets/4b679516-67ea-4ae7-b8bc-5029b2d63d5f)

**SubStep 5.2** : example of proc 

![5p11](https://github.com/user-attachments/assets/52d7aced-4de3-4128-a5c9-59539f0faa3b)

**SubStep 5.2** : example of array 

![5p12](https://github.com/user-attachments/assets/44507efa-4f4e-4e9a-a157-421c3db92140)

**SubStep 5.2** : explaination for set_multi_cpu_usage proc 

![5p13](https://github.com/user-attachments/assets/b04b6ad1-9875-42c5-ac54-ec41ce273d5a)

**SubStep 5.2 LAB** : [PROC] set_multi_cpu_usage proc

![5p14_LAB](https://github.com/user-attachments/assets/3430f1f2-04dc-4f5a-a823-3519ff258e86)

**SubStep 5.2 LAB** : [PROC] Stdout proc 

![5p15_LAB](https://github.com/user-attachments/assets/08376aa3-395a-4cb9-8a74-0f02399d1ac4)

**SubStep 5.2 LAB** : [PROC] read_verilog & read_lib proc 

![5p16_LAB](https://github.com/user-attachments/assets/3db7da75-9223-458a-92d0-e722c063738d)

**SubStep 5.2 LAB** : [PROC] Stdout proc working ... 

![5p17_LAB](https://github.com/user-attachments/assets/f0084177-bbd6-408f-b6b8-55ee940dcf1c)

**SubStep 5.2** : [PROC] read_sdc understanding , it converts the SDC to format which is understood by timing tool 

![5p18](https://github.com/user-attachments/assets/0b956c39-1622-405f-920e-e1324a0b545a)

**SubStep 5.2** : [PROC] read_sdc :: clock - need to get rid of "[ ]" present in sdc 

![5p19](https://github.com/user-attachments/assets/3533e166-eded-4680-8ba5-a38e25e8afe4)

**SubStep 5.2** : [PROC] read_sdc :: clock - getting clock name , period & waveform 

![5p20](https://github.com/user-attachments/assets/b6f47338-8f9d-4614-bd35-87f11cd1e90e)

**SubStep 5.2 LAB** : [PROC] read_sdc :: clock - writing script for removing [] , geting clock name , period & waveform as shown below :- 

![5p21_LAB](https://github.com/user-attachments/assets/bd61ec52-fbed-47e3-ad1e-fb6a85775a01)

**SubStep 5.2** : [PROC] read_sdc :: clock - getting the clock latency 

![5p22](https://github.com/user-attachments/assets/a5ddb506-97e4-4b78-8971-0eaa32d20c7e)

**SubStep 5.2 LAB** : [PROC] read_sdc :: clock - writing script for getting clock latency 

![5p23_LAB](https://github.com/user-attachments/assets/29c83a04-4da4-4de8-90a0-b7636ab10928)

**SubStep 5.2 LAB** : [PROC] read_sdc :: clock - checking for 1st clock 

![5p24_LAB](https://github.com/user-attachments/assets/64e73e01-2315-40a3-8d54-3d21beeca354)

**SubStep 5.2 LAB** : [PROC] read_sdc :: clock - checking for 2nd clock 

![5p25_LAB](https://github.com/user-attachments/assets/afd64a7c-ca29-48b8-b3ad-a664b387944d)

**SubStep 5.2 LAB** : [PROC] read_sdc :: clock - getting the clock transition in similar way 

![5p26_LAB](https://github.com/user-attachments/assets/fc8d22a5-ec01-4aaa-a5ad-55c66b393517)

**SubStep 5.2 LAB** : [PROC] read_sdc :: clock - checking o/p 

![5p27_LAB](https://github.com/user-attachments/assets/cc194a32-8ce5-4d0b-92de-6a350f149a9a)

**SubStep 5.2 LAB** : [PROC] read_sdc :: inputs , similar script is required to get inputs delay & transition 

![5p28](https://github.com/user-attachments/assets/5335b0c8-80c1-45ca-8a05-3c3671ab9e72)

**SubStep 5.2 LAB** : [PROC] read_sdc :: inputs , created similar script for INPUTS 

![5p29_LAB](https://github.com/user-attachments/assets/b6a58d09-9ba8-4268-baa7-35214d01186b)

**SubStep 5.2 LAB** : [PROC] read_sdc :: inputs , checking script o/p created for INPUTS

![5p30_LAB](https://github.com/user-attachments/assets/a46dee92-c46e-407e-a296-3ea2f962ce8f)

**SubStep 5.2 LAB** : [PROC] read_sdc :: outputs , created similar script for OUTPUTS  

![5p33_LAB](https://github.com/user-attachments/assets/23137836-bf56-4b28-b49c-ac72d02ce132)

**SubStep 5.2 LAB** : [PROC] read_sdc :: outputs , checking script o/p created for OUTPUTS

![5p34_LAB](https://github.com/user-attachments/assets/f28355c6-18d5-4ea3-90cd-fa83082f16bf)
![5p35_LAB](https://github.com/user-attachments/assets/491a6612-59b9-40e9-ad44-8c1517731512)

**SubStep 5.2** : [PROC] read_sdc :: bit blasting for all the inputs & outputs we have from sdc to /tmp/3 
this is done with by search for the ports in the final netlist we have 

![5p36](https://github.com/user-attachments/assets/50a85efc-e2f4-476d-be46-3aea3ef98c50)

**SubStep 5.2 LAB** : [PROC] read_sdc :: script for bit blasting 

![5p37_LAB](https://github.com/user-attachments/assets/ace380d4-f681-43c9-81a1-f4cb793e3538)

**SubStep 5.2 LAB** : [PROC] read_sdc :: checking the input & output 

![5p38_LAB](https://github.com/user-attachments/assets/9112b63b-1ac6-4433-80b7-4e54444890df)

**SubStep 5.2 LAB** : [PROC] read_sdc :: checking the format dummped for timing file 

![5p39_LAB](https://github.com/user-attachments/assets/ea431af2-6f0b-4371-8792-37d1932ba552)

**SubStep 5.2 LAB** : generating the spec & conf file required for timing tool with following script 

![5p40_LAB](https://github.com/user-attachments/assets/6115d3a3-e11a-49a0-ad4a-cef4d3db2e75)

**SubStep 5.2 LAB** : review for spec & config file generated 

![5p41_LAB](https://github.com/user-attachments/assets/4b842bc7-f991-4109-8ce6-7116bb54fa83)

**SubStep 5.2 LAB** : script for  [1] running time tool & get the run time , [2] get the worst violation [3] getting no. of violation 

![5p42_LAB](https://github.com/user-attachments/assets/0c5e0c44-e52b-47f1-8a17-c09cf8b6890a)

**SubStep 5.2 LAB** : script for [4] getting the worst setup violation,  [5] getting no. of setup violation [6] getting hold violation 

![5p43_LAB](https://github.com/user-attachments/assets/a82d0d02-10ad-4770-9207-fa7970e75694)

**SubStep 5.2 LAB** : script for [7] getting the no. of hold violation [8] getting the inst count 

![5p44_LAB](https://github.com/user-attachments/assets/3f8a4ede-d305-48fc-91d7-0943cf0f3139)

**SubStep 5.2 LAB** : script to create QOR report veritically & horizontally 

![5p45_LAB](https://github.com/user-attachments/assets/6cbcf11a-f655-407c-ad23-7cbc30be71d3)

**SubStep 5.2 LAB** : FINAL Csv2TimeSpec is performed successfully !! 

![5p46_LAB](https://github.com/user-attachments/assets/b029296b-96ed-4c92-b0af-4b3543cf8475)

```
📌 [Quick Notes]

grep -v -w "*" // print everything removing *

string map <searc> <replace> $line // command to search & replace 

proc // any script which needs to called multiple time can be created as proc

$args - options(-localCpu) // use to sub args in a give input

file dirname $argv // input is file path , this gives the directory name of that file

fail tale $agrv // input is a file path , this gives the file name

```


## 📝 Acknowledgements
I would like to thank Mr. Kunal Ghosh and the VSD (VLSI System Design) team for organizing the TCL workshop and making the learning material accessible in a clear and structured manner. The course offered clear explanations and practical insights that contributed meaningfully to my understanding of the subject.

