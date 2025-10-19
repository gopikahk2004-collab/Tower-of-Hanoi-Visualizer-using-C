 Tower-of-Hanoi-Visualizer-using-C
A C-based console application that visualizes the Tower of Hanoi puzzle using stacks and recursion. Demonstrates stack operations, recursive problem-solving, and step-by-step visualization of disk movements.

 

#include <stdio.h>
#include <stdlib.h>
#define MAX 10
// Stack structure to represent each rod
typedef struct {
int arr[MAX];
int top;
char name;
} Stack;
// Initialize stack
void init(Stack *s, char name) {
s->top = -1;
s->name = name;
}
// Push element onto stack
void push(Stack *s, int val) {
if (s->top == MAX - 1)
return;
s->arr[++(s->top)] = val;
}
// Pop element from stack
int pop(Stack *s) {
if (s->top == -1)
return -1;
return s->arr[(s->top)--];
}
// Display rods as arrays (for visualization)
void displayRods(Stack A, Stack B, Stack C) {
int i;
printf("\nRod %c: [", A.name);
for (i = A.top; i >= 0; i--) {
printf("%d", A.arr[i]);
if (i > 0) printf(", ");
}
printf("]\nRod %c: [", B.name);
for (i = B.top; i >= 0; i--) {
printf("%d", B.arr[i]);
if (i > 0) printf(", ");
}
printf("]\nRod %c: [", C.name);
for (i = C.top; i >= 0; i--) {
printf("%d", C.arr[i]);
if (i > 0) printf(", ");
}
printf("]\n---------------------------\n");
}
// Recursive Tower of Hanoi function
void towerOfHanoi(int n, Stack *from, Stack *to, Stack *aux,
int *stepCount, Stack *A, Stack *B, Stack *C) {
if (n == 1) {
int disk = pop(from);
push(to, disk);
(*stepCount)++;
printf("Step %d: Move disk %d from %c -> %c\n",
*stepCount, disk, from->name, to->name);
displayRods(*A, *B, *C);
return;
}
towerOfHanoi(n - 1, from, aux, to, stepCount, A, B, C);
int disk = pop(from);
push(to, disk);
(*stepCount)++;
printf("Step %d: Move disk %d from %c -> %c\n",
*stepCount, disk, from->name, to->name);
displayRods(*A, *B, *C);
towerOfHanoi(n - 1, aux, to, from, stepCount, A, B, C);
}
// Function to compute (2^n - 1) without math.h
int powerOfTwoMinusOne(int n) {
int result = 1;
int i;
for (i = 0; i < n; i++) {
result *= 2;
}
return result - 1;
}
int main() {
Stack A, B, C;
init(&A, 'A');
init(&B, 'B');
init(&C, 'C');
int i, n;
printf("--- Tower of Hanoi Visualizer ---\n");
printf("Enter number of disks (1-%d): ", MAX);
scanf("%d", &n);
if (n < 1 || n > MAX) {
printf("Invalid number of disks!\n");
return 0;
}
// Initialize rod A with disks
for (i = n; i >= 1; i--) {
push(&A, i);
}
int stepCount = 0;
printf("\nSolving Tower of Hanoi for %d disks...\n", n);
printf("------------------------------------\n");
towerOfHanoi(n, &A, &C, &B, &stepCount, &A, &B, &C);
printf("\nTotal moves required: %d\n", stepCount);
printf("Expected moves (2^n - 1): %d\n", powerOfTwoMinusOne(n));
printf("------------------------------------\n");
printf("Puzzle solved successfully!\n");
return 0;
}

