# PBL-1-Undo-Feature-in-a-Text-Editor
Design an array-based stack that stores user actions (like typed characters or commands). Implement push to record an action and pop to undo it.

**Student Name:** Rafia Sahar


**University:** University of Southern Punjab (USP), Multan


**Subject:** DSA


**Class:** BSCS-P


**Semester:** 3rd


**Roll no:** 63


**Instructor:** Mam Hadia Rehan


## Project Description
This project demonstrates an *Undo Feature* using an *array-based stack* in C++.  
Each user action (typing text or command) is stored in the stack using the *push operation*.
The undo feature removes the most recent action using the *pop operation*.
The stack follows the *LIFO principle*, which makes it suitable for undo functionality.

The PBL implements a simple menu for interaction:

*Menu Options:*
1. Type a character  
2. Undo last character  
3. Display current text  
4. Exit  

This helps understand *stack operations (push and pop)* and how they are applied in real-world applications like text editors.

# Code Implementation

```cpp
#include <iostream>
#include <string>
using namespace std;

#define MAX 50

class Stack {
    string actions[MAX];
    int top;

public:
    Stack() {
        top = -1;
    }

    void push(string action) {
        if (top == MAX - 1) {
            cout << "Action stack is full." << endl;
            return;
        }
        top++;
        actions[top] = action;
        cout << "Action recorded." << endl;
    }

    void pop() {
        if (top == -1) {
            cout << "No action to undo." << endl;
            return;
        }
        cout << "Undoing action: " << actions[top] << endl;
        top--;
    }

    void display() {
        if (top == -1) {
            cout << "No actions performed yet." << endl;
            return;
        }

        cout << "Action History:" << endl;
        for (int i = top; i >= 0; i--) {
            cout << actions[i] << endl;
        }
    }
};

int main() {
    Stack s;
    int choice;
    string action;

    do {
        cout << "\n1. Perform Action";
        cout << "\n2. Undo Last Action";
        cout << "\n3. View Action History";
        cout << "\n4. Exit";
        cout << "\nEnter choice: ";
        cin >> choice;
        cin.ignore();

        switch (choice) {
        case 1:
            cout << "Enter action (word or command): ";
            getline(cin, action);
            s.push(action);
            break;

        case 2:
            s.pop();
            break;

        case 3:
            s.display();
            break;

        case 4:
            cout << "Program ended." << endl;
            break;

        default:
            cout << "Invalid choice." << endl;
        }

    } while (choice != 4);

    return 0;
}
```


## Code Explanation
1-Stores user actions (words/commands) in a stack.


2-Push() records a new action.


3-Pop() undoes the last action.


4-Display() shows all actions from latest to first.

Menu allows: Perform Action → Undo → View History → Exit.
Demonstrates stack operations and the undo feature efficiently.

## Stack & Operations 
-Stack: A data structure that stores items in Last In, First Out (LIFO) order.


-Push: Adds an item to the top of the stack.


-Pop: Removes the most recent item from the stack.
