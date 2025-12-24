#include <stdio.h>
#include <stdlib.h>
struct node
{
    int data;
    struct node*next;
}*head=NULL;
struct node*create(int val)
{
    struct node*temp;
    temp=(struct node*)malloc(sizeof(struct node));
    temp->data=val;
    temp->next=NULL;
    return temp;
}
int count()
{
    struct node *temp;
    int i=1;
    temp=head;
    while(temp->next!=NULL)
    {
        temp=temp->next;
        i++;
    }
    return i;
}
void insert_beg(int val)
{
    struct node*newnode;
    newnode=create(val);
    if(head==NULL)
        head=newnode;
    else
    {
        newnode->next=head;
        head=newnode;
    }
}
void delbeg()
{
    struct node *temp;
    if(head!=NULL)
    {
        temp=head;
        head=temp->next;
        free(temp);
    }
}
void del_end()
{
    struct node *temp1,*temp2;
    temp1=head;
    while(temp1->next!=NULL)
    {
        temp2=temp1;
        temp1=temp1->next;
    }temp2->next=NULL;
    free(temp1);
}
void del_pos(int pos)
{
    struct node *temp1,*temp2;
    int i,c=0;
    i=count();
    if(pos==1)
        delbeg();
    else if(pos>i)
        printf("Position Invalid");
    else
    {
        temp1=head;
        while(c<pos-1 && temp1->next!=NULL)
        {
            temp2=temp1;
            temp1=temp1->next;
            c++;
        }temp2->next=temp1->next;
        free(temp1);
    }
}
void del_key(int key)
{
    struct node *temp1=head;
    struct node *temp2=NULL;
    if(temp1!=NULL && temp1->data==key)
    {
        head=temp1->next;
        free(temp1);
    printf("Element %d deleted",key);
    return;
    }
    while(temp1!=NULL && temp1->data!=key)
    {
        temp2=temp1;
        temp1=temp1->next;
    }
    if(temp1==NULL)
    {
        printf("Element not found");
        return;
    }temp2->next=temp1->next;
    free(temp1);
    printf("Element %d deleted",key);
}
void display()
{
    struct node*temp;
    if(head==NULL)
        printf("Empty");
    else
    {temp=head;
    while(temp->next!=NULL)
    {
        printf("%d ->",temp->data);
        temp=temp->next;
    }printf("%d",temp->data);
    }
}
void main()
{
    int value,pos,ch;
    while(1)
    {
        printf("\n1.Insert in the beggining\n");
        printf("2.Delete in beginning\n3.Delete in the ending\n");
        printf("4.Insert in a specific pos\n5.Delete value\n");
        printf("6.Display\n");
        printf("Enter your choice:");
        scanf("%d",&ch);
        switch(ch)
        {
            case 1:printf("Enter val:");
                scanf("%d",&value);
                insert_beg(value);break;
            case 2:delbeg();break;
            case 3:del_end();break;
            case 4:printf("Enter pos:");
                    scanf("%d",&pos);
                    del_pos(pos);break;
            case 5:printf("Enter val:");
                scanf("%d",&value);
                del_key(value);break;
            case 6:display();break;
            default:printf("Invalid choice\n");
        }
    }
}
