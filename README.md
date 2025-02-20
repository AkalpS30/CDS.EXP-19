# CDS.EXP-19
#### Aim 
To study and implement queue in C++. 

#### Software 
Visual Studio Code 

#### Theory 
<ul>
    A queue in C++ is a data structure that follows the First In, First Out (FIFO) principle, meaning that the first element added to the queue will be the first one to be removed. Think of it like a line of people waiting: the first person in line is the first one to be served.

##### Key Characteristics of a Queue
FIFO Structure: The order of processing follows a strict sequence, where elements are added to the back and removed from the front.

##### Basic Operations:

-Enqueue: Add an element to the back of the queue.

-Dequeue: Remove the element from the front of the queue.

-Front: Access the element at the front without removing it.

-Size: Get the number of elements currently in the queue.

-Empty: Check if the queue has no elements.
</li>
</ul>

#### Code 

(A) <br> 
```cpp
//AKALP SARKAR
//23070123116
//EXP 19 A
//ENTCB2
#include <iostream>
using namespace std;
int queue[100], n = 100, front = - 1, rear = - 1;
void Insert() {
   int val;
   if (rear == n - 1)
   cout<<"Queue Overflow"<<endl;
   else {
      if (front == - 1)
      front = 0;
      cout<<"Insert the element in queue : "<<endl;
      cin>>val;
      rear++;
      queue[rear] = val;
   }
}
void Delete() {
   if (front == - 1 || front > rear) {
      cout<<"Queue Underflow ";
      return ;
   } else {
      cout<<"Element deleted from queue is : "<< queue[front] <<endl;
      front++;;
   }
}
void Display() {
   if (front == - 1)
   cout<<"Queue is empty"<<endl;
   else {
      cout<<"Queue elements are : ";
      for (int i = front; i <= rear; i++)
      cout<<queue[i]<<" ";
         cout<<endl;
   }
}
int main() {
   int ch;
   cout<<"1) Insert element to queue"<<endl;
   cout<<"2) Delete element from queue"<<endl;
   cout<<"3) Display all the elements of queue"<<endl;
   cout<<"4) Exit"<<endl;
   do {
      cout<<"Enter your choice : "<<endl;
      cin>>ch;
      switch (ch) {
         case 1: Insert();
         break;
         case 2: Delete();
         break;
         case 3: Display();
         break;
         case 4: cout<<"Exit"<<endl;
         break;
         default: cout<<"Invalid choice"<<endl;
      }
   } while(ch!=4);
   return 0;
}
```

#### Output 
![OUTPUT19A](https://github.com/user-attachments/assets/b6788bea-cf99-4932-b9ff-59b6de0bbb1d)


(B) <br> 
```cpp
//AKALP SARKAR
//23070123116
//EXP 19 B
//ENTC B2
#include <iostream>
using namespace std;
#define size 5
#define ERROR -9999

class Queue {
    int rear, front, arr[size];
public:
    Queue() {
        rear = -1;
        front = -1;
    }
    void enqueue(int);
    int dequeue();
    void disp();
};
void Queue::enqueue(int num) {
    if (rear == size - 1) {
        cout << "Queue is full" << endl;
    } else {
        if (front == -1) {
            front = 0;
        }
        arr[++rear] = num;
    }
}
int Queue::dequeue() {
    if (front == -1 || front > rear) {
        cout << "Queue is empty" << endl;
        return ERROR;
    } else {
        return arr[front++];
    }
}
void Queue::disp() {
    if (front == -1 || front > rear) {
        cout << "Queue is empty" << endl;
    } else {
        cout << "Queue elements: ";
        for (int i = front; i <= rear; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    }
}

int main() {
    Queue q1;
    q1.enqueue(4);
    q1.enqueue(8);
    q1.enqueue(3);
    q1.disp();
   
    int val = q1.dequeue();
    cout << "Deleted element: " << val << endl;
   
    q1.disp();
   
    return 0;
}
```

#### Output 
![OUTPUT19B](https://github.com/user-attachments/assets/f21298b5-85d3-4e72-94c5-edd3501a20ec)

#### Conclusion 
I learnt about queue in C++ . 
