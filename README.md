# stack
#include<climits>
class StackUsingArray {
    int *data;
    int nextIndex;
    int capacity;
    public: 
    StackUsingArray(int totalSize) {
        data = new int [totalSize];
        nextIndex= 0;
        capacity = totalSize;
    }
    
    int size() {
        return nextIndex;
    }
    bool isEmpty() {
        /*
        if(0 == nextIndex) {
            cout<<"Stack is full";
        }
        else {
            return false;
        }
        */
        return nextIndex == 0;
    }
    
    void push(int element) {
        if(nextIndex==capacity){
             cout<<"Stack is full";
        }
        data[nextIndex] = element;
        nextIndex++;
    }
    //delete the element
    int pop(){
        if(nextIndex==0){
            cout<<"stack is empty"<<endl;
            return INT_MIN;
        }
        nextIndex--;
        return data[nextIndex];
    }
    int top(){
        if(isEmpty()){
            cout<<"Stack is empty"<<endl;
            return INT_MIN;
        }
        return data[nextIndex-1];
    }
    
};


#include<iostream>
using namesapace std;
int main() {
  
  StackUsingArray s;
  s.push(10);
  s.push(43);
  s.push(35);
  s.push(34);
  s.push(343);
  
  cout<<s.top()<<endl;
  cout<<s.pop()<<endl;
  cout<<s.isEmpty()<<endl;
  cout<<s.pop()<<endl;
  cout<<s.pop()<<endl;
  cout<<s.isEmpty()<<endl;
    
}



//size constraint their in inserting array 
// now we uses dynamic array to remove size constraint

STackUsingArray(){
    data = new int[4];
    capacity =4;
    nextIndex =0
}

void push(element) {
    if(nextIndex == capacity) {
        int *newData = new int(2*capacity);
        for(int i=0;i<capacity;i++) {
            newData[i]=data[i];
        }
        delete[] data;
        capacity*=2;
        newData[i]  = element;
        nextInode++;
    }
}


 ----------TEMPLATES------------
 
 
 class pair {
     int x;
     int y;
     
     public:
      void setX(int x) {
          this->x = x;
      }
      int getX(){
          return x;
      }
      void setY(int y){
          this->y =y;
      }
      int getY() {
          return y;
      }
 }
 
// ----------------- After using ----------TEMPLATES------------
  
  
  template<typename T>
  class Pair{
      T x;
      T y;
      public :
      
      void setX(T x) {
          this->x=x;
      }
      T getX(){
          return x;
      }
      void setY(T y) {
          this -> y =y;
      }
      T getY() {
          return y;
      }
  }

 ~~~~~~~~~~~~~~~~~~~~~~~~
 
 int main () {
     Pair<int> p1;
     p1.setX(34);
     p1.setY(75);
     cout<<p1.getX()<<","<< p1.getY()<<endl;
     Pair<double> p2;
     p2.setX(45.3);
     p2.setY(563.3);
     cout<<p2.getX()<<","<<p2.getY()<<endl;
 }
 
 
 
 -------NOw of two different value in  ----------TEMPLATES------------
 
 template<typename T, typename v>
  class Pair() {
      T x;
      V y;
      public: 
      void setX(T x) {
          this -> x = x;
      }
       T getX() {
           return x;
       } 
       void setY(V y) {
           this -> y =y;
       }
       V getY() {
           return y;
       }
}  

~~~~~~~~~~~~~~~~
 int main()
 {
     Pair<int,double>p1;
     p1.setX(22);
     p1.setY(34.2);
     cout<<p1.getX()<<","<<p1.getY()<<endl;
     Pair<int,char> p2;
     p2.setX(34);
     p2.setY('c');
     cout<<p2.getX()<<","<<p2.getY()<<endl;
 } 
  ------------------ making three pair----------
  
   int main() {
       Pair<Pair<int,int>,int> p1;
       p1.setY(23);
       Pair<int,int>p4;
       p4.setX(45);
       p4.setY(75);
       p1.setX(p4);
       cout<<p1.getX().getX()<<","<<p1.getX().getY()<<","<<p1.getY()<<endl;
   }
   
   -----------template in Stack------------
   
   class StackUsingAarray {
       T *data;
       int nextIndex;
       int capacity;
       
       public:
       StackUSingArray(){
           data = new T[4];
           nextIndex =0;
           capacity = 4;
       }
    void push(T element) {
        if(nextIndex  == capacity){
            T *newData = new T(2*capacity);
            for(int i=0;i<capacity;i++) {
                newData[i] =  data[i];
                delete[] data;
                capacity*=2;
                newData[nextIndex] = element;
                nextIndex++;
            }
    }
   }
   T pop() {
       if(nextIndex == capacity) {
           cout<<"Stack is Empty"<<endl;
           return 0;
       }
       return data[nextIndex];
   }
   T top() {
       if(isEmpty()){
           cout<<"Stack is empty"<<endl;
           return 0;
       }
       return data[nextIndex-1];
   }
 } 
 
 ~~~~~~~~~~
 int main()
 {
     StackUsingArray<int>s;
     s.push(54);
     s.push(56);
     s.push(54);
     s.push(43);
     
 }

------------------------Linked list in Stack------------
#include<iostream>
using namespace std;
 template <typename T>
 class Node {
     public :
     Node<T> *next;
     int data;
     Node (T data){
         this->data= data;
         next =NULL;
     }
 };
 
 template<typename T>
 class Stack{
     int  size;  // number elements present in stack
     Node<T> *head;
      // Node<T> *tail;
     public:
     
     Stack() {
       head =NULL;
       //tail = NULL;
       size=0;
         
     }
     int getSize()  {
         return size;
         
     }
      bool isEmpty() {
          return size==0;
          
      }
      void push( T element) {
          Node<T> *newNode = new Node<T>(element);
              newNode->next = head;
              head= newNode;
              size++;
      }
      T pop() {
        if(isEmpty()){
            cout<<"Stack is Empty";
            return 0;
        }
        T ans = head-> data;
        Node<T> *temp = head;
        delete temp;
        head=head->next;
        size--;
        return ans;
      }
      
      T top() {
          if(head==NULL) {
              cout<<"Stack is empty"<<endl;
              return 0;
          }
          return head->data;
          
      }
     
   }

