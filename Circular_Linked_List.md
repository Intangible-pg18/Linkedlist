* Transversal-:
---
	       #include <bits/stdc++.h>
	       using namespace std;
	       class Node 
	       { 
    	        public:
    	         int data; 
    	         Node* next; 
	       };
	       
	       void printData(Node* head) 
	       { 
   	        Node* temp = head; 
    	        if (head != NULL) 
    	        { 
        	       do
        	       { 
            	        cout << temp->data << " "; 
            	        temp = temp->next; 
        	       } 
        	       while (temp != head); 
    	        } 
	       } 
	       
	       int main() 
	       { 
 	        Node* head = NULL;
 	        Node* second = NULL;
 	        Node* third = NULL;
 	        head=new Node();
 	        second=new Node();
 	        third=new Node();
 	        head->data=1;
 	        head->next=second;
 	        second->data=2;
 	        second->next=third;
 	        third->data=3;
 	        third->next=head; 
 	        printData(head);  
 	        return 0; 
	       } 
---
* Insertion-:
---
#include<bits/stdc++.h>
using namespace std;
 
class Node
{   public:
     int data;
     Node* next;
};
 
void pushToEmpty(Node** last_ref, int data)
{
    if (*last_ref != NULL)
     return;
    Node* temp = new Node();
    temp -> data = data;
    *last_ref = temp;
    temp -> next = *last_ref;
}
 
void pushBegin(Node** last_ref, int data)
{
    if (*last_ref == NULL)
     return pushToEmpty(last_ref, data);
    Node* temp = new Node();
    temp -> data = data;
    temp -> next = (*last_ref) -> next;
    (*last_ref) -> next = temp;
    return;
}
 
void pushEnd(Node** last_ref, int data)
{
    if (*last_ref == NULL)
     return pushToEmpty(last_ref, data);
    Node* temp = new Node();
    temp -> data = data;
    temp -> next = (*last_ref) -> next;
    (*last_ref) -> next = temp;
    *last_ref = temp;
    return;
}
 
void pushAfter(Node** last_ref, int data, int item)
{
    if (*last_ref == NULL)
     return;
    Node* temp; Node* p;
    p = (*last_ref) -> next;
    do
    {
        if (p ->data == item)
        {
            Node* temp = new Node();
            temp -> data = data;
            temp -> next = p -> next;
            p -> next = temp;
 
            if (p == *last_ref)
                *last_ref = temp;
            return;
        }
        p = p -> next;
    }  while(p != (*last_ref) -> next);
    cout << item << " not present in the list." << endl;
    return;
}
 
void display(Node* last)
{
    Node *p;
    if (last == NULL)
    {
        cout << "List is empty." << endl;
        return;
    }
    p = last -> next;
    do
    {
        cout << p -> data << "->";
        p = p -> next;
 
    }
    while(p != last->next);
    cout<<last->next->data;
}

int main()
{
 Node *last = NULL;
 pushToEmpty(&last, 6);
 pushBegin(&last, 4);
 pushBegin(&last, 2);
 pushEnd(&last, 8);
 pushEnd(&last, 12);
 pushAfter(&last, 10, 8);
 display(last);
 return 0;
}
