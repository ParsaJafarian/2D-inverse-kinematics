# 2D-inverse-kinematics
Simulation of a 2D robotic manipulator's movement using python and inverse kinematics. This was a small project that was designed to assess my learnings in pre-calculus math and python.

# How to run
1. Clone the repository
2. Open `main.ipynb` in vscode or Jupyter notebooks
3. Run `main.ipynb`

## Steps in the project

###  Math
#### Variables
1. arm: manipulator arm
2. xe: x position of the arm's end point
3. ye: y position of the arm's end point
4. l1: length of the first joint of the arm
5. l2: length of the second joint of the arm
6. teta1: angle of l1
7. teta2: angle of l2
8. _1 suffix: part of the first set of the variable
9. _2 suffix: part of the second set of the variable

#### Introduction
The mathematical problem of this project at its core is about finding a function that takes in a position and lengths of arms as input and gives a set of angles as an output.

(l1,l2,xe,ye) => function => (teta1, teta2)

However, the manipulator arm can get to a certain point with two different sets of angles.

f(l1,l2,xe,ye) = (teta1_1, teta2_1) or
f(l1,l2,xe,ye) = (teta1_2, teta2_2)

The function is found via a system of equations that handles vector angles. When representing the arms, trigonometric definition of vectors are then used. The rest will be discussed in following sections.

###  Arm class
#### Definition
The arm class defines the manipulator arm. It takes in l1, l2, xe and ye as paramters in order to use its method of find_angles. The arm class is thus represented fully with all the variables already named (See Math section).

#### Limitations
The arm cannot reach a point that is either to close or too far. The arm can only reach positions with the following range of radius:

l1 - l2 <= r <= l1 + l2

Note that this application did not take into account a situation where the l2 is greater than l1. That is a point to be improved.

### Functions
The following functions are used to show the different actions that can be performed by the arm and visually represented. In the following visualizations, two arms of different colors are shown. These two arms represent the two different paths to the same position.

#### Show Graph
This function uses matplotlib.pyplot and vectors to show the arm at a position given.

#### Show Animation
This function shows the two different paths that the arm takes from its starting position to the end position

#### Draw Circle
This function draws a circle in two different paths as long as the circle is in the right zone

#### Draw Line
This function draws a straight line from one position to another

## Conclusion

### What I learnt
- How to design a basic class
- How to use pyplot
- How to use mathematical operations in code (such as atan2)
- How to structure code into functions
- How to animate a movement

### Next Steps
- Cleaning up code and breaking existing functions into smaller functions
- Make it so that the user can put their input through the console about the end position and arm lengths
- Make new animations such as telling the arm to get from one point to another while avoiding an obstacle that is in the path
