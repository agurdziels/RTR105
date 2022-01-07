# 4.LD integral

### Uzrakstītais kods
```
#include<stdio.h>
#include<math.h>

void main()
{
float a, b, eps, h, integr1=0., integr2;
int k, n=2;

printf("Ievadi minimuma robežas vērtibu: ");
scanf("%f", &a);

printf("Ievadi maksimuma robežas vērtibu: ");
scanf("%f", &b);

printf("Ievadi precizitātes vērtibu: ");
scanf("%f", &eps);

integr2 = ((b-a)*(exp(a)+exp(b))/n)+2*eps;
while(fabs(integr2-integr1)>eps)
{
    n *= 2;
    h = (b-a)/n;
    integr1 = integr2;
    integr2 = 0;
    for(k=0; k<n; k++)
    integr2 += h*exp(a+(k+0.5)*h);
}
printf("\nIntegrāļa vērtība, izmantojot taisnstūru metodi: %.2f\n", integr2);
n = 2;
integr1 = 0;
integr2 = ((b-a)*(exp(a)+exp(b))/n)+2*eps;
while(fabs(integr2-integr1)>eps)
{
    n *= 2;
    h = (b-a)/n;
    integr1 = integr2;
    integr2 = 0;
    for(k=0 ; k<n ; k++)
    integr2 += h*((exp(a+k*h)+exp(a+(k+1)*h))/2);
}
printf("\nIntegrāļa vērtība, izmantojot trapeču metodi: %.2f\n", integr2);
n = 2;
integr1 = 0;
integr2 = ((b-a)*(exp(a)+exp(b))/n)+2*eps;
while(fabs(integr2-integr1)>eps)
{
    n *= 2;
    h = (b-a)/n;
    integr1 = integr2;
    integr2 = 0;
    for(k=1 ; k<=n/2-1 ; k++)
        {
        integr2 += 2*(2*exp((a+(2*k-1)*h))+exp((a+2*k*h)));
        }
    integr2 += exp(a)+exp(b)+4*exp((b-h)/2);
    integr2 *= h/3;
}
printf("\nIntegrāļa vērtība, izmantojot Simpsona metodi: %.2f\n", integr2);
}
```
### Rezultāts
```
![Rezultāts](https://github.com/agurdziels/RTR105/blob/main/4.LD.%20integral/grafiks.png)
```
### Wolfrmalpha rezultāts
```
(https://github.com/agurdziels/RTR105/blob/main/4.LD.%20integral/grafiks.png)
```
### Grafiks
```
!.[Funkcijas grafiks].(https://github.com/agurdziels/RTR105/blob/main/4.LD.%20integral/grafiks.png)
```