# Program-of-affine-cipher-plaintext-in-lower-case-ciphertext-in-upper-case-Bruteforce-attack
Program of affine cipher in c
#include<stdio.h>
#include<string.h>
void encryption()
{char str[100];
int i,n,flag,j,p[100],c[100],key1,key2;
 printf("enter plain text\n");
 fflush(stdin);
gets(str);
n=strlen(str);
for(i=0;str[i]!='\0';i++)
{

if(str[i]>='a'&&str[i]<='z')
 flag=0;
else
    if(str[i]==' ')
    {j=i;
     while(j<=n-1)
       {  str[j]=str[j+1];
          j++;
        }
        n--;
        flag=0;
    }
else
{  flag=111;
    break;
}
}
if(flag==111)
{ printf("enter plain text\n");
fflush(stdin);
gets(str);
}
if(str[i]==' ')
    {j=i;
     while(j<=n-1)
       {  str[j]=str[j+1];
          j++;
        }
        n--;
        flag=0;
    }
printf("enter key value1\n");
scanf("%d",&key1);
if(key1>25)
key1=key1%26;
printf("enter key value2\n");
scanf("%d",&key2);
if(key2>25)
key2=key2%26;
for(i=0;str[i]!='\0';i++)
{
c[i]=((str[i]-97)*key1+key2)%26;
}
printf("cipher text\n");
for(i=0;str[i]!='\0';i++)
{ c[i]=c[i]+97-32;
printf("%c",c[i]);
}
}

void decryption()
{char str[100];
int i,n,flag,j,p[100],c[100],key1,key2;
 printf("enter cipher text\n");
 fflush(stdin);
gets(str);
n=strlen(str);
for(i=0;str[i]!='\0';i++)
{

if(str[i]>='A'&&str[i]<='Z')
 flag=0;
else
    if(str[i]==' ')
    {j=i;
     while(j<=n-1)
       {  str[j]=str[j+1];
          j++;
        }
        n--;
        flag=0;
    }
else
{  flag=111;
    break;
}
}
if(flag==111)
{ printf("enter cipher text\n");
fflush(stdin);
gets(str);
}
if(str[i]==' ')
    {j=i;
     while(j<=n-1)
       {  str[j]=str[j+1];
          j++;
        }
        n--;
        flag=0;
    }

printf("enter key value1\n");
scanf("%d",&key1);
if(key1>25)
key1=key1%26;
printf("enter key value2\n");
scanf("%d",&key2);
if(key2>25)
key2=key2%26;
j=1;
while((key1*j)%26!=1)
j++;
key1=j;
printf("%d",key1);
for(i=0;str[i]!='\0';i++)
{ 
c[i]=((str[i]-65-key2)*key1)%26;
if(c[i]<0)
c[i]=c[i]+26;
}
printf("cipher text\n");
for(i=0;str[i]!='\0';i++)
{ c[i]=c[i]+97;
printf("%c",c[i]);
}
}


void bruteforce()
{int key3,flag,i,n,key1,p[100],ct[100],j,key2,c[100],bogus,a[100];
char str[100],c1[100];
printf("enter plain text\n");
fflush(stdin);
gets(str);
n=strlen(str);
for(i=0;str[i]!='\0';i++)
{

if(str[i]>='a'&&str[i]<='z')
 flag=0;
else
    if(str[i]==' ')
    {j=i;
     while(j<=n-1)
       {  str[j]=str[j+1];
          j++;
        }
        n--;
        flag=0;
    }
else
{  flag=111;
    break;
}
}
if(flag==111)
{ printf("enter plain text\n");
fflush(stdin);
gets(str);
}
if(str[i]==' ')
    {j=i;
     while(j<=n-1)
       {  str[j]=str[j+1];
          j++;
        }
        n--;
        flag=0;
    }

printf("enter cipher text\n");
fflush(stdin);
gets(c1);
printf("enter bogus length\n");
scanf("%d",&bogus);
n=strlen(c1);
for(i=0;c1[i]!='\0';i++)
{

if(c1[i]>='A'&&c1[i]<='Z')
 flag=0;
else
    if(c1[i]==' ')
    {j=i;
     while(j<=n-1)
       {  c1[j]=c1[j+1];
          j++;
        }
        n--;
        flag=0;
    }
else
{  flag=111;
    break;
}
}
if(flag==111)
{ printf("enter cipher text\n");
fflush(stdin);
gets(c1);
}
if(c1[i]==' ')
    {j=i;
     while(j<=n-1)
       {  c1[j]=c1[j+1];
          j++;
        }
        n--;
        flag=0;
    }

printf("enter key value1\n");
scanf("%d",&key1);
if(key1>25)
key1=key1%26;
printf("enter key value2\n");
scanf("%d",&key2);
if(key2>25)
key2=key2%26;
for(i=0;str[i]!='\0';i++)
{
c[i]=((str[i]-97)*key1+key2)%26;
}
for(i=0;str[i]!='\0';i++)
{ c[i]=c[i]+97-32;
printf("%c",c[i]);
}

key3=bogus-1;
i=bogus;
while(i<n-bogus)
{ if(c1[i]==c[i])
{
key3++;
}
i++;
}
printf("matches string at position=%d",key3);

}
int main()
{ int ch;
printf("enter choice:\n1.encryption\n2.decryption\n3.bruteforce\n4. exit\n");
scanf("%d",&ch);
switch(ch)
{ case 1: encryption();
case 2: decryption();
case 3: bruteforce();
default : break;
}
 return 0;
}
 
