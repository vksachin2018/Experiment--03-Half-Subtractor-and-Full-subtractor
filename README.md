NAME:GOKUL SACHIN K
# Experiment-03 Implementation of Half subtractor and Full subtractor circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime
Theory
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
# Half Subtractor:

module halfsub(diff,carry,a,b);
input a,b;
output diff,carry;
xor(diff,a,b);
assign carry=(~a)&b;
endmodule

# Full Subtractor:

module fullsub(diff,carry,a,b,c);
input a,b,c;
output diff,carry;
xor(diff,a,b,c);
assign carry= (~a)&c | (~a)&b | (b&c);
endmodule

## Truthtable
![WhatsApp Image 2023-12-20 at 19 24 30_5bf8ee4e](https://github.com/vksachin2018/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/149366019/62f0fe97-b965-4cf7-8197-cd462f0dcafb)
![WhatsApp Image 2023-12-20 at 19 24 30_8fb03e5b](https://github.com/vksachin2018/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/149366019/9326b7dc-5867-40cf-9a9c-5031cf753371)



##  RTL realization
![WhatsApp Image 2023-12-20 at 19 24 04_38a6b520](https://github.com/vksachin2018/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/149366019/fd8a3677-5fc5-4339-8dec-a3012a30186d)
![WhatsApp Image 2023-12-20 at 19 24 06_22372f37](https://github.com/vksachin2018/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/149366019/129349a1-1d73-40d4-9117-0f6f6afb1b36)


## Timing diagram 
![WhatsApp Image 2023-12-20 at 19 24 29_3e6a9e6b](https://github.com/vksachin2018/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/149366019/c8851a09-60fb-4379-b072-7a8a7df61852)
![WhatsApp Image 2023-12-20 at 19 24 29_3f4ea634](https://github.com/vksachin2018/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/149366019/e2ea897e-0331-46a2-9ada-9411a582bfda)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
