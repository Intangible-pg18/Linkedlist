## Singly Linked List-:
* Type declaration-:
---
		       class Node { 
		       public: 
    		       int data; 
    		       Node* next; 
		       }; 
---
* Creation of 3 nodes-:
---
		       include <bits/stdc++.h>
		       using namespace std;
		       
		       class Node { 
		       public: 
    		       int data; 
    		       Node* next; 
		       };
		       
		       int main() {
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
 		        third->next=NULL;
 		        return 0;
		       }
---
* Traversing the Linked List-:
---
		       #include <bits/stdc++.h>
		       using namespace std;
		       
		       class Node { 
		       public: 
    		       int data; 
    		       Node* next; 
               Node(int val) {
                data=val;
                next=NULL;
               }
		       };
		       
		       void printdata(Node* n) {
            while(n!=NULL) {
             cout<<n->data<<endl;
             n=n->next;
            }
           }
           
		       int main() {
 		        head=new Node(1);
 		        second=new Node(2);
 		        third=new Node(3);
            head->next=second;
            second->next=third;
            third->next=NULL;
            printdata(head);
 		        return 0;
		       }
---
* Insertion
---
           #include <bits/stdc++.h> 
           #include <typeinfo>
		       using namespace std; 
		        
		       class Node  
		       {  
		           public: 
		           int data;  
		           Node *next;  
		       };
		       
		       void push_at_head(Node** head_ref, int new_data)  
		       {   
		           Node* new_node = new Node();  
		           new_node->data = new_data;  
		           new_node->next = *head_ref;  
		           *head_ref = new_node;
		       }
		       
		       void push_at_tail(Node** head_ref, int new_data)
		       {
		            Node* new_node = new Node();  
		            new_node->data = new_data;
		            new_node->next=NULL;
		            if(*head_ref == NULL)
		            { *head_ref = new_node;
		               return;
		            }
		            else
		            { Node* last = *head_ref;
		              while (last->next != NULL)   
		               { last = last->next; }
		              last->next = new_node;   
		              return;
		            }
		       }
		       
		       void push_after(Node** head_ref, int new_data, int pos_data)
		       { 
		           Node* new_node = new Node();  
		           new_node->data = new_data;
		           Node* temp= *head_ref;
		           while( temp->data!=pos_data)
		           { temp=temp->next; }
		           new_node->next = temp->next;
		           temp->next = new_node;
		           return;
		       }
		       
		       void push_before(Node** head_ref, int new_data, int pos_data)
		       { 
		           Node* new_node = new Node();  
		           new_node->data = new_data;
		           Node* temp= *head_ref;
		           while( temp->data!=pos_data)
		           {
		             if((temp->next)->data!=pos_data)
		               temp=temp->next; 
		             else
		             break;
		           }
		           new_node->next = temp->next;
		           temp->next = new_node;
		           return;
		       }
		       
		       void display(Node *node)  
		       {  
		           while (node!= NULL)  
		           {  
		               cout<<node->data;  
		               cout<<"->";
		               node = node->next;  
		           }  
		           cout<<"NULL";
		       }
		       
		       int main()
		       { 
		           Node* head = NULL;  
		           push_at_tail(&head, 6);
		           push_at_head(&head, 7);
		           push_at_head(&head, 1);
		           push_after(&head, 8, 7);  
		           push_before(&head, 9, 6);
		           cout<<"Created Linked list is: ";
		           display(head);  
		           return 0;
		       }
---
