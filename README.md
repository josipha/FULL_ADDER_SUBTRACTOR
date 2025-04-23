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

**Procedure**

Write the detailed procedure here

**Program:**

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 

Developed by: V. Anisha

RegisterNumber: 212224040023
*/

FULL ADDER
```
module FAS(a, b, c, sum, carry);
    input a;
    input b;
    input c;
    output sum;
    output carry;
	 reg sum,carry;
	 reg t1,t2,t3;
	 always @ (a or b or c) begin
	 sum = (a^b)^c;
	 t1=a & b;
	 t2=b & c;
	 t3=a & c;
	 carry=(t1 | t2) | t3;
	 end
endmodule

```

FULL SUBTRACTOR
```
module FAS1(a, b, cin, diff, borrow);
    input a;
    input b;
    input cin;
    output diff;
    output borrow;
	 reg t1,t2,t3;
	 reg diff,borrow;
	 reg abar;
	 always @ (a or b or cin) begin
	 abar= ~ a;
	 diff = (a^b)^cin;
	 t1=abar & b;
	 t2=b & cin;
	 t3=cin & abar;
	 borrow=(t1 | t2) | t3;
	 end
	endmodule
```
**RTL Schematic**

![image](https://github.com/user-attachments/assets/229659ff-0db3-44f0-97c1-78254ed7e8a6)

![image](https://github.com/user-attachments/assets/f958d59d-bb1d-41c0-a0e1-174a33947fee)


**Output Timing Waveform**

![image](https://github.com/user-attachments/assets/fbada0d4-5ebb-44b0-a39c-4e03a4549096)

![image](https://github.com/user-attachments/assets/077dcc0f-e182-4daa-b9e7-f57190eb9394)


**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



