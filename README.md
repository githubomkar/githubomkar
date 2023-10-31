Experiment No. 1
Aim: Implementation of stack using Array

#include<stdio.h>
int stack[100],choice,max,top,data,i;

int main()
{
    //clrscr();
    top=-1;
    printf("\n Enter the size of STACK[MAX=100]:");
    scanf("%d",&max);
    printf("\n\t STACK OPERATIONS USING ARRAY");
    printf("\n\t--------------------------------");
    printf("\n\t 1.PUSH\n\t 2.POP\n\t 3.DISPLAY\n\t 4.EXIT");
    do
    {
        printf("\n Enter the Choice:");
        scanf("%d",&choice);
        switch(choice)
        {
            case 1:
            {
                if(top>=max-1)
    {
        printf("\n\tSTACK is over flow");
        
    }
    else
    {
        printf(" Enter a value to be pushed:");
        scanf("%d",&data);
        top++;
        stack[top]=data;
    }
                break;
            }
            case 2:
            {
                if(top<=-1)
    {
        printf("\n\t Stack is under flow");
    }
    else
    {
        printf("\n\t The popped elements is %d",stack[top]);
        top--;
    }
                break;
            }
            case 3:
            {
               if(top>=0)
    {
        printf("\n The elements in STACK \n");
        for(i=top; i>=0; i--)
            printf("\n%d",stack[i]);
        printf("\n Press Next Choice");
    }
    else
    {
        printf("\n The STACK is empty");
    }
                break;
            }
            case 4:
            {
                printf("\n\t EXIT POINT ");
                break;
            }
            default:
            {
                printf ("\n\t Please Enter a Valid Choice(1/2/3/4)");
            }
                
        }
    }
    while(choice!=4);
    return 0;
}

EXPERIMENT NO-2
IMPLEMENTATION OF LINEAR QUEUE USING ARRAY

#include<stdio.h>
#define n 5
int main()
{
    int queue[n],ch=1,front=0,rear=0,i,j=1,x=n;
    printf("Queue using Array");
    printf("\n1.Insertion \n2.Deletion \n3.Display \n4.Exit");
    while(ch)
    {
        printf("\nEnter the Choice:");
        scanf("%d",&ch);
        switch(ch)
        {
        case 1:
            if(rear==x)
                printf("\n Queue is Full");
            else
            {
                printf("\n Enter no %d:",j++);
                scanf("%d",&queue[rear++]);
            }
            break;
        case 2:
            if(front==rear)
            {
                printf("\n Queue is empty");
            }
            else
            {
                printf("\n Deleted Element is %d",queue[front++]);
                x++;
            }
            break;
        case 3:
            printf("\nQueue Elements are:\n ");
            if(front==rear)
                printf("\n Queue is Empty");
            else
            {
                for(i=front; i<rear; i++)
                {
                    printf("%d",queue[i]);
                    printf("\n");
                }
                break;
            case 4:
                exit(0);
            default:
                printf("Wrong Choice: please see the options");
            }
        }
    }
    return 0;
}
OUTPUT:


EXPERIMENT No. 3
PROGRAM TO CONVERT INFIX TO POSTFIX EXPRESSION
#include<stdio.h>
#include<stdlib.h>
#include<ctype.h>
char stack[50];
int top = -1;
void push(char x)
{
    stack[++top] = x;
}
char pop()
{
    if(top == -1)
        return -1;
    else
        return stack[top--];
}
int priority(char x)
{
    if(x == '(')
        return 0;
    if(x == '+' || x == '-')
        return 1;
    if(x == '*' || x == '/')
        return 2;
    return 0;
}

int main()
{
    char exp[100];
    char *e, x;
    printf("Enter the expression : ");
    scanf("%s",exp);
    printf("\n");
    e = exp;
    
    while(*e != '\0')
    {
        if(isalnum(*e))
            printf("%c ",*e);
        else if(*e == '(')
            push(*e);
        else if(*e == ')')
        {
            while((x = pop()) != '(')
                printf("%c ", x);
        }
        else
        {
            while(priority(stack[top]) >= priority(*e))
                printf("%c ",pop());
            push(*e);
        }
        e++;
    }
    
    while(top != -1)
    {
        printf("%c ",pop());
    }return 0;
}





OUTPUT:

