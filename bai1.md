
#include <iostream>

using namespace std;

struct Node {
    int data;
    Node* next;
    Node(int val) {
        data = val;
        next = nullptr;
    }
};

class StackLinkedList {

    Node* topNode; 


    StackLinkedList() {
        topNode = nullptr;
    }

    bool isEmpty() {
        return topNode == nullptr;
    }

    void push(int x) {
        Node* newNode = new Node(x);
        newNode->next = topNode;
        topNode = newNode;
    }

    void pop() {
        if (isEmpty()) {
            cout << "Stack Underflow!\n";
            return;
        }
        Node* temp = topNode;
        topNode = topNode->next;
        delete temp;
    }

    int top() {
        if (isEmpty()) {
            cout << "Stack is empty!\n";
            return -1;
        }
        return topNode->data;
    }
};
