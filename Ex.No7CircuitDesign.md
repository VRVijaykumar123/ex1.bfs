# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE: 19-03-2024                                                                           
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

xor(0, 0, 0).
xor(0, 1, 1).
xor(1, 0, 1).
xor(1, 1, 0).


and(0, 0, 0).
and(0, 1, 0).
and(1, 0, 0).
and(1, 1, 1).


not(0, 1).
not(1, 0).


halfsubtractor(A, B, Diff, Borrow) :-
    xor(A, B, Diff),
    not(B, NotB),
    and(A, NotB, Borrow).


halfadder(A, B, Sum, Carry) :-
    xor(A, B, Sum),
    and(A, B, Carry).




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

### Output for halfadder:
![ai exp7 a ](https://github.com/VRVijaykumar123/ex1.bfs/assets/133218255/8f94b3b6-2a66-44d5-baeb-6489d5829574)

### Output for halfsubtractor:
![image](https://github.com/VRVijaykumar123/ex1.bfs/assets/133218255/adc0a82a-cddf-4d98-bb7c-8ca858639b49)


### Result:
Thus the truth table of circuit verified sucessfully.
