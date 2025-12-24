#include <stdio.h>
#define Size 5
int items[Size];
int front=-1,rear=-1;
int isFull()
{
    if((front==rear+1)||(front==0 && rear==Size-1))
        return 1;
    return 0;
}
int isEmpty()
{
    if(front==-1)return 1;
    return 0;
}
int deQueue()
{
    int ele;
    if(isEmpty())
    {
        printf("\nQueue is empty!!\n");
        return(-1);
    }
    else
    {
        ele=items[front];
        if(front==rear)
        {
            front=-1;
            rear=-1;
        }
        else
        {
            front=(front+1)%Size;
        }
        printf("\nDeleted element= %d\n",ele);
        return(ele);
    }
}
void enQueue(int ele)
{
    if(isFull())
        printf("\nQueue is full!!\n");
    else
    {
        if(front==-1)
            front=0;
        rear=(rear+1)%Size;
        items[rear]=ele;
        printf("\nInserted= %d",ele);
    }
}
void display()
{
    int i;
    if(isEmpty())
        printf("\nEmpty Queue\n");
    else
    {
        printf("\nItems= ");
        for(i=front;i!=rear;i=(i+1)%Size)
        {
            printf("%d",items[i]);
        }
        printf("%d",items[i]);
    }
}
int main()
{
    int option, val, del;
    do
    {
        printf("\n*****MAIN MENU*****");
        printf("\n1.Insert");
        printf("\n2.Delete");
        printf("\n3.Display");
        printf("\n4.Exit");
        printf("\nEnter your option: ");
        scanf("%d",&option);
        switch(option)
        {
            case 1:printf("\nEnter the number: ");
                    scanf("%d",&val);
                    enQueue(val);
                    break;
            case 2: del=deQueue();
                    printf("\nNumber deleted: %d",del);
                    break;
            case 3: display();break;
            case 4: exit(0);
        }
    }while(option!=4);
     return 0;
}
