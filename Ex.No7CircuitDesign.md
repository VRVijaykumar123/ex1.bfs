# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE:  19-03-2024                                                                          
### REGISTER NUMBER : 212221040178
### AIM: 
To write a logic program to design a circuit like half adder and half subtractor.
###  Algorithm:
1. Start the Program
2. Design a AND gate logic if both inputs are 1 then output is 1.
3. Design a OR gate logic if any one of input is 1 then output is 1.
4. Design a XOR gate logic if both inputs are different then output is 1.
5. Design a NOT gate logic if input is 0 then output is 1.
6. Design a half adder and half subtractor using the rules.
7. Test the logic.
8. Stop the program.

### Program:

% Define the XOR gate
xor(0, 0, 0).
xor(0, 1, 1).
xor(1, 0, 1).
xor(1, 1, 0).

% Define the AND gate
and(0, 0, 0).
and(0, 1, 0).
and(1, 0, 0).
and(1, 1, 1).

% Define the NOT gate
not(0, 1).
not(1, 0).

% Define the half-subtractor circuit
half_subtractor(A, B, Diff, Borrow) :-
    xor(A, B, Diff),
    not(B, NotB),
    and(A, NotB, Borrow).

% Define the half-adder circuit
half_adder(A, B, Sum, Carry) :-
    xor(A, B, Sum),
    and(A, B, Carry).










### Output:
% halfadder
![image](https://github.com/DrUmaRaniV/AI_Lab_2023-24/assets/133218255/c82b818a-6965-41e9-b548-18b4aef4de78)
%halfsubtractor
![image](https://github.com/DrUmaRaniV/AI_Lab_2023-24/assets/133218255/8add7aa3-a2ae-4bd1-ae29-737eb2a08db1)



### Result:
Thus the truth table of circuit verified sucessfully.
