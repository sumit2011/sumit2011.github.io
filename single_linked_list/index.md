# Single Linked List

Navigation system works on the concept of linked list.
<!--more-->
{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}
## 1. Introduction:
Single linked list is a `linear data structure`. It’s elements are not stored in contiguous memory location like arrays. it is slightly different from array. it made by the nodes, each nodes consist a data and the address of the next node and each nodes are linked using pointers.

## 2. Creation of Node
To create a new node in `C++`, you will need to define a structure or class that represents a node, and then create an instance of that structure or class.

Here is an example of a node structure in `C++`:
```c
struct Node 
{
  int value;
  Node* next;
};
```
## 3. Insertion
An insertion operation in a single linked list involves adding a new node to the list. There are several ways to do this, depending on where you want to insert the new node:
 1. At the beginning of the list
 2. At the end of the list
 3. At a specific position

### 3.1 Insertion at Begining
To insert a new node at the beginning of the list, you need to create a new node and set its next pointer to point to the current head of the list. Then, you can set the head of the list to the new node.
```c
void insertAtBeg(int value)
{
    struct Node *newnode;
    newnode = (struct Node *)malloc(sizeof(struct Node));
    newnode->data = value;
    if (head == NULL)
    {
        newnode->next = NULL;
        head = newnode;
    }
    else
    {
        newnode->next = head;
        head = newnode;
    }
    printf("\n\n*Inserted successfully at beginning*\n");
}
```

### 3.2 Insertion at Last
To insert a new node at the end of the list, you need to traverse the list until you reach the last node. Then, you can set the next pointer of the last node to point to the new node.
```c
void insertATend(int value)
{
    struct Node *newnode;
    newnode = (struct Node *)malloc(sizeof(struct Node));
    newnode->data = value;
    if (head == NULL)
    {
        newnode->next = NULL;
        head = newnode;
    }
    else
    {
        struct Node *temp;
        temp = head;
        while (temp->next != NULL)
        {
            temp = temp->next;
        }
        temp->next = newnode;
        newnode->next = NULL;
    }
    printf("\n\n*Inserted Successfully in END *\n");
}
```

### 3.3 Insertion at Any Position
To insert a new node at a specific position in the list, you need to traverse the list until you reach the node before the position where you want to insert the new node. Then, you can set the next pointer of the new node to point to the node at the desired position, and set the next pointer of the node before the position to point to the new node.
```c
// insertion at any position
void insertAtPos(int pos, int value)
{
    struct Node *newnode;
    newnode = (struct Node *)malloc(sizeof(struct Node));
    newnode->data = value;

    struct Node *temp = NULL;
    int i = 1;
    temp = head;
    while (i < pos - 1)
    {
        temp = temp->next;
        i++;
    }
    newnode->next = temp->next;
    temp->next = newnode;
}
```
## 4. Deletion
A deletion operation in a single linked list involves removing a node from the list. There are several ways to do this, depending on which node you want to delete:
 1. Deleting the head node
 2. Deleting the last node
 3. Deleting a node in the middle of the list
### 4.1 Deletion from Begining
To delete the head node, you simply need to set the head of the list to the next node in the list.
```c
// deletion at begining
void deletatBeg()
{
    struct Node *temp;
    temp = head;
    head = head->next;
    free(temp);
}
```

### 4.2 Deletion from End
To delete the last node, you need to traverse the list until you reach the second-to-last node. Then, you can set the next pointer of the second-to-last node to null, effectively removing the last node from the list.
```c 
// deletion at end
void deletatEnd()
{
    struct Node *temp, *prev;
    prev = temp = head;
    while (temp->next != NULL)
    {
        prev = temp;
        temp = temp->next;
    }
    prev->next = NULL;
    free(temp);
}
```

### 4.3 Deletion from Any Position
To delete a node in the middle of the list, you need to traverse the list until you reach the node before the one you want to delete. Then, you can set the next pointer of the previous node to point to the node after the one you want to delete, effectively skipping over the node to be deleted.
```c
// deletion at any position
void deletatPos(int pos)
{
    struct Node *nextnode, *temp;
    int i = 1;
    nextnode = temp = head;
    while (i < pos)
    {
        temp = nextnode;
        nextnode = nextnode->next;
        i++;
    }
    temp->next = nextnode->next;
    free(nextnode);
}
```

## 5. Sorting of the Single Linked List
There are several ways to sort a single linked list, depending on the type of data being stored in the list and the desired sort order.
```c
// sorting of linked list
void sortlist()
{
    struct Node *ptr, *cpt;
    ptr = head;
    int temp;
    while (ptr->next != NULL)
    {
        cpt = ptr->next;
        while (cpt != NULL)
        {
            if (ptr->data > cpt->data)
            {
                temp = ptr->data;
                ptr->data = cpt->data;
                cpt->data = temp;
            }
            cpt = cpt->next;
        }
        ptr = ptr->next;
    }
}
```
## 6. Print Function
```c
// printing of linked list
void print()
{
    struct Node *temp;
    temp = head;
    while (temp != NULL)
    {
        printf("%d-->", temp->data);
        temp = temp->next;
    }
    printf("NULL");
}
```
## 7. To Find Length
```c
// length of the linked
int getlength()
{
    int len = 0;
    struct Node *temp = head;
    while (temp != NULL)
    {
        len++;
        temp = temp->next;
    }
    printf("%d", len);
}
```


## 8. Main Function

```c
// main function
int main()
{
    // int a;
    // printf("how many elements do you want enter= ");
    // scanf("%d", &a);
    // for (int i = 0; i < a; i++)
    // {
    //     int data;
    //     scanf("%d", &data);
    //     insertATend(data);
    // }
    // print();
    insertAtBeg(34);
    insertAtBeg(45);
    insertAtBeg(72);
    insertAtBeg(5);
    insertAtBeg(89);
    insertAtBeg(99);
    insertATend(23);
    insertATend(55);
    insertATend(13);
    insertATend(41);
    insertAtPos(6, 8992);
    print();
    printf("\n");
    deletatBeg();
    deletatEnd();
    deletatPos(3);
    print();
    printf("\n");
    sortlist();
    print();
    insertATend(58);
    print();
    printf("\n");
    reverse();
    print();
    printf("\n\n");
    printf("length: ");
    getlength();
    return 0;
}
```


<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-PFRLG5MZ6V"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-PFRLG5MZ6V');
</script>

