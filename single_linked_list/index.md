# Single Linked List

Navigation system works on the concept of linked list.
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}
## 1. Introduction:
**Single linked list** is a **linear data structure**. It is slightly different from array. It made by the `nodes`, each nodes consist a data and the address of the next node and each `node` are linked using pointers. Here data are not stored in the contiguous memory location, nodes are present anywhere in the memory space but every `nodes` are linked with eachother that's why we call this `linked list`. Main benefit of linked list is that we can insert or delete data from any position in the list.

{{< mermaid >}}
graph LR;
    A(Head Node) --> B(2nd Node) --> C(3rd Node) --> D(Last Node)
{{< /mermaid >}}

## 2. Creation of Node
To create a **new node** in `C++`, you will need to define a **structure** or **class** that represents a node, and then create an instance of that structure or class. Here we will use structure to create or define a `node`.

Here is an example of a node structure in `C++` or `C`:
```c
struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;
```
## 3. Insertion
An insertion operation in a single linked list involves adding a new node to the list. For this first you have to create a `newnode` and then insert this node where you want. There are several ways to do this:
 1. At the beginning of the list
 2. At the end of the list
 3. At a specific position of the list

### 3.1 Insertion at Begining
To insert a new node at the beginning of the list, you need to create a new node and set it's next pointer to point to the current head of the list. Then, you can set the head of the list to the new node. You also have to check whether the first node is present or not in the list or we can say list is empty or not.
```c
// insertion at begining
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
    printf("%d is inserted at beginning.\n", value);
}
```

### 3.2 Insertion at Last
To insert a new node at the end of the list, you need to traverse the list until you reach the last node. Then, you can set the next pointer of the last node to point to the new node. If the list is empty then set the head to the newnode.
```c
// insertation at end
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
    printf("%d is inserted at the end.\n", value);
}
```
_`temp` is just a temorary node just like count variable after the operation it does'nt have any use._
{{< admonition type=info title="Traversal Technique" open=true >}}
_Traversal is the process of visiting and processing each node in a data structure, such as a linked list, tree, or graph. There are several techniques for traversing data structures, including depth-first search, breadth-first search, and in-order, pre-order, and post-order tree traversal._
{{< /admonition >}}
### 3.3 Insertion at Any Position
To insert a `new node` at a desired position in the list, first you need to make a temporary node say `temp` initialise with `head` then  traverse the list until you reach the node before the position where you want to insert the new node. Then, you can set the next pointer of the new node to point to the node at the desired position, and set the next pointer of the node before the position to point to the new node.
{{< figure src="/posts/DSA/Linkedlist_insert_middle.png" >}}
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
    printf("%d is inserted at the %dth position.\n", value, pos);
}
```
{{< admonition type=warning title="point to be consider" open=true >}}
_Here you get a segmentation fault if you enter that position which are not exist in the list. For this first you have to check whether the position is present or not in the list then insert the node at that position._
{{< /admonition >}}


## 4. Deletion
A deletion operation in a single linked list involves removing a node from the list and free the space. There are several ways to do this, depending on which node you want to delete:
 1. Deleting the head node
 2. Deleting the last node
 3. Deleting a node in the middle of the list
### 4.1 Deletion from Begining
To delete the head node, first you have to make a `temp` node initialise with `head` then set the head of the list to the next node in the list. Now free the `temp`.
```c
// deletion at begining
void deleteatBeg()
{
    if (head == NULL)
    {
        printf("The list is empty.\n");
    }
    else
    {
        struct Node *temp;
        temp = head;
        head = head->next;
        printf("%d is deleted from the begining\n", temp->data);
        free(temp);
    }
}
```

### 4.2 Deletion from End
To delete the last node, make a `temp` node traverse the list until you reach the second-to-last node. Then, you can set the next pointer of the second-to-last node to null, effectively removing the last node from the list.
```c 
// deletion at end
void deleteatEnd()
{
    if (head == NULL)
    {
        printf("The list is empty.\n");
    }
    else
    {
        struct Node *temp, *prev;
        prev = temp = head;
        while (temp->next != NULL)
        {
            prev = temp;
            temp = temp->next;
        }
        prev->next = NULL;
        printf("%d is deleted from the end\n", temp->data);
        free(temp);
    }
}
```

### 4.3 Deletion from Any Position
To delete a node in the middle of the list, you need to traverse the list until you reach the node before the one you want to delete. Then, you can set the next pointer of the previous node to point to the node after the one you want to delete, effectively skipping over the node to be deleted.
{{< figure src="/posts/DSA/Linkedlist_deletion.png" >}}
```c
// deletion at any position
void deleteatPos(int pos)
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
    printf("%d is deleted from the %dth position.\n", nextnode->data, pos);
    free(nextnode);
}
```

## 5. Sorting 
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
    printf("The list is sorted successfully.\n");
}
```

