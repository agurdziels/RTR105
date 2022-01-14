# 1.LD series
Šajā labratorijas darbā tika realizēta programma, kas izmanto skaitlisko metodi - Teilora rindas, lai aprēķinātu funkcijas vērtību kādā punktā. Teilora rindas dod iespēju efektīvāk aprēķināt funkcijas vērtību, izmantojot rekurences izteiksmi dotajai funkcijai, manā gadījumā exp(x) funkcijai. Manas funkcijas grafikā var novērot, ka pieaugot Teilora rindas kārtas skaitlim, funkcija arvien garāku gabalu ir vienāda ar pētāmo funkciju.

### Uzrakstītais kods
```
#include <stdio.h>
#include <math.h>

int main() 
{
long double a499, a500;
double x, a0, s0, s499, s500, teil;
int k=0;

printf("Dotā funkcija exp(x)!\n");
printf("Ievadiet x vērtību: ");
scanf("%lf", &x);

printf("\nDotās funkcijas summas izteiksme: \n\n");
printf("               500\n");
printf("              _____\n");
printf("              %c           k  \n",92);
printf("               %c        x   \n",92);
printf("exp(%.2lf) =     >    _______ \n", x);
printf("               /\n");
printf("              /____     k!   \n");
printf("               k=0\n\n");

//definīcijas apgabals x∈R

printf("Dotās funkcijas rekurences funkcionālā reizinātāja izteiksme: \n\n");
printf("       x\n");
printf("R =  _____\n");
printf(" \n");
printf("       k \n\n");

a0 = pow(x,0)/(1);
s0 = a0;
printf("a0 = %.2lf\tS0 = %.2lf\n", a0,s0);


a499 = a0;
s499 = s0;

while(k<499)
    {
    k++;
    a499 *= x/k;
    s499 += a499;
    }
printf("a499 = %Le\ts499 = %lf\n", a499, s499);//


a500 = a499 * x/500;//
s500 = s499 + a500;
printf("a500 = %Le\ts500 = %lf\n", a500, s500);//

teil = s500;
printf("Funkcijas vērtība aprēķinot, izmantojot, Teilora rindas izteiksmi: %lf\n", teil);

double f1 = exp(x);
printf("Funkcijas vērtība aprēķinot, izmantojot, funkcijas izteiksmi: %lf\n", f1);

return 0;
}
```
### Rezultāts
![rezultats1](https://user-images.githubusercontent.com/90239365/148692720-0c7d3afb-d599-4218-82b3-cc9a2ed91342.png)
### Grafiks
![grafiks1](https://user-images.githubusercontent.com/90239365/149596358-19ac2c8d-1882-45c6-9eac-b0b043cd2f9a.png)



