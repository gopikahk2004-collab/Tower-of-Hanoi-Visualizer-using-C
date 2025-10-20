Tower-of-Hanoi-Visualizer-using-C
A C-based console application that visualizes the Tower of Hanoi puzzle using stacks and recursion. Demonstrates stack operations, recursive problem-solving, and step-by-step visualization of disk movements.

Tower of Hanoi Visualizer (C Program)

Overview

The Tower of Hanoi Visualizer is a C-based console program that demonstrates the classic Tower of Hanoi puzzle using stacks to represent rods.
It visually shows the movement of disks between rods and displays each intermediate step to help users understand the recursive process behind the puzzle.

Table of Contents

Technologies Used

Prerequisites

Setup and Execution

Project Structure

Program Logic

Usage

Output Example

Contributing

License

Technologies Used

C Language – Core programming language.
Stacks – Implemented using arrays to represent rods.
Recursion – Solves the Tower of Hanoi puzzle step-by-step.
Console I/O – For user interaction and visualization.

Prerequisites

Before running this project, ensure you have:
A C compiler (e.g., GCC, Turbo C, or any IDE like Code::Blocks / VS Code with C extension)
Basic understanding of recursion and stack operations

Setup and Execution

Compile the program:
gcc tower_of_hanoi.c -o tower

Run the program:
./tower

Follow on-screen instructions:

Enter the number of disks (e.g., between 1 and 10)
Watch the program display each step of the solution

Project Structure

TowerOfHanoiVisualizer/

├── tower_of_hanoi.c  

├── README.md  

└── (optional) output.txt 

Program Logic

Stack Structure
Each rod is represented as a stack holding disks.
Disks are integers, with smaller numbers representing smaller disks.
Recursive Algorithm
Move n-1 disks to the auxiliary rod.
Move the largest disk to the destination rod.
Move the n-1 disks from auxiliary to destination.
Visualization
After every move, rods are printed showing current disk arrangement.

Usage

When you run the program, you’ll see something like this:

--- Tower of Hanoi Visualizer ---

Enter number of disks (1-10): 3

Step 1: Move disk 1 from A -> C

Step 2: Move disk 2 from A -> B

Step 3: Move disk 1 from C -> B

Step 4: Move disk 3 from A -> C

...

Puzzle solved successfully!

Contributing

Contributions are welcome!
If you’d like to improve or add features:
Fork the repository
Create a new branch: git checkout -b feature-branch
Commit changes: git commit -m "Added new feature"
Push to your fork and submit a Pull Request

License

This project is licensed under the MIT License.
Feel free to modify, use, and share for learning purposes.
