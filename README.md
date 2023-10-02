1. Frequency of Elements in Array

#include <iostream> 
#include <map> 
using namespace std; 
void frequency(int *arr, map<int,int> m){ 
 for(int i=0;i<10;i++) { 
 m[arr[i]]++; 
 }
 for(auto i:m){ 
 cout<<i.first<<" "<<i.second<<endl;
 } 
} 
int main(){ 
map<int,int> m; 
 int arr[10] = {1,4,6,4,2,7,4,2,2,6}; 
cout<<"Frequency of array1 elements: "<<endl; frequency(arr,m); 
int arr2[10] = {1,2,3,4,6,2,3,4,2,4}; 
 cout<<"Frequency of array2 elements: "<<endl; frequency(arr2,m); 
return 0; 
}

2. Circular, Single, Doubly LinkedList

#include <iostream> 
class LinkedList { 
public: 
 Node* head; 
 LinkedList() : head(nullptr) {} 
 void insertHead(int val) { 
 Node* newNode = new Node(val); 
 newNode->next = head; 
 head = newNode; 
 } 
 void deleteHead() { 
if (head) { 
 Node* temp = head; 
 head = head->next; 
 delete temp; 
 } 
 } 
 void insertEnd(int val) { 
 Node* newNode = new Node(val); 
 if (!head) { 
 head = newNode; 
 } 
else { 
 Node* current = head; 
 while (current->next) { 
 current = current->next; 
 } 
 current->next = newNode; 
 } 
 } 
 void deleteEnd() { 
 if (!head) { 
 return; 
 } 
 if (!head->next) { 
 delete head; 
head = nullptr; 
 return; 
 } 
 Node* current = head; 
while (current->next->next) { 
current = current->next; 
 } 
 delete current->next; 
 current->next = nullptr; 
 } void printList() { 
Node* current = head; 
while (current) { 
std::cout << current->data << " "; 
current = current->next; 
 } 
 } };
int main() { 
 LinkedList sll; sll.insertEnd(1); sll.insertEnd(2); sll.insertHead(3); sll.printList(); // Output: 3 1 2 
sll.deleteHead(); sll.deleteEnd(); sll.printList(); // Output: 1 
return 0; 
} 
#include <iostream>
class DoublyLinkedList { public: 
 Node* head; 
 DoublyLinkedList() : head(nullptr) {} 
 void insertHead(int val) { //same as singly linked list 
 } 
 void deleteHead() { 
 if (head) { 
 Node* temp = head; 
head = head->next; 
if (head) 
head->prev = nullptr; 
delete temp; 
 } 
 } 
 void insertEnd(int val) { 
Node* newNode = new Node(val); 
 if (!head) { 
head = newNode; 
 } 
else { 
 Node* current = head
while (current->next) { 
current = current->next; 
 } 
 current->next = newNode; 
newNode->prev = current; 
 } 
 } 
 void deleteEnd() { 
if (!head) { 
return; 
 } 
 if (!head->next) {
 delete head; 
head = nullptr; 
return; 
 } 
 Node* current = head; 
while (current->next) { 
current = current->next; 
 } 
 current->prev->next = nullptr; 
delete current; 
 } 
int main() {
 DoublyLinkedList dll; 
 //same as singly linked list 
 //output- 6 5 4 }
4. Circular Linked List: 
#include<iostream> 
class CircularLinkedList{
public: 
 Node* head; 
 CircularLinkedList() : head(nullptr) {} 
void insertHead(int val) { 
Node* newNode = new Node(val); 
 if (!head) { 
newNode->next = newNode; 
head = newNode; 
 }
else {
 Node* tail = head;
 while (tail->next != head) { 
 tail = tail->next; 
 }
 tail->next = head; 
 } 
 } 
 void deleteHead() {
 if (!head) {
 return; 
 } 
 if (head->next == head) { 
 delete head;
 head = nullptr;
 } 
else { 
 Node* temp = head; 
 Node* tail = head; 
 while (tail->next != head) { 
 tail = tail->next; 
 }
 delete temp;
 } 
 } 
 void insertEnd(int val) { 
 Node* newNode = new Node(val); 
 if (!head) { 
 newNode->next = newNode; 
head = newNode; 
 } 
else {
 Node* tail = head;
 while (tail->next != head) {
 tail = tail->next; 
 } 
 newNode->next = head; 
 } 
 } 
 void deleteEnd() { 
 if (!head) { 
 return; 
 } 
 if (head->next == head) { 
 delete head;
 head = nullptr; 
 }
else { 
 Node* tail = head;
 Node* prev = nullptr; 
 while (tail->next != head) { 
 prev = tail; 
 } 
 delete tail; 
 } 
 } 
 void printList() { 
 int main() { 
 CircularLinkedList cll; 
 return 0; 
} 





3. Power function
   
  #include <iostream> 
using namespace std; 
int power(int x, unsigned int n) { 
 int temp; 
if (n == 0) 
 return 1;
 temp = power(x, n /2);
if (n % 2 == 0) 
return temp * temp; 
else 
 return x * temp * temp; 
} 
int main() { 
int x; 
 cout<<"Enter value of x"<<endl; 
 cin>>x; 
 int n; 
 cout<<"Enter value of n"<<endl; 
 cin>>n; 
cout<<power(x,n); 
 return 0; 
}


4. Stack IsEmpty, IsFull
  
#include<iostream>
using namespace std; 
class node{ 
public: node* next;
int data; 
node(int data){ this->next=NULL; this->data=data;
} }; 
class stack{ 
node* head=NULL; 
int size=0; 
public: 
void push(int x){ 
node* nodetopush=new node(x); 
nodetopush->next=head; 
head=nodetopush; size++;
} 
void pop(){ 
if(head==NULL){ 
return;
}
else{ 
node* temp = head; 
head=head->next; 
delete (temp); size--; 
} 
} 
void top(){ 
if(head==NULL) { 
cout<<"Stack is empty ... "<<endl; 
return; 
}
cout<<head->data<<endl; 
}
int showsize(){ 
return size; 
} 
};
int main(){ 
stack st;
st.push(40);
st.top(); 
st.push(60); 
st.top(); 
st.push(100);
st.top();
st.pop(); 
st.top(); 
st.pop(); 
cout<<"Size of the stack is: "<<st.showsize(); 
st.top(); 
st.pop(); 
st.top(); 
return 0; 
}
