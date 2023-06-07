# Exercise-07-Multiplexer-and-De-multiplexer
### AIM: To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”
![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)


Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p


## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.
![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)
Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

 
 
### Procedure
Step 1 Create a project with required entities.

Step 2 Create a module along with respective file name for both Multiplexer and De-multiplexer.

Step 3 Run the module and get the respective RTL outputs.

Step 4 Create university program(VWF) for getting timing diagram.

Step 5 Give the respective inputs for timing diagram and obtain the results.



### PROGRAM 
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: M.A.Vishal
RegisterNumber:  212222230177
*MULTIPLEXER:
```
module multi (s0,s1,a0,a1,a2,a3,y);
input s0,s1,a0,a1,a2,a3;
output y;
wire a,b,c,d,s0bar,s1bar;
not (s0bar,s0);
not (s1bar,s1);
and (a,s0,s1,a3);
and (b,s0bar,s1,a2);
and (c,s0,s1bar,a1);
and (d,s0bar,s1bar,a0); 
or (y,a,b,c,d); 
endmodule
```
DEMULTIPLEXER:
```
module demul(y0,y1,y2,y3,s0,s1,i);
input s0,s1,i;
output y0,y1,y2,y3;
wire sbar,s1bar; 
nor(sbar,s0); 
nor(s1bar,s1);
and(y0,i,sbar,s1);
and(y1,i,sbar,s1bar); 
and(y2,i,s0,s1bar);
and(y3,i,s0,s1);
endmodule
```
### RTL LOGIC  
MULTIPLEXER:

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/e64f19c7-ac15-4bab-b4b4-2c8463c29703)

DEMULTIPLEXER:

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/f8fb36b1-34ed-421d-b6e5-fb69c674666a)



### TIMING DIGRAMS  
MULTIPLXER:

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/08d19e77-a373-4402-a11e-3b0da19a409b)

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/6480a8ec-1cb1-4358-8aca-8543951b5507)

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/aed8dd90-a6ea-41d7-9e67-a4837f59fc98)

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/deac02d1-c02b-4174-9497-8188b0b6e5a9)

DE MULTIPLEXER:

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/b440be3f-e113-4e8d-8f2a-90a1c9416874)


### TRUTH TABLE 
MULTIPLEXER: 

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/1343f4e4-6819-494e-804a-5be100744ce6)

DE MULTIPLEXER:

![image](https://github.com/AdhithyaMR/Exercise-07-Multiplexer-and-De-multiplexer/assets/118834761/03c9b748-fe13-4999-9648-2c7d582e1ba3)

### RESULTS 
Hence the 4 X1 multiplexer and 1X4 de multiplexer has been implemented using verilog and outputs are validated.