EXPERIMENT No. 4
PROGRAM TO EVALUATE POSTFIX EXPRESSION
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<math.h>
#define SIZE 100
int top=-1;
int stack[SIZE];
void push(int item);
int pop();
int is_operator(char symbol);
void posteval(char *);
void main()
{
    char postfix_exp[SIZE];
    int item;
    printf("\nEnter the arithmetic expression in Postfix notation:\n");
    gets(postfix_exp);
    posteval(postfix_exp);
}
void posteval(char postfix_exp[SIZE])
{
    int i, j;
    int x, y, result, value;
    j=0;
    for(i=0; postfix_exp [i]!='\0';i++)
    {
        if (isdigit (postfix_exp[i]) )
        {
            push (postfix_exp[i]-48);
        }
        else if(is_operator(postfix_exp[i]))
        {
           y = pop();
           x = pop();
           switch (postfix_exp[i])
           {
              case '+':
                       result = x + y;
                       break;
              case '-':
                       result = x - y;
                       break;
              case '*':
                       result = x * y;
                       break;
              case '/':
                       result = x / y;
                       break;
              case '^':
                       result = pow(x,y);
                       break;
            }
            push(result);
        }
        else
        {
            printf("\nInvalid postfix expression\n");
            exit(0);
        }
    }
    value=pop();
    printf("\nValue of the postfix expression is %d", value);
}
void push(int item)
{
    if(top==SIZE-1)
    {
        printf("\nStack Full");
    }
    else
    {
        top=top+1;
        stack[top]=item;
    }
}
int pop()
{
    int item;
    if(top==-1)
    {
        printf("\nStack Empty");
    }
    else
    {
        item=stack[top];
        top=top-1;
    }
    return(item);
}
int is_operator(char symbol)
{
    if(symbol=='^'||symbol=='*'||symbol=='/'||symbol=='+'||symbol=='-')
    {
        return 1;
    }
    else
    {
        return 0;
    }
}

OUTPUT:


Exp No. 6
To implement Singly linked list

#include<stdio.h>  
#include<stdlib.h>  
struct node   
{  
    int data;  
    struct node *next;   
};  
struct node *head;  
  
