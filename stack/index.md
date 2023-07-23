# Stack (array implementation)


<!--more-->
{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## Introduction
**Stack** is a **linear data structure** that follows a particular order in which several type of operations like push pull are performed. The order can be `LIFO` or `FILO`, both are same so don't be confused.

LIFO:(Last in first out) It means which element that can be filled at last that will be removed first.

FILO:(first in last out) It means that element will be removed at last which is filled at first.

Operations that can be performed:
 1. push
 2. pop
 3. peek
 4. isempty

## Creation of stack
This code defines a C++ class named "stack," representing a basic stack data structure. The class has three properties: "arr" (a pointer to an integer array to store the stack elements), "top" (an integer representing the index of the topmost element in the stack), and "size" (an integer specifying the maximum capacity of the stack). Additionally, the class has a constructor that takes an integer "size" as a parameter and initializes the properties accordingly. The constructor allocates memory for the stack using the "new" keyword, sets the stack size, and initializes "top" to -1 to indicate that the stack is initially empty. With this class, you can create a stack object with a specific size and use it to implement stack operations like push, pop, peek, and check if the stack is empty or not.
```c++
//array emplementation of stack

 #include<iostream>
 using namespace std;

 class stack {
    //properties
    public:
        int *arr;
        int top;
        int size;

    //behaviour
    stack(int size) {
        this -> size = size;
        arr = new int[size];
        top=-1;
    }
 };
 ```

## Push Function
The "push" function is part of the "stack" class and aims to add a new element to the stack. It checks if there is space available by comparing the difference between the maximum size of the stack and the current top index. If space is available, the function increments the top index to make room for the new element, assigns the new element to the top position in the array, effectively adding it to the stack. If the stack is already full, the function prints an error message indicating "stack overflow," signifying that the operation cannot be performed.
 ```c++
 //push function
 void push (int element) {
        if(size-top >1 ){
            top++;
            arr[top] = element;
        }
        else{
            cout << "stack overflow" << endl;
        }
    }
```
## Pop Function
The "pop" function is also part of the "stack" class and serves to remove the topmost element from the stack, following the Last-In-First-Out (LIFO) principle. It first checks if there are any elements in the stack by examining the value of the top index. If the top index is greater than or equal to 0, it means there is at least one element in the stack. In that case, the function decrements the top index, effectively removing the top element and making the next element (if any) the new top. This simulates the removal of the last added element. However, if the top index is less than 0, it means the stack is empty, and there are no elements to remove. In this situation, the function prints an error message, "stack underflow," indicating that the operation cannot be performed as the stack is already empty.
```c++
//pop function
void pop(){
        if(top >= 0){
            top--;
        }
        else{
            cout<< " stack underflow "<<endl;
        }

    }
```

## Peek Function
The "peek" function is a part of the "stack" class and is used to look at the topmost element of the stack without removing it. When called, the function first checks if there are any elements in the stack by examining the value of the top index. If the top index is greater than or equal to 0, it means there is at least one element in the stack. In this case, the function returns the value of the element at the top position. However, if the top index is less than 0, it means the stack is empty, and there are no elements to peek at. In this situation, the function prints an error message, "stack is empty," and returns -1 to indicate that there's no valid element to return.
```c++
int peek() {
        if(top >=0 )
            return arr[top];
        else{
            cout <<"stack is empty "<<endl;
            return -1;
        }
    }
```

## IsEmpty function
The "isempty" function is a member of the "stack" class and is used to check whether the stack is empty or not. When called, the function examines the value of the "top" index, which represents the position of the topmost element in the stack. If the "top" index is equal to -1, it means there are no elements in the stack, and it is considered empty. In this case, the function returns "true" to indicate that the stack is empty. However, if the "top" index is not -1, it means there is at least one element in the stack, and it is not empty. In this situation, the function returns "false" to indicate that the stack is not empty. In summary, the "isempty" function provides a convenient way to check the emptiness status of the stack, returning "true" if it's empty and "false" if it contains elements.
```c++
bool isempty(){
        if(top == -1){
            return true;
        }
        else{
            return false;   
        }
    }
```

## The main function 
In this C++ code, the "main" function demonstrates the usage of a stack data structure implemented through the "stack" class. Firstly, it creates a stack object "st" with a size of 5. Then, it uses the "push" function to add three elements (22, 33, and 44) to the stack. The "peek" function is called to print the top element (44). Subsequently, the "pop" function is used to remove the top element from the stack, and "peek" is called again to print the new top element (33). This process is repeated two more times with the last element (22) being popped, and "peek" is called again, but the stack is now empty. Finally, the "isempty" function is called to verify if the stack is empty, and it prints "stack is empty" as the output, confirming that the stack is empty at this point.

```c++
int main(){
    stack st(5);

    st.push(22);
    st.push(33);
    st.push(44);
    cout << st.peek()<<endl;
    st.pop();
    cout << st.peek()<<endl;
st.pop();
    cout << st.peek()<<endl;
    st.pop();
    cout << st.peek()<<endl;

    if(st.isempty()){
        cout<< "stack is empty"<<endl;
    }
    else
    cout<<"stack is not empty"<<endl;
 }
```

output of the following code
{{< figure src="/posts/DSA/stack/output.png" >}}

>Complete code
```c++
//array emplementation of stack

 #include<iostream>
 
 using namespace std;

 class stack {
    //properties
    public:
        int *arr;
        int top;
        int size;

    //behaviour
    stack(int size) {
        this -> size = size;
        arr = new int[size];
        top=-1;
    }

    void push (int element) {
        if(size-top >1 ){
            top++;
            arr[top] = element;
        }
        else{
            cout << "stack overflow" << endl;
        }
    }

    void pop(){
        if(top >= 0){
            top--;
        }
        else{
            cout<< " stack underflow "<<endl;
        }

    }

    int peek() {
        if(top >=0 )
            return arr[top];
        else{
            cout <<"stack is empty "<<endl;
            return -1;
        }
    }

    bool isempty(){
        if(top == -1){
            return true;
        }
        else{
            return false;   
        }
    }

 };

 int main(){
    stack st(5);

    st.push(22);
    st.push(33);
    st.push(44);
    cout << st.peek()<<endl;
    st.pop();
    cout << st.peek()<<endl;
st.pop();
    cout << st.peek()<<endl;
    st.pop();
    cout << st.peek()<<endl;

    if(st.isempty()){
        cout<< "stack is empty"<<endl;
    }
    else
    cout<<"stack is not empty"<<endl;
 }
```



Questions
reverse a string using stack

{{< admonition type=question title="Problems" open=false >}}
{{< link "https://www.codingninjas.com/studio/problems/two-stacks_983634" "**Two stack** (Coding ninjas)">}}
{{< link "https://www.codingninjas.com/studio/problems/delete-middle-element-from-stack_985246" "**Middle element** (Coding ninjas)">}}


{{< /admonition >}}
