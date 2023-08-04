#include<stdio.h>
#include<conio.h>
int stack[100],choice,num,top,x,i;
void push();
void pop();
void display();
void main() {
	top=-1;
	clrscr();
	printf("\nEnter size of stack [MAX=100]:");
	scanf("%d",&num);
	printf("\n\t STACK OPERATION USING ARRAY");
	printf("\n\t----------------------------");
	printf("\n\t1.PUSH\n\t2.POP\n\t3.DISPLAY\n\t4.EXIT");
	do {
		printf("\n\tEnter choice\n\t");
		scanf("%d",&choice);
		switch(choice) {
			case 1: {
				push();
				break;
			} case 2: {
				pop();
				break;
			} case 3: {
				display();
				break;
			} case 4: {
				printf("\n\tEXIT POINT\n\t");
				break;
			} default:{
				printf("\n\tPlease enter a valiud choice (1/2/3/4)");
				break;
			}
		}
	} while (choice !=4);
}
void push() {
	if(top >= num-1)
		printf("\n\tstack is overflow\n\t");
	else {
		printf("\n\tEnter value to be pushed\n\t");
		scanf("%d",&x);
		top++;
		stack[top]=x;
	}
}
void pop() {
	if(top <= -1)
		printf("\n\tstack is underflow\n\t");
	else {
		printf("\n\n The popped element is %d\n\t",stack[top]);
		top--;
	}
}
void display() {
	if (top>=0) {
		for (i=top;i>=0;i--)
			printf("\n\t%d",stack[i]);
		printf("\n\tPress next choice");
	} else {
		printf("\n\tThe stack is empty");
	}
}

