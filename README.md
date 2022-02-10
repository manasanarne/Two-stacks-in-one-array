# Two-stacks-in-one-array
#include<stdio.h>
#include<stdlib.h>
#define MAX 10
int a[MAX];
int top1=-1,top2=MAX;
void push1(int k1)
{
    if (top1+1==top2)
    {
        printf("stack overflow");
    }
    else
    {
    a[++top1]=k1;
    }
}
void push2(int k2)
{
    if (top1+1==top2)
    {
        printf("stack overflow");
    }
    else
    {
    top2=top2-1;
    a[top2]=k2;
    }
}
void pop1()
{
    int x;
    x=a[top1];
    top1=top1-1;
    printf("the popped element in stack1 is %d",x);
   
}
void pop2()
{
    int y;
    y=a[top2];
    top2=top2+1;
    printf("the popped element in stack2 is %d",y);
}
void display1()
{
    int i;
    for (i=0;i<=top1;i++)
    {
        printf("%d",a[i]);
    }
}
void display2()
{
    int j;
    for (j=top2;j<=MAX-1;j++)
    {
        printf("%d",a[j]);
    }
}
void main()
{
    int ch,k1,k2;
    while(1)
    {
        printf("enter ch:");
        scanf("%d",&ch);
        switch(ch)
        {
            case 1:printf("enter k1:");
                   scanf("%d",&k1);
                   push1(k1);
                   break;
            case 2:printf("enter k2:");
                   scanf("%d",&k2);
                   push2(k2);
                   break;
            case 3:pop1();
                   break;
            case 4:pop2();
                   break;
            case 5:display1();
                   break;
            case 6:display2();
                   break;
            case 7:exit(0);
             
        }
    }
}

OUTPUT:-
enter ch:1
enter k1:2
enter ch:1
enter k1:3
enter ch:1
enter k1:5
enter ch:1
enter k1:6
enter ch:3
the popped element in stack1 is 6
