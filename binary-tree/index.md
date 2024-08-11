# Binary Tree



<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## Intro


## Basic operations in the binary tree
1. Inserting an element
2. Removing
3. Searching
4. Traversing
5. Height of the tree
6. Level of a node
7. Size of the tree


## Application of binary tree


## Creation of binary tree
First we create a class with name node which represent a node of the binary tree. Each node contain the data, pointer to the left child and pointer the right child. By the following code we 

```c++
#include<iostream>
#include <queue>
using namespace std;

class node {
    public:
        int data;
        node* left;
        node* right;

    node(int d) {
        this -> data=d;
        this -> left = NULL;
        this -> right = NULL;
    }
};
```

```c++
node* buildTree(node* root) {
    cout<<"Enter The Data:" <<endl;
    int data;
    cin>>data;
    root = new node(data);

    if(data== -1) {
        return NULL;
    }

    cout << "Enter data for inserting in left of "<<data << endl;
    root->left = buildTree(root->left);
    cout <<" Enter data for inserting in right of "<<data<< endl;
    root -> right = buildTree(root->right);
    return root;

}
```
## Different type of traversals in binary tree
1. level order traversal
2. Inorder
3. Preorder
4. Postorder

### Levelorder Traversal

```c++
//level order triversal
void levelOrderTraversal(node* root)
{
    queue<node*> q;
    q.push(root);
    q.push(NULL);

    while(!q.empty()) {
        node* temp = q.front();
        
        q.pop();

        if(temp==NULL){
            cout<<endl;
            if(!q.empty()){
                q.push(NULL);
            }
        }

        else{
            cout<< temp -> data << " ";
            if(temp-> left) {
            q.push ( temp-> left);
        }

        if(temp->right){
            q.push ( temp-> right);
        }
        }
        

    }
}
```
### Inorder Traversal

```c++
//inorder traversal
void inorder(node* root)
{
    if(root == NULL){
        return;
    }
    inorder(root->left);
    cout<<root->data<<" ";
    inorder(root->right);
}
```

### Preorder Traversal
```c++
//preorder traversal
void preorder(node* root)
{
    if(root == NULL){
        return;
    }
    cout<<root->data<<" ";
    preorder(root->left);
    
    preorder(root->right);
}
```

### Postorder Traversal
```c++
//post traversal
void postorder(node* root)
{
    if(root == NULL){
        return;
    }
    postorder(root->left);
    
    postorder(root->right);
    cout<<root->data<<" ";
}
```


```c++
void buildFromLevelOrder(node* &root){
    queue<node*> q;1 3 5 7 11 17 -1 -1 -1 -1 -1 -1 -1
    cout<<"enter data for root"<<endl;
    int data;
    cin>>data;
    root = new node(data);
    q.push(root);

    while(!q.empty()){
        node* temp = q.front();
        q.pop();

        cout<< " enter left node for: "<<root->data<<endl;
        int leftData;
        cin>>leftData;

        if(leftData != -1){
            temp->left = new node(leftData);
            q.push(temp->left);
        }
        cout<< "enter right node for: "<<root->data<<endl;
        int rightData;
        cin>>rightData;

        if(rightData != -1){
            temp->right = new node(rightData);
            q.push(temp->right);
        }
    }
}
```


```c++
int main() {

    node* root = NULL;

    buildFromLevelOrder(root);
    levelOrderTraversal(root);

// 1 3 5 7 11 17 -1 -1 -1 -1 -1 -1 -1

    root = buildTree(root);
    cout<<"the given tree is:"<<endl; 
// 1 3 7 -1 -1 11 -1 -1 5 17 -1 -1 -1
    levelOrderTraversal(root);


    cout<<"inorder traversal is: ";
    inorder(root);
    cout<<endl;

    cout<<"preorder traversal is: ";
    preorder(root);
    cout<<endl;

    cout<<"postorder traversal is: ";
    postorder(root);
    return 0;

}
```

## Imp functions to solve dsa problems 
### converting BT into the inarr

### finding a node
finding a node in the given binary tree

finding the distance of a node from the root


