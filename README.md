# POTENTIOMETRIC DIGITAL-TO-ANALOG CONVERTER
The project aims to design a 10-bit Potentiometric Digital to Analog Converter using end-to-end Open-source EDA tools.
The target is to design 10-bit potentiometric DAC with 3.3v analog voltage, 1.8v digital voltage and 1 off-chip external voltage reference using sky130nm technology node.
## Table of Content
- 1.Purpose of Digital to Analog Converter (DAC)
- 2.IP Block Design Specifications
- 3.EDA tools used to implement Potentiometric DAC
-	4.New Implementation of 10Bit Potentiometric DAC
-	5.Conventional Implementation of 10Bit Potentiometric DAC
-	6.Pre-layout Designs and Simulations (Conventional Implementation)
    -	Switch design
    -	2-Bit DAC design and simulation
    -	3-Bit DAC design and simulation
    -	4-Bit DAC design and simulation
    -	5-Bit DAC design and simulation
    -	6-Bit DAC design and simulation
    -	7-Bit DAC design and simulation
    -	8-Bit DAC design and simulation
    -	9-Bit DAC design and simulation
    -	10-Bit DAC design and simulation
    -	INL and DNL Waveforms
-	7.Post-Layout Designs and Simulations (Conventional Implementation)
    -   Resistor 250 layout and value
    -   Resistor 500 layout and value
    -   Inverter layout
    -   Switch layout and simulation
    -	2-Bit DAC layout and simulation
    -	3-Bit DAC layout and simulation
    -	4-Bit DAC layout and simulation
    -	5-Bit DAC layout and simulation
    -	6-Bit DAC layout and simulation
    -	7-Bit DAC layout and simulation
    -	8-Bit DAC layout and simulation
    -	9-Bit DAC layout and simulation
    -	10-Bit DAC layout and simulation
-	8.Instructions to get started with the design
    -	Spice simulation speed improvement (Multi-threading)
    -	Pre-layout Simulation commands
    -	Post-layout Simulation commands
-	9.Future Works
-	10.Contributors

## 1.Purpose of Digital to Analog Converter (DAC)
In real world, most of the data available is in the form of analog in nature. We have two types of converters analog to digital converter and digital to analog converter. These two converting interfaces are essential to obtain the required operations of a processor to manipulate the data of digital electronic equipment and an analog electric equipment. 
Digital to Analog Converter (DAC) is a device that transforms digital data into an analog signal in order to interact with the real world. The digital signal is represented with a binary code, which is a combination of bits 0???s and 1???s. The digital data can be produced from a microprocessor, Field Programmable Gate Array (FPGA), or Application Specified Integrated Circuit (ASIC). There are two commonly used DAC conversions ??? Weighed resistors method and R-2R ladder network method. 
Applications of a DAC: audio amplifier, video encoder, display electronics, data acquisition systems, calibration, Digital potentiometer.

## 2.IP Block Design Specifications

