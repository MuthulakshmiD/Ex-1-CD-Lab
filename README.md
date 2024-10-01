# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol is inserted into symbol table along with its memory address.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8.	Stop the program. 
# PROGRAM
```
#include<stdio.h>
#include<conio.h> 
#include<ctype.h> 
#include<malloc.h> 
#include<string.h> 
#include<math.h>
void main()
{
int i=0,j=0,x=0,n,flag=0; void *p,*add[5];
char ch,srch,b[15],d[15],c; 
printf("Enter the Expression terminated by $: ");
while((c=getchar())!='$')
{
b[i]=c; i++;
}
n=i-1;
printf("Given Expression:"); i=0;
while(i<=n)
{
printf("%c",b[i]); i++;
}
printf("\n Symbol Table\n"); printf("Symbol\taddr\ttype"); while(j<=n)
{
c=b[j]; if(isalpha(toascii(c)))
{
if(j==n)
{
p=malloc(c); add[x]=p;
d[x]=c;
printf("%c\t%d\tidentifier",c,p);
}
else
{
ch=b[j+1];
if(ch=='+'||ch=='-'||ch=='*'||ch=='=')
{
p=malloc(c); add[x]=p;
d[x]=c; printf("\n%c\t%d\tidentifier\n",c,p); x++;
}}} j++;
}
printf("\n The symbol is to be searched"); srch=getch();
for(i=0;i<=x;i++)
{
if(srch==d[i])
{
printf("\n Symbol Found"); printf("\n%c%s%d\n",srch,"@address",add[i]); flag=1;
}
}
if(flag==0)
printf("\nSymbol Not Found"); 
getch();
}
```
# OUTPUT
![Screenshot 2024-09-18 114557](https://github.com/user-attachments/assets/f78ebfed-4755-426d-bb45-0965c70356a0)
# RESULT
### The program to implement a symbol table is executed and the output is verified.