void beginsert ();   
void lastinsert ();  
void randominsert();  
void begin_delete();  
void last_delete();  
void random_delete();  
void display();  
void search();  
void main ()  
{  
    int choice =0;  
    while(choice != 9)   
    {  
        printf("\n\n*********Main Menu*********\n");  
        printf("\nChoose one option from the following list ...\n");  
        printf("\n===============================================\n");  
        printf("\n1.Insert in begining\n2.Insert at last\n3.Insert at any random location\n4.Delete from Beginning\n 5.Delete from last\n6.Delete node after specified location\n7.Search for an element\n8.Show\n9.Exit\n");  
        printf("\nEnter your choice?\n");         
        scanf("\n %d",&choice);  
        switch(choice)  
        {  
            case 1:  
            beginsert();      
            break;  
            case 2:  
            lastinsert();         
            break;  
            case 3:  
            randominsert();       
            break;  
            case 4:  
            begin_delete();       
            break;  
            case 5:  
            last_delete();        
            break;  
            case 6:  
            random_delete();          
            break;  
          /*  case 7:  
            search();         
            break;  */
            case 8:  
            display();        
            break;  
            case 9:  
            exit(0);  
            break;  
            default:  
            printf("Please enter valid choice..");  
        }  
    }  
}  
void beginsert()  
{  
    struct node *newnode;  
    int item;  
    newnode = (struct node *) malloc(sizeof(struct node *));  
    if(newnode == NULL)  
    {  
        printf("\nOVERFLOW");  
    }  
    else  
    {  
        printf("\nEnter value\n");    
        scanf("%d",&item);    
        newnode->data = item;  
        newnode->next = head;  
        head = newnode;  
        printf("\nNode inserted");  
    }  
      
}  
void lastinsert()  
{  
    struct node *newnode,*temp;  
    int item;     
    newnode = (struct node*)malloc(sizeof(struct node));      
    if(newnode == NULL)  
    {  
        printf("\nOVERFLOW");     
    }  
    else  
    {  
        printf("\nEnter value?\n");  
        scanf("%d",&item);  
        newnode->data = item;  
        if(head == NULL)  
        {  
            newnode -> next = NULL;  
            head = newnode;  
            printf("\nNode inserted");  
        }  
        else  
        {  
            temp = head;  
            while (temp -> next != NULL)  
            {  
                temp = temp -> next;  
            }  
            temp->next = newnode;  
            newnode->next = NULL;  
            printf("\nNode inserted");  
          
        }  
    }  
}  
void randominsert()  
{  
    int i,loc,item;   
    struct node *newnode, *temp;  
    newnode = (struct node *) malloc (sizeof(struct node));  
    if(newnode == NULL)  
    {  
        printf("\nOVERFLOW");  
    }  
    else  
    {  
        printf("\nEnter element value");  
        scanf("%d",&item);  
        newnode->data = item;  
        printf("\nEnter the location after which you want to insert ");  
        scanf("\n%d",&loc);  
        temp=head;  
        for(i=0;i<loc;i++)  
        {  
            temp = temp->next;  
            if(temp == NULL)  
            {  
                printf("\ncan't insert\n");  
                return;  
            }  
          
        }  
        newnode ->next = temp ->next;   
        temp ->next = newnode;   
        printf("\nNode inserted");  
    }  
}  
void begin_delete()  
{  
    struct node *temp;  
    if(head == NULL)  
    {  
        printf("\nList is empty\n");  
    }  
    else   
    {  
        temp = head;  
        head = temp->next;  
        free(temp);  
        printf("\nNode deleted from the beginning ...\n");  
    }  
}  
void last_delete()  
{  
    struct node *temp1,*temp2;  
    if(head == NULL)  
    {  
        printf("\n list is empty");  
    }  
    else if(head -> next == NULL)  
    {  
        head = NULL;  
        free(head);  
        printf("\nOnly node of the list deleted ...\n");  
    }  
          
    else  
    {  
        temp1 = head;   
        while(temp1->next != NULL)  
        {  
            temp2 = temp1;  
            temp1 = temp1 ->next;  
        }  
        temp2->next = NULL;  
        free(temp1);  
        printf("\nDeleted Node from the last ...\n");  
    }     
}  
void random_delete()  
{  
    struct node *temp1,*temp2;  
    int loc,i;    
    printf("\n Enter the location of the node after which you want to perform deletion \n");  
    scanf("%d",&loc);  
    temp1=head;  
    for(i=0;i<loc;i++)  
    {  
        temp2 = temp1;       
        temp1 = temp1->next;  
              
        if(temp1 == NULL)  
        {  
            printf("\nCan't delete");  
            return;  
        }  
    }  
    temp2 ->next = temp1 ->next;  
    free(temp1);  
    printf("\nDeleted node %d ",loc+1);  
}  

void display()  
{  
    struct node *temp;  
    temp = head;   
    if(temp == NULL)  
    {  
        printf("Nothing to print");  
    }  
    else  
    {  
        printf("\nprinting values . . . . .\n");   
        while (temp!=NULL)  
        {  
            printf("\n%d",temp->data);  
            temp = temp -> next;  
        }  
    }  
}     
                




EXP No. 7

To implement Circular Linked List


#include<stdio.h>  
#include<stdlib.h>  
struct node   
{  
	int data;  
	struct node *next;   
};  
struct node *head=NULL;  
 
