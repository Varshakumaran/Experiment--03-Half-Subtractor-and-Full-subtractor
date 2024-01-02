## Name: varsha.k

## ref number: 23005952
# Experiment 03 Half Subtractor and Full subtractor
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

Use module projname(input,output) to start the Verilog programmming.

Assign inputs and outputs using the word input and output respectively.

Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

Use each output to represnt onre for differnce and the other for borrow.

End the verilog program using keyword endmodule


## Program:
# Half Subtractor:
```
module halfsub(diff,carry,a,b);
input a,b;
output diff,carry;
xor(diff,a,b);
assign carry=(~a)&b;
endmodule
```
# Full Subtractor:
```
module fullsub(diff,carry,a,b,c);
input a,b,c;
output diff,carry;
xor(diff,a,b,c);
assign carry= (~a)&c | (~a)&b | (b&c);
endmodule
```

##  RTL realization:
# Half Subtractor:
![image](https://github.com/Varshakumaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979367/8c437a9c-3b75-4e8e-a870-c3075f79fe25)
# Full Subtractor:
![image](https://github.com/Varshakumaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979367/32e63d12-c9a3-47f4-99dc-0f3c8582c994)

## Timing diagram :
# Half Subtractor:
![image](https://github.com/Varshakumaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979367/359b2164-c964-4993-b942-9b5fbddb732a)
# Full Subtractor:
![image](https://github.com/Varshakumaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979367/1ecd9e1e-4947-4e40-bd9c-a1105eaca3a6)

# Truth Table:
# Half Subtractor:
![image](https://github.com/Varshakumaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979367/10c200f4-c409-475e-808a-a6dad079ae12)
# Full Subtractor:
![image](https://github.com/Varshakumaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144979367/749ea70f-9d3e-4d03-b684-a0a49c23af0b)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
