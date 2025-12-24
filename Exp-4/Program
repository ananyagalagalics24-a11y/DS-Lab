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
};
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
void insert_end(int val)
{
    struct node*newnode,*temp;
    newnode=create(val);
    if(head!=NULL)
    {
        temp=head;
        while(temp->next!=NULL)
            temp=temp->next;
        temp->next=newnode;
    }
}
void display()
{
    struct node*temp;
    temp=head;
    while(temp->next!=NULL)
    {
        printf("%d->",temp->data);
        temp=temp->next;
    }printf("%d",temp->data);
}
void main()
{
    int value,pos,ch;
    while(1)
    {
        printf("\n1.Insert in the beggining\n");
        printf("2.Insert in the ending\n");
        printf("3.Insert in a specific pos\n");
        printf("4.Display\n");
        printf("Enter your choice:");
        scanf("%d",&ch);
        switch(ch)
        {
            case 1:printf("Enter val:");
                scanf("%d",&value);
                insert_beg(value);break;
            case 2:printf("Enter val:");
                scanf("%d",&value);
                insert_end(value);break;
            case 4:display();break;
            default:printf("Invalid choice\n");
        }
    }
}