## 6. Reversing
This approach involves iterating through the linked list, and for each node, changing the next pointer to point to the previous node instead of the next node. This effectively reverses the order of the nodes in the linked list.This approach involves a recursive function that reverses the next pointers of each node as it traverses the linked list. The function returns the reversed linked list by returning the last node in the original linked list as the new head.
```c
// to reverse the list
void reverse()
{
    struct Node *current = head;
    struct Node *prev = NULL, *next = NULL;

    while (current != NULL)
    {
        next = current->next;
        current->next = prev;
        prev = current;
        current = next;
    }
    head = prev;
    printf("The list is reversed successfully.\n");
}
```

## 7. Print Function
To print the list you have to travarse the list and print each `node` one by one. For this make a `temp` node initialise with `head`, travarse and print.
```c
// printing of linked list
void display()
{
    printf("The list is: ");
    struct Node *temp;
    temp = head;
    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n\n");
}

```
## 8. To Find Length
To find the length of the list, first make a `temp` node initialise with `head` than travarse the list and increment the `count` by `1` on every travarsal until you reach to the last node.
```c
// length of the linked
int getlength()
{
    int count = 0;
    struct Node *temp = head;
    while (temp != NULL)
    {
        count++;
        temp = temp->next;
    }
    printf("Total nodes present in the list is: %d\n", count);
}
```


## 9. Main Function
Here is the main function. Now we check all the function whether they are working or not, call all the functions one by one.
```c
// main function
int main()
{

    insertAtBeg(34);
    insertAtBeg(45);
    insertAtBeg(72);
    insertAtBeg(50);
    insertAtBeg(89);
    insertAtBeg(99);
    insertATend(23);
    insertATend(55);
    insertATend(13);
    insertATend(41);
    insertAtPos(6, 8992);
    display();
    deleteatBeg();
    deleteatEnd();
    deleteatPos(3);
    display();
    sortlist();
    display();
    insertATend(58);
    display();
    reverse();
    display();
    insertAtBeg(99);
    insertATend(23);
    display();
    getlength();
    return 0;
}
```
{{< admonition type=note title="Note" open=true >}}
_It will be a better practice if you take the input from the user in the output terminal.
Then the main function will be:_
```c
// main function
int main()
{
    int choice,value,pos;

    printf("1) Insert at begining\n");
    printf("2) insert at last\n");
    printf("3) Insert at any position\n");
    printf("4) Delete from the begining\n");
    printf("5) Delete from the end\n");
    printf("6) Delete from any position\n");
    printf("7) Sort the list\n");
    printf("8) Reverse the list\n");
    printf("9) Fint the length of the list\n");
    printf("10) Display the list\n");
    printf("11) Exit\n")

    do
    {
        printf("Enter Choice: ");
        scanf("%d",&choice);
        switch (choice)
        {
        case 1:
            printf("Enter value to be inserted: ");
            scanf("%d",&value);
            insertAtBeg(value);
            break;
        case 2:
            printf("Enter value to be inserted: ");
            scanf("%d",&value);
            insertATend(value);
            break;
        case 3:
            printf("Enter the position and the value to be inserted respectively: ");
            scanf("%d%d",&pos,&value);
            insertAtPos(pos,value);
            break;
        case 4:
            deleteatBeg();
            break;
        case 5:
            deleteatEnd();
            break;
        case 6:
            printf("Enter the position of the node to be deleted: ");
            scanf("%d",&pos);
            deleteatPos(pos);
            break;
        case 7:
            sortlist();
            break;
        case 8:
            reverse();
            break;
        case 9:
            getlength();
            break;
        case 10:
            display();
            break;
        case 11:
            printf("Exit");
            break;
        default:
            break;
        }
    } while (choice!=11)
    return 0;
}
```

{{< /admonition >}}

***Complete Code of Single Linked List:*** {{< link "https://github.com/sumit2011/dsa-lab-assignment/blob/main/single_linklist.c" "Code">}}


{{< admonition type=tip title="Fun Dose" open=false >}}
{{< youtube FMzj9UYHTPQ >}}
{{< /admonition >}}


{{< admonition type=question title="Problems" open=false >}}
{{< link "https://www.codechef.com/YTPP001/problems/LL1" "**Linked List 1** (CodeChef)">}}
{{< link "https://www.codechef.com/YTPP001/problems/LL2" "**Linked List 2** (CodeChef)">}}
{{< link "https://www.hackerearth.com/practice/data-structures/linked-list/singly-linked-list/practice-problems/algorithm/reversed-linked-list-01b722df/" "**Reversed Linked List** (HackerEarth)" >}}
{{< link "https://www.hackerearth.com/practice/data-structures/linked-list/singly-linked-list/practice-problems/algorithm/remove-friends-5/" "**Remove Friends** (HackerEarth)" >}}

{{< /admonition >}}



<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-PFRLG5MZ6V"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-PFRLG5MZ6V');
</script>

