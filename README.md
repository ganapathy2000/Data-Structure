# Data-Structure
// c pgm to singly linked list//<br>
#include<iostream> <br>
#include<cstdlib> <br>
using namespace std; <br>
struct node <br>
{ <br>
 int info;<br> 
 struct node *next;<br> 
}*start; <br>
class single_llist<br> 
{ <br>
 public:<br> 
 node* create_node(int);<br> 
 void insert_begin(); <br>
 void insert_last(); <br>
 void insert_pos();<br> 
 void delete_begin(); <br>
 void delete_last(); <br>
 void delete_pos(); <br>
 void update_begin(); <br>
 void update_last();<br> 
 void update_pos();<br> 
 void sort(); <br>
 void reverse(); <br>
 void search(); <br>
 void display(); <br>
 single_llist() <br>
 { <br>
 start = NULL;<br> 
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice; <br>
 single_llist sl,s2; <br>
 start = NULL; <br>
 do <br>
 { <br>
 cout<<"---------------------------------"<<endl;<br> 
 cout<<"Operations on singly linked list"<<endl;<br> 
 cout<<"---------------------------------"<<endl; <br>
 cout<<"1.Insert at first"<<endl; <br>
 cout<<"2.Insert at last"<<endl;<br> 
 cout<<"3.Insert at position"<<endl;<br> 
 cout<<"4.Delete at first"<<endl; <br>
 cout<<"5.Delete at Last"<<endl;<br> 
 cout<<"6.Delete at position"<<endl; <br>
 cout<<"7.Update at first"<<endl; <br>
 cout<<"8.Update at last"<<endl; <br>
 cout<<"9.Update at position"<<endl;<br> 
 cout<<"10.Ascending order"<<endl;<br> 
 cout<<"11.Descending order"<<endl; <br>
 cout<<"12.Search"<<endl; <br>
 cout<<"13.Display"<<endl;<br> 
 cout<<"14.Exit "<<endl; <br>
 cout<<"Enter your choice :";<br> 
 cin>>choice; <br>
 switch(choice) <br>
 {<br> 
 case 1: sl.insert_begin(); <br>
 sl.display(); <br>
 break;<br> 
 case 2: sl.insert_last();<br> 
 sl.display(); <br>
 break;<br> 
 case 3: sl.insert_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 4: s2.delete_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 5: s2.delete_last(); <br>
 sl.display(); <br>
 break; <br>
 case 6: sl.delete_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 7: sl.update_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 8: sl.update_last(); <br>
 sl.display(); <br>
 break; <br>
 case 9: sl.update_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 10:sl.sort(); <br>
 sl.display(); <br>
 break; <br>
 case 11:sl.reverse(); <br>
 sl.display(); <br>
 break; <br>
 case 12:sl.search(); <br>
 sl.display(); <br>
 break; <br>
 case 13:sl.display(); <br>
 break; <br>
 case 14:exit(0); <br>
 break; <br>
 default:cout<<"Wrong choice...???"<<endl; <br>
 break; <br>
 } <br>
 } <br>
 while(choice != 14); <br>
} <br>
node *single_llist::create_node(int value)<br> 
{ <br>
 struct node *temp, *s; <br>
 temp = new(struct node); <br>
 if (temp == NULL) <br>
 { <br>
 cout<<"Memory not allocated"<<endl; <br>
 return 0; <br>
 } <br>
 else <br>
 { <br>
 temp->info = value; <br>
 temp->next = NULL; <br>
 return temp; <br>
 } <br>
} <br>
void single_llist::insert_begin() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
}<br>
void single_llist::insert_last() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL;<br>
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 while (s->next != NULL)<br> 
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_pos() <br>
{ <br>
 int value, pos, counter = 0, loc = 1; <br>
 struct node *temp, *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if(pos == 1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 for (int i = 1; i < pos; i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = temp; <br>
 temp->next = s; <br>
 cout<<temp->info<<" is inserted at position "<<pos<<endl; <br>
 } <br>
 else if (pos == counter+1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL;<br> 
 s->next = temp;<br> 
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Positon out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_begin() <br>
{ <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl;<br> 
 free(s); <br>
 } <br>
} <br>
void single_llist::delete_last() <br>
{ <br>
 int i, counter = 0; <br>
 struct node *s, *ptr; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s = start; <br>
 if (counter == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 else<br> 
 { <br>
 for (i = 1;i < counter;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_pos() <br>
{ <br>
 int pos, i, counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br><br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else<br> 
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : ";<br> 
 cin>>pos;<br> 
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl;<br> 
 free(s); <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 for (i = 1;i < pos;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 if(pos == counter) <br>
 {cout<<s->info<<" deleted from last"<<endl; <br>
 free(s);} <br>
 else <br>
 {cout<<s->info<<" deleted from postion "<<pos<<endl;<br> 
 free(s);} <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::update_begin() <br>
{ <br>
 int value, pos=1, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_last() <br>
{ <br>
 int value, pos, i,counter = 0; <br>
 struct node *s, *ptr;<br> 
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s=start; <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < counter ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_pos()<br> 
{ <br>
 int value, pos, i,counter = 0, loc = 1; <br>
 struct node *s, *ptr;<br> 
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else<br> 
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos;<br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl;<br> 
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < pos ; i++) <br>
 { <br>
 s = s->next;<br> 
 }<br> 
 s->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 }<br>
 }<br>
} <br>
void single_llist::sort() <br>
{<br> 
 struct node *ptr, *s;<br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info > s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info;<br> 
 s->info = value;<br> 
 }<br> 
 } <br>
 ptr = ptr->next; <br>
} <br>
 } <br>
}<br> 
void single_llist::reverse() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){}<br> 
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 {<br> 
 if (ptr->info < s->info) <br><br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info;<br> 
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next;<br> 
 }<br><br> 
 }<br> 
}<br> 
void single_llist::search()<br> 
{<br> 
 int value, loc = 0, pos = 0, counter = 0;<br> 
 struct node *s;<br> 
 s = start; <br>
 while (s != NULL) <br><br>
 {<br> 
 s = s->next; <br>
 counter++; <br>
 }<br> 
 if (start == NULL){}<br> 
 else<br> 
 { <br>
 cout<<"Enter the value to be searched : "; <br>
 cin>>value;<br> 
 struct node *s; <br>
 s = start;<br> 
 while (s != NULL) <br>
 { <br>
 pos++; <br>
 if (s->info == value) <br>
 {<br> 
 loc++;<br> 
 if(loc == 1)<br> 
 cout<<"Element "<<value<<" is found at position "<<pos; <br>
 else if(loc <= counter)<br> 
 cout<<" , "<<pos; <br>
 }<br> 
 s = s->next;<br> 
 } <br><br>
 cout<<endl; <br>
 if (loc == 0) <br>
 cout<<"Element "<<value<<" not found in the list"<<endl; <br>
 } <br>
} <br>
void single_llist::display() <br>
{ <br>
 struct node *temp; <br>
 if (start == NULL) <br>
 cout<<"Linked list is empty...!!!"<<endl; <br>
 else <br>
 { <br>
 cout<<"Linked list contains : "; <br>
 temp = start; <br>
 while (temp != NULL) <br>
 { <br>
 cout<<temp->info<<" "; <br>
 temp = temp->next; <br>
 } <br>
 cout<<endl; <br>
 } <br>
}<br>
 Output:
 
 1-
 ![image](https://user-images.githubusercontent.com/98145098/152732423-58977b5b-51b2-4e7e-a414-6f900bc6f68a.png)<br>
 2-
 ![image](https://user-images.githubusercontent.com/98145098/152732564-a144509e-22ca-43c6-82d1-eb12659f388d.png)<br>
 3-
 ![image](https://user-images.githubusercontent.com/98145098/152732696-8dc15628-ed86-4f9c-b90c-c71900e1f2cf.png)<br>
 4-
 ![image](https://user-images.githubusercontent.com/98145098/152732795-66d83149-9257-435a-9149-0f922f2d4f0c.png)<br>
 5-
 ![image](https://user-images.githubusercontent.com/98145098/152733082-4600662d-2110-4ac5-8525-f60fa73a5520.png)<br>
 6-
 ![image](https://user-images.githubusercontent.com/98145098/152733148-083b7587-0d49-4418-8327-646555158ead.png)<br>
 7-
 ![image](https://user-images.githubusercontent.com/98145098/152733255-73fb027e-9b88-44b3-9f6c-f55ddc208991.png)<br>
 8-
![image](https://user-images.githubusercontent.com/98145098/152733399-c9e45dbe-282b-46cb-853c-db36ed43e2b3.png) <br>
 
 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>

 
//2. Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.//<br>
#include<iostream><br>
using namespace std;<br>
struct Node<br>
{<br>
int value;<br>
struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
struct Node* sHead = NULL;<br>
struct Node* temp = NULL;<br>
void insert(int new_data)<br>
{<br>
struct Node* new_node = new Node();<br>
new_node->value = new_data;<br>
new_node->next = head;<br>
head = new_node;<br>
}<br>
int n;<br>
int ele;<br>
int splitIndex;<br>
int main()<br>
{<br>
int i;<br>
cout<<"Enter number of elements you want in the list\t";<br>
cin>>n;<br>
cout<<"Enter elements :" <<endl;<br>
for(i=0;i<n;i++)<br>
{<br>
cin>>ele;<br>
insert(ele);<br>
}<br>
cout<<"\nList of elements : "<<endl;<br>
Node *t;<br>
t = head;<br>
while(t != NULL)<br>
{<br>
cout<<t->value<<"\t";<br>
t = t->next;<br>
}<br>
cout<<"\n\nEnter the position you want the list to split ";<br>
cin>>splitIndex;<br>
while(splitIndex < 0 || splitIndex > n-1)<br>
{<br>
cout<<"Invalid position. Try again."<<endl;<br>
cin>>splitIndex;<br>
}<br>
temp = head;<br>
for(i=0;i<=splitIndex;i++)<br>
{<br>
if(i==splitIndex-1)<br>
{<br>
Node *tN;<br>
tN = temp->next;<br>
sHead = tN;<br>
temp->next = NULL;<br>
break;<br>
}<br>
temp = temp->next;<br>
}<br>
temp = head;<br>
if(temp == NULL)<br>
{<br>
cout<<"\nFirst list is empty"<<endl;<br>
}<br>
else<br><br>
{<br><br>
cout<<"\n\nFirst list element "<<endl;<br>
while(temp != NULL)<br>
{<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
temp = sHead;<br>
if(temp == NULL)<br>
{<br>
cout<<"\nSecond list is empty"<<endl;<br>
 }<br>
 else<br>
 {<br>
cout<<"\n\nSecond list elements "<<endl;<br>
while(temp != NULL)<br>
{<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
return 0;<br>
}<br>

 Output:<br> 
 