void beginsert ();   
void lastinsert ();  
void randominsert();  
void begin_delete();  
void last_delete();  
void random_delete();  
void display();  
void search();  
void main ()  
{  
	int choice =0;  
	while(choice != 9)   
	{  
    	printf("\n\n*********Main Menu*********\n");  
    	printf("\nChoose one option from the following list ...\n");  
    	printf("\n===============================================\n");  
    	printf("\n1.Insert in begining\n2.Insert at last\n3.Insert at any random location\n4.Delete from Beginning\n 5.Delete from last\n6.Delete node after specified location\n7.Search for an element\n8.Show\n9.Exit\n");  
    	printf("\nEnter your choice?\n");    	 
    	scanf("\n %d",&choice);  
    	switch(choice)  
    	{  
        	case 1:  
        	beginsert(); 	 
        	break;  
        	case 2:  
        	lastinsert();    	 
        	break;  
        	case 3:  
        	randominsert();  	 
        	break;  
        	case 4:  
        	begin_delete();  	 
        	break;  
        	case 5:  
        	last_delete();   	 
        	break;  
        	case 6:  
        	random_delete();     	 
        	break;  
      	/*  case 7:  
        	search();    	 
        	break;  */
        	case 8:  
        	display();   	 
        	break;  
        	case 9:  
        	exit(0);  
        	break;  
        	default:  
        	printf("Please enter valid choice..");  
    	}  
	}  
}  
void beginsert()  
{  
	struct node *newnode, *temp;  
	int item;  
	newnode = (struct node *) malloc(sizeof(struct node *));  
  /* if(newnode == NULL)  
	{  
    	printf("\nOVERFLOW");  
	}
	else  
	{ */
	printf("\nEnter value\n");    
	scanf("%d",&item);    
	newnode->data = item;
 	if(head==NULL)
	{
	head=newnode;
	newnode->next=head;
	printf("\nNode inserted");  
	}
	else
	{  
   	 
    	temp=head;
    	while(temp->next!=head)
    	{
    	temp=temp->next;
    	}
    	newnode->next = head;
     	temp->next=newnode;
    	head = newnode;  
    	printf("\nNode inserted");  
	}  
 	 
}  
void lastinsert()  
{  
	struct node *newnode,*temp;  
	int item;	 
	newnode = (struct node*)malloc(sizeof(struct node)); 	 
	if(newnode == NULL)  
	{  
    	printf("\nOVERFLOW");	 
	}  
	else  
	{
    	printf("\nEnter value:\n");  
    	scanf("%d",&item);  
    	newnode->data = item;  
    	if(head == NULL)  
    	{  
       	 
        	head = newnode;
        	newnode -> next = head;  
        	printf("\nNode inserted");  
     	}
    	else  
    	{  
        	temp = head;  
        	while (temp -> next != head)  
        	{  
            	temp = temp -> next;  
        	}  
       	 
        	newnode->next = head;
        	temp->next = newnode;   
        	printf("\nNode inserted");  
     	 
    	}  
	}  
 }
void randominsert()  
{  
	int i,loc,item;   
	struct node *newnode, *temp;  
	newnode = (struct node *) malloc (sizeof(struct node));  
	if(newnode == NULL)  
	{  
    	printf("\nOVERFLOW");  
	}  
	else  
	{  
    	printf("\nEnter element value");  
    	scanf("%d",&item);  
    	newnode->data = item;  
    	printf("\nEnter the location after which you want to insert ");  
    	scanf("\n%d",&loc);  
    	temp=head;  
    	for(i=0;i<loc;i++)  
    	{  
        	temp = temp->next;  
        	if(temp == NULL)  
        	{  
            	printf("\ncan't insert\n");  
            	return;  
        	}  
     	 
    	}  
    	newnode ->next = temp ->next;   
    	temp ->next = newnode;   
    	printf("\nNode inserted");  
	}  
}  
void begin_delete()  
{  
	struct node *temp;  
	if(head == NULL)  
	{  
    	printf("\nList is empty\n");  
	}
	else if(head->next==head)
	{
	temp=head;
	head=NULL;
	free(temp);
	}
	else   
	{  
    	temp = head;  
    	while(temp->next!=head)
    	{
    	temp=temp->next;
    	}
    	temp->next=head->next;
    	free(head);
     	head = temp->next;  
    	printf("\nNode deleted from the begining ...\n");  
	}  
}  
void last_delete()  
{  
	struct node *temp1,*temp2,*temp;  
	if(head == NULL)  
	{  
    	printf("\nlist is empty");  
	}  
	else if(head->next==head)
	{
	temp=head;
	head=NULL;
	free(temp);
 	printf("\nOnly node of the list deleted ...\n");
  	}  
	else  
	{  
    	temp1 = head;
    	temp2=head;  
    	while(temp1->next != head)  
    	{  
        	temp2 = temp1;  
        	temp1 = temp1 ->next;  
    	}  
    	temp2->next = head;  
    	free(temp1);  
    	printf("\nDeleted Node from the last ...\n");  
	}	 
}  
void random_delete()  
{  
	struct node *temp1,*temp2;  
	int loc,i;    
	printf("\n Enter the location of the node after which you want to perform deletion \n");  
	scanf("%d",&loc);  
	temp1=head;  
	for(i=0;i<loc;i++)  
	{  
    	temp2 = temp1;  	 
    	temp1 = temp1->next;  
         	 
    	if(temp1 == NULL)  
    	{  
        	printf("\nCan't delete");  
        	return;  
    	}  
	}  
	temp2 ->next = temp1 ->next;  
	free(temp1);  
	printf("\nDeleted node %d ",loc+1);  
}  

