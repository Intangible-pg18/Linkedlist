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
	       
	       void printList(Node* head) 
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
 	       printList(head);  
 	       return 0; 
	       } 
