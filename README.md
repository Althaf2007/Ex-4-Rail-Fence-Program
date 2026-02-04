# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include <stdio.h>
#include <string.h>

void rail(char *t,int r,int d)
{
int l=strlen(t),i,j,k=0,dir=1,row=0; 
char a[r][l];
for(i=0;i<r;i++)for(j=0;j<l;j++)a[i][j]='\n';
for(i=0;i<l;i++){a[row][i]=d?'*':t[i]; 
row+=dir; 
if(row==0||row==r-1)dir=-dir;}
if(d){for(i=0;i<r;i++)for(j=0;j<l;j++)if(a[i][j]=='*')a[i][j]=t[k++];
}
row=0;dir=1;
for(i=0;i<l;i++){t[i]=a[row][i];
row+=dir; if(row==0||row==r-1)dir=-dir;
}
}
int main()
{
char m[50]; int r;
printf("Enter message: "); scanf(" %[^\n]",m);
printf("Rails: "); scanf("%d",&r);
rail(m,r,0); printf("Encrypted: %s\n",m);
rail(m,r,1); printf("Decrypted: %s\n",m);
}
}
```
# OUTPUT

<img width="1742" height="933" alt="Screenshot 2026-02-04 091730" src="https://github.com/user-attachments/assets/4c81a595-3157-47e9-b36e-2b98461f03e5" />

# RESULT

Thus to write a C program to implement the rail fence transposition technique has been done successfully.
