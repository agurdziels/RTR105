# 5.LD statistics

### Uzrakstītais kods
```
#include<stdio.h>
#include<string.h>

void main()
{
 char str1[100], str2[100], i=0, moda=0, x=0, min=0, max=0, j=0, buf=0;
 long int sk=0;
 float vid=0, med=0;

 printf("Ievadi simbolu rindu: ");
 scanf("%[^\n]s", str1);
 strcpy(str2,str1);
 
 sk = strlen(str1);
 for (i=0;i < sk-1;i++)
 {
  for (j=i+1; j < sk;j++)
  {
   if (str2[i] > str2[j])
   {
    buf = str2[i];
    str2[i] = str2[j];
    str2[j] = buf;
   }
  }
 }
 
 if (sk%2 == 1)
 
 med = str2[sk/2];

 if (sk%2 == 0)
 {
   med = (str2[sk/2-1]+str2[sk/2])/2.0;
 }
 
 max=str2[j-1];
 min=str2[0];
 
 printf("\nSimbolu skaits rindā: %ld\n",sk); 
 printf("Ievaditie simboli alfabēta kārtībā: %s\n",str2);
 printf("Sakārtoto simbolu ASCII vērtības: ");
 
 for (i=0;str1[i] != '\0';i++)
    {
     x=str1[i];
    vid+=x;
    printf("%d ",str2[i]);
    }
    vid/=sk;
 
 printf("\n\nMin vērtība: %d\n",min);
 printf("Max vērtība: %d\n",max);
 printf("Vidēja vērtība: %.2f\n",vid);
 printf("\nMediana: %.2f\n",med);
 
 j=0;
 for (i=0;sk > i ;i++)
 {
    if (str2[i] == str2[i+1])
        j++;
    else if (str2[i] != str2[i+1])
        if(j > moda)
        {
        moda = j;
        j=0;
        }
 }
 
 j=0;
 for (i=0;sk > i ;i++)
 {
    if (str2[i] == str2[i+1])
        j++;
    else if (str2[i] != str2[i+1])
        {
        if (moda==j)
            {
            printf("Moda: %d\n", str2[i]);
            }
        j=0;
        }
 }
 
}
```
### Rezultāts
![rezultats5 1](https://user-images.githubusercontent.com/90239365/149633652-5bb76721-df92-4021-9826-8f49c3363b9e.png)
### Grafiks
