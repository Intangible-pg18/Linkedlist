* Insertion-:
---
	       #include <bits/stdc++.h>
	       using namespace std;
	       
	       class Node 
	       { 
	           public:
	            int data; 
	            Node* next; 
	            Node* prev; 
	       }; 
	       
	       void push(Node** head_ref, int new_data) 
	       { 
	           Node* new_node = new Node();
	           new_node->data = new_data; 
	           new_node->next = (*head_ref); 
	           new_node->prev = NULL;
	           if ((*head_ref) != NULL) 
	               (*head_ref)->prev = new_node; 
	           (*head_ref) = new_node; 
	       } 
	       
	       void insertAfter(Node** head_ref, int val, int new_data) 
	       {
	           Node* new_node = new Node();
	           new_node->data = new_data;
	           Node* temp=*head_ref;
	           while(temp->data!=val)
	               temp=temp->next;
	           new_node->next = temp->next;
	           new_node->prev = temp;
	           temp->next = new_node;
	           if (new_node->next != NULL) 
	               new_node->next->prev = new_node; 
	       } 
	       
	       void append(Node** head_ref, int new_data) 
	       { 
	           Node* new_node = new Node(); 
	           Node* temp = *head_ref;
	           new_node->data = new_data;
	           new_node->next = NULL;
	           if (*head_ref == NULL)
	           { 
	               new_node->prev = NULL; 
	               *head_ref = new_node; 
	               return; 
	           }
	           while (temp->next != NULL) 
	               temp = temp->next;
	           temp->next = new_node;
	           new_node->prev = temp; 
	           return; 
	       } 
	        
	       void display(Node* node) 
	       {
	           while (node != NULL) 
	           { 
	               cout<<" "<<node->data<<" ";
	               node = node->next; 
	           }    
	       } 
	       
	       int main() 
	       { 
	           Node* head = NULL;
	           append(&head, 6);
	           push(&head, 7);
	           push(&head, 1); 
	           append(&head, 4); 
	           insertAfter(&head,7,8);
	           display(head); 
	           return 0; 
	       } 
---