void display()  
{  
	struct node *temp;
	int i;
	temp = head;
  	 
	if(head == NULL)  
	{  
    	printf("Nothing to print");  
	}  
	else  
	{  
    	printf("\nprinting values . . . . .\n");   
       	printf("\n%d",temp->data);
    	do
    	{  
 	 
    	temp = temp -> next;
     	printf("\n%d",temp->data);	 
    	}  while (temp->next!=head) ;
	}  
}	 
           	 
























Experiment No.  9

Aim : To implement the Binary Search Tree 

#include <stdio.h>
#include <stdlib.h>
 
// structure of a node
struct node
{
    int data;
    struct node *left;
    struct node *right;
};
 
// globally initialized root pointer
struct node *root = NULL;
 
// function prototyping
struct node *create_node(int);
void insert(int);
struct node *delete (struct node *, int);
int search(int);
void inorder(struct node *);
void postorder();
void preorder();
struct node *smallest_node(struct node *);
struct node *largest_node(struct node *);
int get_data();
 
int main()
{
    int userChoice;
    int userActive = 'Y';
    int data;
    struct node* result = NULL;
 
    while (userActive == 'Y' || userActive == 'y')
    {
        printf("\n\n------- Binary Search Tree ------\n");
        printf("\n1. Insert");
        printf("\n2. Delete");
        printf("\n3. Search");
        printf("\n4. Get Larger Node Data");
        printf("\n5. Get smaller Node data");
        printf("\n\n-- Traversals --");
        printf("\n\n6. Inorder ");
        printf("\n7. Post Order ");
        printf("\n8. Pre Oder ");
        printf("\n9. Exit");
 
        printf("\n\nEnter Your Choice: ");
        scanf("%d", &userChoice);
        printf("\n");
 
        switch(userChoice)
        {
            case 1:
                data = get_data();
                insert(data);
                break;
 
            case 2:
                data = get_data();
                root = delete(root, data);
                break;
 
            case 3:
                data = get_data();
                if (search(data) == 1)
                {
                    printf("\nData was found!\n");
                }
                else
                {
                    printf("\nData does not found!\n");
                }
                break;
 
            case 4:
                result = largest_node(root);
                if (result != NULL)
                {
                    printf("\nLargest Data: %d\n", result->data);
                }
                break;
 
            case 5:
                result = smallest_node(root);
                if (result != NULL)
                {
                    printf("\nSmallest Data: %d\n", result->data);
                }
                break;
 
            case 6:
                inorder(root);
                break;
 
            case 7:
                postorder(root);
                break;
 
            case 8:
                preorder(root);
                break;
 
            case 9:
                printf("\n\nProgram was terminated\n");
                break;
 
            default:
                printf("\n\tInvalid Choice\n");
                break;
        }
 
//        printf("\n__________\nDo you want to continue? ");
//        fflush(stdin);
//        scanf(" %c", &userActive);
    }
 
    return 0;
}
 
// creates a new node
struct node *create_node(int data)
{
    struct node *new_node = (struct node *)malloc(sizeof(struct node));
 
    if (new_node == NULL)
    {
        printf("\nMemory for new node can't be allocated");
        return NULL;
    }
 
    new_node->data = data;
    new_node->left = NULL;
    new_node->right = NULL;
 
    return new_node;
}
 
// inserts the data in the BST
void insert(int data)
{
    struct node *new_node = create_node(data);
 
    if (new_node != NULL)
    {
        // if the root is empty then make a new node as the root node
        if (root == NULL)
        {
            root = new_node;
            printf("\n* node having data %d was inserted\n", data);
            return;
        }
 
        struct node *temp = root;
        struct node *prev = NULL;
 
        // traverse through the BST to get the correct position for insertion
        while (temp != NULL)
        {
            prev = temp;
            if (data > temp->data)
            {
                temp = temp->right;
            }
            else
            {
                temp = temp->left;
            }
        }
 
        // found the last node where the new node should insert
        if (data > prev->data)
        {
            prev->right = new_node;
        }
        else
        {
            prev->left = new_node;
        }
 
        printf("\n* node having data %d was inserted\n", data);
    }
}
 
