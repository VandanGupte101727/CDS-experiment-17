# CDS-experiment-17
c plus plus and data structures experiment 17

AIM:- To learn and implement singly linked lists.<br>

Software used:- VS code<br>

Theory:-<br>
A Singly Linked List is a linear data structure consisting of nodes, where each node contains two components: data and a pointer to the next node. The first node is called the head, and the last node points to nullptr, marking the end of the list. Singly linked lists support dynamic memory allocation, which means their size can grow or shrink during runtime. Operations such as insertion, deletion, and traversal are common, with time complexity of O(n) for most operations due to sequential access. However, they provide better space efficiency compared to arrays because they do not require contiguous memory.<br>

Code:-<br>
  
    #include <iostream>
    using namespace std;

    struct node 
    {
    int data;     
    node* next;
    };

    node* createnode(int value) 
    {
    node* newnode = new node();  
    newnode->data = value;       
    newnode->next = nullptr; 
    return newnode;
    }


    void insertdata(node*& head, int value) 
    {
    node* newnode = createnode(value);

    if (head == nullptr) 
    {
        head = newnode;
    } 
    
    else 
    {
        node* temp = head;
        while (temp->next != nullptr) 
        {
            temp = temp->next;
        }
        temp->next = newnode;
    }
    }

    void display(node* head) 
    {
    node* temp = head;

    while (temp != nullptr) 
    {
        cout << temp->data << " ";
        temp = temp->next;
    }
    }


    int main() 
    {
    node* head = nullptr;

    insertdata(head, 10);
    insertdata(head, 20);
    insertdata(head, 30);
    insertdata(head, 40);

    cout << "Singly Linked List: ";
    display(head);

    return 0;
    }
