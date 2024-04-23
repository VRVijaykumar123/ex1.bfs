# Ex.No: 12  PLANNING –  MONKEY BANANA PROBLEM
### DATE:13/04/2024

### REGISTER NUMBER : 212221040011

### AIM: 
    To find the sequence of plan for Monkey Banana problem using PDDL Editor.
    
###  ALGORITHM
    Step 1:  Start the program.
    
    Step 2 : Create a domain for Monkey Banana Problem.
    
    Step 3:  Create a domain by specifying predicates.
    
    Step 4: Specify the actions GOTO, CLIMB, PUSH-BOX, GET-KNIFE, GRAB-BANANAS in Monkey Banana problem.
    
    Step 5:   Define a problem for Monkey Banana problem.
    
    Step 6:  Obtain the plan for given problem.
    
    Step 7: Stop the program.
    
### PROGRAM:

    (define (domain monkey)         
    (:requirements :strips) 
    (:constants monkey box knife bananas glass waterfountain) 
    (:predicates (location ?x) 
    (on-floor) 
    (at ?m ?x) 
    (hasknife) 
    (onbox ?x) 
    (hasbananas) 
    (hasglass) 
    (haswater)) 
    ;; movement and climbing 
    (:action GO-TO 
    :parameters (?x ?y) 
    :precondition (and (location ?x) (location ?y) (on-floor) (at monkey ?y)) 
    :effect (and (at monkey ?x) (not (at monkey ?y)))) 
    (:action CLIMB 
    :parameters (?x) 
    :precondition (and (location ?x) (at box ?x) (at monkey ?x)) 
    :effect (and (onbox ?x) (not (on-floor)))) 
    (:action PUSH-BOX 
    :parameters (?x ?y) 
    :precondition (and (location ?x) (location ?y) (at box ?y) (at monkey ?y)  
    (on-floor)) 
    :effect (and (at monkey ?x) (not (at monkey ?y)) 
    (at box ?x)(not (at box ?y)))) 
    ;; getting bananas 
    (:action GET-KNIFE 
    :parameters (?y) 
    :precondition (and (location ?y) (at knife ?y) (at monkey ?y)) 
    :effect (and (hasknife) (not (at knife ?y)))) 
    (:action GRAB-BANANAS 
    :parameters (?y) 
    :precondition (and (location ?y) (hasknife)  
    (at bananas ?y) (onbox ?y)) 
    :effect (hasbananas)) 
    ;; getting water 
    (:action PICKGLASS 
    :parameters (?y) 
    :precondition (and (location ?y) (at glass ?y) (at monkey ?y)) 
    :effect (and (hasglass) (not (at glass ?y)))) 
    (:action GETWATER 
    :parameters (?y) 
    :precondition (and (location ?y) (hasglass) 
    (at waterfountain ?y) 
    (at monkey ?y) 
    (onbox ?y)) 
    :effect (haswater))) 


### INPUT

  ### PROBLEM.PDDL
  
    (define (problem pb1) 
    (:domain monkey) 
    (:objects p1 p2 p3 p4 bananas monkey box knife) 
    (:init (location p1) 
    (location p2) 
    (location p3) 
    (location p4) 
    (at monkey p1) 
    (on-floor) 
    (at box p2) 
    (at bananas p3) 
    (at knife p4) 
    ) 
    (:goal (and (hasbananas))) 
    )
    
### OUTPUT/PLAN:

![Experiment - 12](https://github.com/AKASHBKUMAR/AI_Lab_2023-24/assets/113763258/6cc65bda-a206-4f85-bef4-2a153acbba95)


### RESULT:
    Thus, the plan was found for the initial and goal state of given problem.
