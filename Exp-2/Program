#include<stdio.h>
#include<ctype.h>
#define MAX 50
char stack[MAX];
int top=-1;
void push(char c){
    stack[++top]=c;
}
char pop()
{
    if (top==-1){
        printf("stack underflow");
        return '\0';
    }
    else{
        return stack[top--];

    }
}
int precedence(char c){
    if (c=='*' || c=='/'){
        return 2;
    }
    if (c=='+' || c=='-'){
        return 1;
    }
    return 0;
}
void infixtopostfix(char infix[], char postfix[]){
    int k=0;
    for (int i=0;infix[i]!='\0';i++){
        char c= infix[i];
        if (isalpha(c)){
            postfix[k]=c;
            k++;
        }
        else if(c=='('){
               push(c);
    }
    else if(c==')'){
    while (top!=-1 && stack[top]!='('){
            postfix[k]=pop();
            k++;
           }
           pop();
    }
    else{
            while(top!=-1 && precedence(stack[top])>=precedence(c)){
                postfix[k]=pop();
                k++;
            }
            push(c);
    }
    }
   while(top!=-1){
        postfix[k]=pop();
            k++;
    }
   postfix[k]='\0';
}

int main()
{
    char infix[MAX],postfix[MAX];
    printf("enter infix expression:");
    scanf("%s",infix);
    infixtopostfix(infix,postfix);
    printf("postfix expression:%s",postfix);

    return 0;
}
