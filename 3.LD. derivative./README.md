# 3.LD derivative

## Uzrakstītais kods
```
#include<stdio.h>
#include<math.h>
void tabula(int N,float a,float b, float delta_x);

void main()
{
    int k=0;
    float a,b,x,delta_x;

    printf("Ievadi sākuma robežu: ");
    scanf ("%f", &a);

    printf("Ievadi beigas robežu: ");
    scanf ("%f", &b);

    printf("Ievadi precizitāti: ");
    scanf ("%e", &delta_x);

    x=a;
    while(x<=b)
    {
    k++;
     x+= delta_x;
    }
    tabula(k,a,b,delta_x);
}

void tabula(int N,float a,float b, float delta_x)
{
    int i;
    float x[N],fx[N],fp1[N],yp[N],fpp[N],ypp[N];
 
    for(i=0;i<N;i++)
    {
    if (i==0)
    x[i]=a;
    else
    x[i] = x[i-1] + delta_x;
    fx[i] = exp(x[i]);
    fp1[i] = exp(x[i]);
    fpp[i] = exp(x[i]);
    }

    for(i=0;i<(N-1);i++)
    yp[i] = (fx[i+1]-fx[i])/(x[i+1]-x[i]);


    for(i=0;i<(N-2);i++)
    ypp[i] = (yp[i+1]-yp[i])/(x[i+1]-x[i]);
    

    FILE *fp = fopen("./derivative.dat", "w");
    fprintf(fp,"|%13s|%13s|%13s|%13s|%13s|%13s|\n", "x", "f(x)", "f\'", "             f\'", "            f\'\'", "            f\'\'");
    fprintf(fp,"|%13s|%13s|%13s|%13s|%13s|%13s|\n", " ", " ", " analītiskais", "     skaitliskā", "   analītiskais", "     skaitliskā");
    for(i=0; i<N-2 ; i++)
        {
        fprintf(fp,"|%13.3f|%13.3f|%13.3f|  %13.3f|  %13.3f|  %13.3f|\n",x[i],fx[i],fp1[i],yp[i],fpp[i],ypp[i]);
        }   
    fprintf(fp,"|%13.3f|%13.3f|%13.3f|  %13.3f|  %13.3f|  %13s|\n",x[i],fx[i],fp1[i],yp[i],fpp[i],"nav");
    i++;
    fprintf(fp,"|%13.3f|%13.3f|%13.3f|  %13s|  %13.3f|  %13s|\n",x[i],fx[i],fp1[i],"nav",fpp[i],"nav");
    
    fclose(fp);
}
```
## Rezultāts
![rezultats3 1](https://user-images.githubusercontent.com/90239365/149642871-ad2b7189-039c-4fb3-80bc-9e9d0c0d9e22.png)
## Grafiks
![grafiks3](https://user-images.githubusercontent.com/90239365/149642882-b9622bab-c476-42e7-ae66-dcee8491722a.png)
