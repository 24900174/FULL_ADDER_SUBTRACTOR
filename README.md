# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**
![391812197-26765e12-1448-4442-8b42-e173735db3e5](https://github.com/user-attachments/assets/b333b4b6-59d0-479d-b7ca-64eee168b7fa)

**Procedure**

Write the detailed procedure here
~~~
**Program:**
module full(A,B,Cin,Bin,Sum,Carry,Diff,Borrow);
input A,B,Cin,Bin;
output Sum,Carry,Diff,Borrow;
assign Sum=A^(B^Cin);
assign Carry=(A&B)|(A&Cin)|(B&Cin);
assign Diff=A^(B^Bin);
assign Borrow=(~A&Bin)|(~A&B)|(B&Bin);
endmodule

module fs(a,b,difference,borrow);
input a,b,bin;
output difference,borrow;
assign difference= ( (a ^ b)^bin);
assign borrow= ( ( ~a & b)| ( bin & (~(a ^ b )));
endmodule

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 
Developed by:prabanjan r
RegisterNumber:24900174
*/
~~~
**RTL Schematic**

![391812005-f0422017-40df-4f51-8b2b-18ebbb9d47ea](https://github.com/user-attachments/assets/504a07b7-09fa-4c47-b435-4bfd247cba4f)

**Output Timing Waveform**
![391812099-d5d06393-4aaa-4ce0-a983-ce784ddbf165](https://github.com/user-attachments/assets/9e4fdd4b-16b5-40ac-9232-8cedfc9fdd29)

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



