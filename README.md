/*Muhammad Daniyal 
Reg#34804 
Lab 9: Advanced Programming 
Introduction: 
I have created a step-by-step algebraic equation evaluator program. The evaluator takes an algebraic equation and checks it for syntax errors. It also solves the equation and shows the steps involved in finding the solution. 
 
How to run my application: 
Run the c++ code given in the attachment. */
<><<><><><><<><><><<><><><CODE<><><><><><><><><><><><><><><><
/*Lab 6
Muhammad Daniyal Reg#34804*/
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include<iostream>
#include<conio.h>
using namespace std;
int top = -1;//THIS INTEGER IS FOR CHECKING STACK
char stack[20];

//FOLLOWING ARE THE FUNCTIONS TO BE USED
void push(char);
void pop();
void top_pop();



//PUSH FUNCTION DEFINED
void push(char a)
{
	stack[top] = a;
	top++;
}

// POP FUNCTION DEFINITION
void pop()
{
	if (top == -1)
	{
		printf("expression is invalid\n");
		exit(0);
	}
	else
	{
		top--;
	}
}


void top_pop()//this function checks  whether the expression is correct by checking the stack size element 'top'
{
	if (top == -1)
		printf("\nExpression is Valid\n");
	else
		printf("\nexpression is invalid\n");
}
int main()
{
	system("Color F6");
	char a[60];
	cout << "Enter the Expression to be Checked\n";
	cin >> a;
	for (int i = 0; a[i] != '\0'; i++)
	{
		switch (a[i]) //SWITCH STATEMENT DETECTS AND RESPONDS TO THE TYPE OF BRACKET ENCOUNTERED 
		{

		case '(':

		{
					push(a[i]);
					break;
		}
		case ')':
		{
					pop();
					break;
		}
		case '{':
		{
					push(a[i]);
					break;
		}
		case '}':

		{
					pop();
					break;
		}
		case '[':

		{
					push(a[i]);
					break;
		}
		case ']':

		{
					pop();
					break;
		}
		}
	}
	top_pop(); //TOP POP FUNCTION IS CALLED TO CHECK WHETHER THE EXPRESSION IS VALID OR NOT.

	getch();
	return 0;
}