### IP Block Diagram
![avsdDAC3v3](https://user-images.githubusercontent.com/73480418/109257152-7deed980-77c5-11eb-888c-805d33d2b3dc.PNG)


### Terminal Functions
|Name	   |Pin No. |	I/O |	Description       |
|:-------|:-------|:----|:------------------|
|D [0:9] |1-10	  |I	  |Digital inputs     |
|EN	     |11	    |I	  |Enable pin|
|VDD	   |12	    |I  	|Digital power supply (1.8)|
|VSS	|13	|I	|Digital ground|
|OUT	|14	|O	|DAC analog voltage output|
|VDDA	|15	|I	|Analog voltage supply (3.3)|
|VSSA	|16	|I	|Analog ground|
|VREFH	|17	|I	|Reference voltage high for DAC(3.3)|
|VREFL	|18	|I	|Reference voltage low for DAC|
 
## 3.EDA tools used to implement Potentiometric DAC
The design has been built using open-source EDA tools. The library used is sky130.
This design is implemented using [xschem](https://xschem.sourceforge.io/stefan/index.html), and [ngspice](http://ngspice.sourceforge.net/download.html) is used to run the simulations & verify the circuitry. For circuit layout implementation, [Magic](http://opencircuitdesign.com/magic/) will be used. 
The step to install xschem with sky130 and ngspice can be found [here](https://github.com/bluecmd/learn-sky130/blob/main/schematic/xschem/getting-started.md#installation-of-xschem).

## 4.New_Implementation of 10Bit DAC

This project is design of 10-bit Potentiometric DAC with Sky-130 PDK
The novel design for 10bit DAC with reduced number of resistors and switches is proposed. 
The conventional DAC has 1024 resistors, but the proposed DAC requires only 94 resistors.
The conventional DAC has 1024 swithces, but the proposed DAC requires only 96 switches.
For whole design, we will use 1172 transistors. 
So, the proposed design could be an efficient alternative for Higher bit DACs and this 10-Bit Potentiometric implementation designs can be found [here](https://github.com/deepsita/P-DAC_INTERNSHIP/tree/main/ProjectDesigns).

The complete design of the proposed DAC is given in the [proposed_dac.pdf](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/proposed_dac.pdf). 

### Designs and waveforms
*Switch Design and its waveform*
![Switch Circuit](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/ProjectDesigns/Switch/Switch%20Circuit.png)

![Switch Waveform](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/ProjectDesigns/Switch/Switch_new_1.png)

To see this waveform run `Switch_new_1.spice` file

*5Bit AND gate Design and its waveform*
![5Bit AND gate Waveform](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/ProjectDesigns/5BitAND/5Bit%20AND%20Circuit.png)

![5Bit AND gate Waveform](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/ProjectDesigns/5BitAND/Sim_5bitAND_sym.png)

To see this waveform run `Sim_5bitAND_sym.spice` file

*Switch and 5Bit AND gate Design and its waveform*
![Switch and 5bit AND gate circuit](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/ProjectDesigns/Switch_and_5BITAND/Switch_and_5Bit_AND%20circuit.png)


![Switch and 5Bit AND gate Waveform](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/ProjectDesigns/Switch_and_5BITAND/Sim_Switch_plus_5bit_AND_final.png)

To see this waveform run `Sim_Switch_pulse_5Bit_AND_final.spice` file

*10Bit DAC Design*

![10Bit DAC Desing](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/ProjectDesigns/10bitDAC/10Bit_DAC%20design.png)


To test this design 10Bit_DAC_design_1_vref_3.3.spice file can be excecuted.

The challenge in this DAC design was to obtain the required voltage level. The practical implementation and simulation [resulted in lower voltage levels](https://github.com/deepsita/P-DAC_INTERNSHIP/blob/main/ProjectDesigns/spicefiles/output_msbr1_lsbr32).

<!--![2 stage potentiometric DAC](https://user-images.githubusercontent.com/73480418/109258230-da52f880-77c7-11eb-9be6-f4f74b83ac5e.PNG)-->

<!--*Basic Design of new DAC implementation*-->

 
## 5.Conventional Implementation of 10Bit Potentiometeric DAC
The basic idea is to divide the voltage into N different voltage values in the range of VREFH and VREFL- for an N-Bit DAC. The design used here to achieve this is the simple resistor string DAC which consists of resistors in series. These resistors are then connected to various switches in such a fashion that it routes the exact voltage to the output. The problem of the largeness of the circuit is reduced by building hierarchical subcircuits of 10-Bit potentiometric DAC ??? Switch, 2-bit, 3-bit, 4-bit, 5-bit, 6-bit, 7-bit, 8-bit, 9-bit and 10-bit.

![Conventional DAC](https://user-images.githubusercontent.com/73480418/109262054-e2fafd00-77ce-11eb-91ad-d75cca9803a2.png)


*Basic Architecture of Potentiometric DAC*
## 6.Pre-layout Designs and Simulations (Conventional Implementation)
#### *Switch Design*

Switch design implementation and respective waveform are shown below 

![Switch Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/TG_schematics.PNG)


![Switch waveform](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/switch_outputfinal.png)


To see this waveform run `switch.spice` file

#### *2-Bit DAC design and simulation:*

2Bit DAC is implemented using 3 switch instances. 2-Bit circuitry and waveform are shown bellow


![2Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/2bit_schematic.PNG)


![2Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/2bit_waveform.PNG)


To see this waveform run `my_2bitdac.spice` file

#### *3-Bit DAC design and simulation:*

3Bit DAC is implemented using 2 2-Bit DACs and 1 switch instances. 3-Bit circuitry and waveform are shown bellow

![3Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/3bit_schematic.PNG)

![3Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/3bit_waveform.PNG)

To see this waveform run `my_3bitdac.spice` file

#### *4-Bit DAC design and simulation:*

4Bit DAC is implemented using 2 3-Bit DACs and 1 switch instances. 4-Bit circuitry and waveform are shown bellow

![4Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/4bit_schematic.PNG)

![4Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/4bit_waveform.PNG)

To see this waveform run `my_4bitdac.spice` file

#### *5-Bit DAC design and simulation:*

5Bit DAC is implemented using 2 4-Bit DACs and 1 switch instances. 5-Bit circuitry and waveform are shown bellow

![5Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/5bit_schematics.PNG)

![5Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/5bit_waveform.PNG)


To see this waveform run `my_5bitdac.spice` file

#### *6-Bit DAC design and simulation:*

6Bit DAC is implemented using 2 5-Bit DACs and 1 switch instances. 6-Bit circuitry and waveform are shown bellow

![6Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/6bit_schematics.PNG)

![6Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/6bit_waveform.PNG)



To see this waveform run `my_6bitdac.spice` file

#### *7-Bit DAC design and simulation:*

7Bit DAC is implemented using 2 6-Bit DACs and 1 switch instances. 7-Bit circuitry and waveform are shown bellow
![7Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/7bit_schematics.PNG)

![7Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/7bit_waveform.PNG)


To see this waveform run `my_7bitdac.spice` file

#### *8-Bit DAC design and simulation:*

8Bit DAC is implemented using 2 7-Bit DACs and 1 switch instances. 8-Bit circuitry and waveform are shown bellow

![8Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/8bit_schematics.PNG)

![8Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/8bit_waveform.PNG)

To see this waveform run `my_8bitdac.spice` file

#### *9-Bit DAC design:*
9Bit DAC is implemented using 2 8-Bit DACs and 1 switch instances. 9-Bit circuitry and waveform are shown bellow

![9Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/9bit_schematics.PNG)


![9Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/9bit_waveform.png)


To see the waveform run `my_9bitdac.spice` file. 

#### *10-Bit DAC design:*
10Bit DAC is implemented using 2 9-Bit DACs and 1 switch instances. 10-Bit circuitry and waveform are shown bellow

![10Bit DAC Design](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/10bit_schematics.PNG)


![10Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Schematic_design_files/Pictures/10bit_waveform.png)


To see the wavefrom run `my_10bitdac.spice` file.


Every block of the circuit until 10 bit DAC are tested and spice models until 10 bit dac are included in [specified folders](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/tree/main/10Bit_Potentiometeric_DAC_Conventional_Design/spicefiles).

### INL AND DNL outputs

![](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/spicefiles/DNL_LSB.png)


![](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/spicefiles/INL_LSB.png)



## 7.Post-layout Designs and Simulations (Conventional Implementation)
#### *Resistor 250 layout and value*

![Resistor 250 layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/res250%20layout%20design.PNG)

R = 249.8ohms

#### *Resistor 500 layout and value*

![Resistor 500 layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/res500%20layout%20design.PNG)

R = 497.2ohms

#### *Inverter layout*

Inverter Implementation is shown below

![Inverter Layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/INV%20layout%20design.PNG)


#### *Switch layout and simulation*
Switch layout implementation and its respective waveform are shown below 

![Switch Layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/Switch%20layout%20design.PNG)


![Switch layout waveform](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/switch%20layout%20waveform.png)


To see this waveform run `switch_layout_test.spice` file

#### *2-Bit DAC layout and simulation*
2Bit DAC is implemented using 3 switch instances. 2-Bit layout and waveform are shown bellow


![2Bit DAC Layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/2bitdac%20layout%20design.PNG)


![2Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/2bitdac%20layout%20waveform.png)


To see this waveform run `2bitdac_layout_test.spice` file

#### *3-Bit DAC layout and simulation*
3Bit DAC is implemented using 2 2-Bit DACs and 1 switch instances. 3-Bit layout and waveform are shown bellow

![3bit DAC layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/3bitdac%20layout%20design.PNG)


![3Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/3bitdac%20layout%20waveform.png)


To see the wavefrom run `3bitdac_layout_test.spice` file.

#### *4-Bit DAC layout and simulation*
4Bit DAC is implemented using 2 3-Bit DACs and 1 switch instances. 4-Bit layout and waveform are shown bellow

![4bit DAC layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/4bitdac%20layout%20design.PNG)


![4Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/4bitdac%20layout%20waveform.png)


To see the wavefrom run `4bitdac_layout_test.spice` file.

#### *5-Bit DAC layout and simulation*
5Bit DAC is implemented using 2 4-Bit DACs and 1 switch instances. 5-Bit layout and waveform are shown bellow

![5bit DAC layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/5bitdac%20layout%20design.PNG)

![5Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/5bitdac%20layout%20waveform.png)


To see the wavefrom run `5bitdac_layout_test.spice` file.

#### *6-Bit DAC layout and simulation*
6Bit DAC is implemented using 2 5-Bit DACs and 1 switch instances. 6-Bit layout and waveform are shown bellow

![6bit DAC layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/6bitdac%20layout%20design.PNG)

![6Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/6bitdac%20layout%20waveform.PNG)


To see the wavefrom run `6bitdac_layout_test.spice` file.

#### *7-Bit DAC layout and simulation*
7Bit DAC is implemented using 2 6-Bit DACs and 1 switch instances. 7-Bit layout and waveform are shown bellow

![7bit DAC layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/7bitdac%20layout%20design.PNG)

![7Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/7bitdac%20layout%20waveform.PNG)


To see the wavefrom run `7bitdac_layout_test.spice` file.

#### *8-Bit DAC layout and simulation*
8Bit DAC is implemented using 2 7-Bit DACs and 1 switch instances. 8-Bit layout and waveform are shown bellow

![8bit DAC layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/8bitdac%20layout%20design.PNG)

![8Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/8bitdac%20layout%20waveform.PNG)


To see the wavefrom run `8bitdac_layout_test.spice` file.

#### *9-Bit DAC layout and simulation*
9Bit DAC is implemented using 2 8-Bit DACs and 1 switch instances. 9-Bit layout and waveform are shown bellow

![9bit DAC layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/9bitdac%20layout%20desing.PNG)

![9Bit DAC WaveForm](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/9bitdac%20layout%20waveform.png)


To see the wavefrom run `9bitdac_layout_test.spice` file.

#### *10-Bit DAC layout and simulation*
10Bit DAC is implemented using 2 9-Bit DACs and 1 switch instances. 10-Bit layout and waveform are shown bellow

![10bit DAC layout](https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP/blob/main/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/10bitdac%20layout%20desing.PNG)

![10Bit DAC WaveForm]()


To see the wavefrom run `10bitdac_layout_test.spice` file.


## 8.Instructions to get started with the design
#### Spice simulation speed improvement
 Ngspice provides multithreading options to improve the simulation time. To enable multithreading following steps are to be followed:

 o Install ngspice from tarball
 
 o `sudo apt-get install -y autoconf`

 o `sudo apt-get install -y libtool`
 
 o `tar -zxvf ngspice`
 
 o `cd ngspice`
 
 o `./autogen.sh`
 
 o `./configure --enable-xspice --enable-openmp --disable-debug --with-readline=yes`
 
 o `make clean`
 
 o `make`
 
 o `sudo make install`
  
  Then in the netlist's control section, add the following:
  `set num_threads=4` (or more)

![Multithreading](https://user-images.githubusercontent.com/73480418/110157539-46c88b80-7db6-11eb-894d-096e770abd39.PNG)

However, multithreading option is effective if the major part of the circuit are MOSFETs (BSIM 3V8 or BSIM4V5),since the DAC consits of more number of resistors, multithreading option was not helpful to increase the simulation speed.
#### Pre-layout Simulation commands
o	Clone the git repo with following command

        git clone https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP.git
        

o	The conventional design Spice files are in the path 
                    P-DAC_INTERNSHIP/10Bit_Potentiometeric_DAC_Conventional_Design/spicefiles/

o	The new proposed design Spice files are in the path 
                    P-DAC_INTERNSHIP/ProjectDesigns/spicefiles/

o	The libraries are given the folder 
                    P-DAC_INTERNSHIP/10Bit_Potentiometeric_DAC_Conventional_Design/spicefiles/sky130_fd_pr/

o   Open the terminal from the cloned folder or run bellow command after cloning while in the same path
    
            cd P-DAC_INTERNSHIP/ 

o	Command to simulate .Spice files of conventional design

            cd 10Bit_Potentiometeric_DAC_Conventional_Design/spicefiles/
   
            ngspice my_nbitdac.spice  
    
o	Command to simulate .Spice files of new proposed design

            ngspice ProjectDesigns/spicefiles/<Designname.spice>  

#### Post-layout Simulation commands
o   Clone the git repo with following command (if you haven't cloned for pre-layout simulation)

               git clone https://github.com/Shalini24Kanna/P-DAC_INTERNSHIP.git
         
o	The conventional design Spice files are in the path 
                    P-DAC_INTERNSHIP/10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/  
                    
o   Open the terminal from the cloned folder or run bellow command after cloning while in the same path
    
        cd P-DAC_INTERNSHIP/ 

o	Command to simulate .Spice files of conventional design layout
        
        cd 10Bit_Potentiometeric_DAC_Conventional_Design/Layout_Design_files/
        ngspice nbitdac_layout_test.spice

o type `y` when simulation asks for

## 9.Future Works

Layout simulation of 10Bit Potentiometer DAC and plotting INL & DNL for 10Bit DAC layout. Runtime for layout can be reduced further.
The design for the new implementation can be modify and the results for both designs can be compared


## 10.Contributors

Shalini Kanna, Master of Science in Computer Engineering, University of Massachusetts Lowell, Lowell,MA, USA; Contact: kannashalini97@gmail.com, [LinkedIn](https://www.linkedin.com/in/shalini-kanna/)

Harshitha Basavaraju, PhD Scholar @ University of Bundeswehr, Munich, Germany; Contact: harshithab0707@gmail.com

Skandha Deepsita S, PhD Scholar @ IIITDM Kancheepuram; Contact: skandha.deepsita5@gmail.com, [LinkedIn](linkedin.com/in/skandha-deepsita-sarvepalli-027433ba)

Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com
