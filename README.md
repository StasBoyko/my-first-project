# my-first-project
my repository where my new works will be stored
this is my job of pop programming with c ++



#include <iostream>
	
#include <cstring>
	
#include <Windows.h>

using namespace std;

struct elememSt
{
	char someData[15];
	
	elememSt* toNext;
};

elememSt* head, * myEl;
	
char newEl[15];
	
char oldEl[15];

void push(char * addEl) 
{
	myEl = new elememSt;
	
	strcpy_s(myEl->someData, newEl);
	
	myEl->toNext = head;
	
	head = myEl;
	
	cout << "\nDone!\n";
}

void vvod(char * text) {
	cout << "\tThis element was on top :";
	
	cout << head->someData << endl;
}

void pop(char* showEl) 
{
	if (head != NULL)
	{
		myEl = head;
	
		strcpy_s(oldEl, head->someData);
	
		head = myEl->toNext;
	
		cout << "\tThis element was on top :";
	
		cout << myEl->someData << endl;
	
		delete myEl;
	}
	else
		cout << "\n\tNo element in stack yet !";
}

int main()
{
	head = NULL;
	
	char choice;
	
	cout << "\t*********************\n";
	
	cout << "\tLet's play with STAK\n";
	
	cout << "\t********************\n";
	

	do
	{
		cout << "\n----------------------------\n";
		cout << "Press 1,2,3,4 to start work : \n";
		cout << "1- add new element\n";
		cout << "2- output last element\n";
		cout << "3- exit\n";
		cout << "4_ pereglad vershin steku\n";
		cout << "----------------------------\n";
		cin >> choice;
		switch (choice)
		{
		case '1': {
			system("cls");
			cout << "\tYour element data(String) : ";
			cin >> newEl;
			push(newEl); break;}


		case '2': {
			system("cls");
			pop(oldEl);break;
		}
		case '3': {
			cout << "\nGood bye))";
			return 0;
		}
		case '4': {
			vvod(newEl);break;
		}
		{
			system("cls");
			cout << "\tMake the right choise!";
		}
		}
	} 	while (choice != '3');
}