// deletes the given key node from the BST
struct node *delete (struct node *root, int key)
{
    if (root == NULL)
    {
        return root;
    }
    if (key < root->data)
    {
        root->left = delete (root->left, key);
    }
    else if (key > root->data)
    {
        root->right = delete (root->right, key);
    }
    else
    {
        if (root->left == NULL)
        {
            struct node *temp = root->right;
            free(root);
            return temp;
        }
        else if (root->right == NULL)
        {
            struct node *temp = root->left;
            free(root);
            return temp;
        }
        struct node *temp = smallest_node(root->right);
        root->data = temp->data;
        root->right = delete (root->right, temp->data);
    }
    return root;
 
}
 
// search the given key node in BST
int search(int key)
{
    struct node *temp = root;
 
    while (temp != NULL)
    {
        if (key == temp->data)
        {
            return 1;
        }
        else if (key > temp->data)
        {
            temp = temp->right;
        }
        else
        {
            temp = temp->left;
        }
    }
    return 0;
}
 
// finds the node with the smallest value in BST
struct node *smallest_node(struct node *root)
{
    struct node *curr = root;
    while (curr != NULL && curr->left != NULL)
   {
        curr = curr->left;
    }
    return curr;
}
 
// finds the node with the largest value in BST
struct node *largest_node(struct node *root)
{
    struct node *curr = root;
    while (curr != NULL && curr->right != NULL)
    {
        curr = curr->right;
    }
    return curr;
}
 
// inorder traversal of the BST
void inorder(struct node *root)
{
    if (root == NULL)
    {
        return;
    }
    inorder(root->left);
    printf("%d ",  root->data);
    inorder(root->right);
}
 
// preorder traversal of the BST
void preorder(struct node *root)
{
    if (root == NULL)
    {
        return;
    }
    printf("%d ", root->data);
    preorder(root->left);
    preorder(root->right);
}
 
// postorder travsersal of the BST
void postorder(struct node *root)
{
    if (root == NULL)
    {
        return;
    }
    postorder(root->left);
    postorder(root->right);
    printf("%d ", root->data);
}
 
// getting data from the user
int get_data()
{
    int data;
    printf("\nEnter Data: ");
    scanf("%d", &data);
    return data;
}
















Experiment:- 10
Implement Graph Traversal Techniques-

1)DEPTH FIRST SEARCH
// DFS algorithm in C

#include <stdio.h>
#include <stdlib.h>

struct node {
  int vertex;
  struct node* next;
};

struct node* createNode(int v);

struct Graph {
  int numVertices;
  int* visited;

  // We need int** to store a two dimensional array.
  // Similary, we need struct node** to store an array of Linked lists
  struct node** adjLists;
};

// DFS algo
void DFS(struct Graph* graph, int vertex) {
  struct node* adjList = graph->adjLists[vertex];
  struct node* temp = adjList;

  graph->visited[vertex] = 1;
  printf("Visited %d \n", vertex);

  while (temp != NULL) {
    int connectedVertex = temp->vertex;

    if (graph->visited[connectedVertex] == 0) {
      DFS(graph, connectedVertex);
    }
    temp = temp->next;
  }
}

// Create a node
struct node* createNode(int v) {
  struct node* newNode = malloc(sizeof(struct node));
  newNode->vertex = v;
  newNode->next = NULL;
  return newNode;
}

// Create graph
struct Graph* createGraph(int vertices) {
  struct Graph* graph = malloc(sizeof(struct Graph));
  graph->numVertices = vertices;

  graph->adjLists = malloc(vertices * sizeof(struct node*));

  graph->visited = malloc(vertices * sizeof(int));

  int i;
  for (i = 0; i < vertices; i++) {
    graph->adjLists[i] = NULL;
    graph->visited[i] = 0;
  }
  return graph;
}

// Add edge
void addEdge(struct Graph* graph, int src, int dest) {
  // Add edge from src to dest
  struct node* newNode = createNode(dest);
  newNode->next = graph->adjLists[src];
  graph->adjLists[src] = newNode;

  // Add edge from dest to src
  newNode = createNode(src);
  newNode->next = graph->adjLists[dest];
  graph->adjLists[dest] = newNode;
}

// Print the graph
void printGraph(struct Graph* graph) {
  int v;
  for (v = 0; v < graph->numVertices; v++) {
    struct node* temp = graph->adjLists[v];
    printf("\n Adjacency list of vertex %d\n ", v);
    while (temp) {
      printf("%d -> ", temp->vertex);
      temp = temp->next;
    }
    printf("\n");
  }
}

