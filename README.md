# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure



Write the detailed procedure here 


## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: sentamilsaran S
RegisterNumber: 22008684 
*/
HALF SUBTRACTOR:

module HalfSubtractor(A,B,Diff,Borrow);

input A,B;

output Diff,Borrow;

wire x;

xor (Diff, A,B);

not(x,A);

and(Borrow,x,B);

endmodule

FULL SUBTRACTOR:

module FullSubtractor(A,B,C,Diff,Borrow);

input A,B,C;

output Diff,Borrow;

wire p;

assign Diff = ((A^B)^C);

not(p,A);

assign Borrow = ((p&B)|(p&C)|(B&C));

endmodule

## Output:

## Truthtable
![image](https://user-images.githubusercontent.com/123304969/213918796-6da2e5e7-85f1-43d5-a620-22cf538843cf.png)
![image](https://user-images.githubusercontent.com/123304969/213918811-acd4399c-ea64-4e1e-9df3-1f042daf4647.png)



##  RTL realization
![image](https://user-images.githubusercontent.com/123304969/213918820-c57bb47b-bc4f-4c08-80db-1084f227f22e.png)
![image](https://user-images.githubusercontent.com/123304969/213918827-5fa13e20-f91f-493a-b7d0-3b47d2b7ec36.png)


## Timing diagram 
![image](https://user-images.githubusercontent.com/123304969/213918839-d08ea9c4-d1ef-4621-85c1-5c9746dd8bbd.png)
![image](https://user-images.githubusercontent.com/123304969/213918845-daccbbde-6921-434f-98e5-10af3da88780.png)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