int main() {
  struct Graph* graph = createGraph(4);
  addEdge(graph, 0, 1);
  addEdge(graph, 0, 2);
  addEdge(graph, 1, 2);
  addEdge(graph, 2, 3);

  printGraph(graph);

  DFS(graph, 2);

  return 0;
}


2)BREADTH FIRST SEARCH

// BFS algorithm in C

#include <stdio.h>
#include <stdlib.h>
#define SIZE 40

struct queue {
  int items[SIZE];
  int front;
  int rear;
};

struct queue* createQueue();
void enqueue(struct queue* q, int);
int dequeue(struct queue* q);
void display(struct queue* q);
int isEmpty(struct queue* q);
void printQueue(struct queue* q);

struct node {
  int vertex;
  struct node* next;
};

struct node* createNode(int);

struct Graph {
  int numVertices;
  struct node** adjLists;
  int* visited;
};

// BFS algorithm
void bfs(struct Graph* graph, int startVertex) {
  struct queue* q = createQueue();

  graph->visited[startVertex] = 1;
  enqueue(q, startVertex);

  while (!isEmpty(q)) {
    printQueue(q);
    int currentVertex = dequeue(q);
    printf("Visited %d\n", currentVertex);

    struct node* temp = graph->adjLists[currentVertex];

    while (temp) {
      int adjVertex = temp->vertex;

      if (graph->visited[adjVertex] == 0) {
        graph->visited[adjVertex] = 1;
        enqueue(q, adjVertex);
      }
      temp = temp->next;
    }
  }
}

// Creating a node
struct node* createNode(int v) {
  struct node* newNode = malloc(sizeof(struct node));
  newNode->vertex = v;
  newNode->next = NULL;
  return newNode;
}

// Creating a graph
struct Graph* createGraph(int vertices) {
  struct Graph* graph = malloc(sizeof(struct Graph));
  graph->numVertices = vertices;

  graph->adjLists = malloc(vertices * sizeof(struct node*));
  graph->visited = malloc(vertices * sizeof(int));

  int i;
  for (i = 0; i < vertices; i++) {
    graph->adjLists[i] = NULL;
    graph->visited[i] = 0;
  }

  return graph;
}

// Add edge
void addEdge(struct Graph* graph, int src, int dest) {
  // Add edge from src to dest
  struct node* newNode = createNode(dest);
  newNode->next = graph->adjLists[src];
  graph->adjLists[src] = newNode;

  // Add edge from dest to src
  newNode = createNode(src);
  newNode->next = graph->adjLists[dest];
  graph->adjLists[dest] = newNode;
}

// Create a queue
struct queue* createQueue() {
  struct queue* q = malloc(sizeof(struct queue));
  q->front = -1;
  q->rear = -1;
  return q;
}

// Check if the queue is empty
int isEmpty(struct queue* q) {
  if (q->rear == -1)
    return 1;
  else
    return 0;
}

// Adding elements into queue
void enqueue(struct queue* q, int value) {
  if (q->rear == SIZE - 1)
    printf("\nQueue is Full!!");
  else {
    if (q->front == -1)
      q->front = 0;
    q->rear++;
    q->items[q->rear] = value;
  }
}

// Removing elements from queue
int dequeue(struct queue* q) {
  int item;
  if (isEmpty(q)) {
    printf("Queue is empty");
    item = -1;
  } else {
    item = q->items[q->front];
    q->front++;
    if (q->front > q->rear) {
      printf("Resetting queue ");
      q->front = q->rear = -1;
    }
  }
  return item;
}

// Print the queue
void printQueue(struct queue* q) {
  int i = q->front;

  if (isEmpty(q)) {
    printf("Queue is empty");
  } else {
    printf("\nQueue contains \n");
    for (i = q->front; i < q->rear + 1; i++) {
      printf("%d ", q->items[i]);
    }
  }
}

int main() {
  struct Graph* graph = createGraph(6);
  addEdge(graph, 0, 1);
  addEdge(graph, 0, 2);
  addEdge(graph, 1, 2);
  addEdge(graph, 1, 4);
  addEdge(graph, 1, 3);
  addEdge(graph, 2, 4);
  addEdge(graph, 3, 4);

  bfs(graph, 0);

  return 0;
}

OUTPUT:








