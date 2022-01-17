# 4.LD integral
Šajā labratorijas darbā tika realizēta programma, kas aprēķina integrāļa vērtību ar taisnstūra, trapeču un Simpsona metodi. Ievērojama atšķirība bija veikto ciklu skaitā, kas tika izpildīti, lai aprēķinātu integrāli. Koda svarīgāka daļa nepārprotami ir cikli, katras metodes aprēķināšanai. Iegūtais integrālis sakrita ar wolframalpha rezultātu.
### Uzrakstītais kods:
```
#include<stdio.h>
#include<math.h>

void main()
{
float a, b, eps, h, integr1=0., integr2;
int k, i, n=2;

printf("Ievadi min robežas vērtibu: ");
scanf("%f", &a);

printf("Ievadi max robežas vērtibu: ");
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
printf("Izpildīto ciklu skaits dotās metodes aprēķinā: %.2d\n", k);

n = 2;
integr1 = 0;
integr2 = ((b-a)*(exp(a)+exp(b))/n)+2*eps;
while(fabs(integr2-integr1)>eps)
    {
    n *= 2;
    h = (b-a)/n;
    integr1 = integr2;
    integr2 = 0;
    for(k=0; k<n; k++)
    integr2 += h*((exp(a+k*h)+exp(a+(k+1)*h))/2);
    }
printf("\nIntegrāļa vērtība, izmantojot trapeču metodi: %.2f\n", integr2);
printf("Izpildīto ciklu skaits dotās metodes aprēķinā: %.2d\n", k);
n = 2;
integr1 = 0;
integr2 = ((b-a)*(exp(a)+exp(b))/n)+2*eps;
while(fabs(integr2-integr1)>eps)
    {
    n *= 2;
    h = (b-a)/n;
    integr1 = integr2;
    integr2 = 0;
    for(i=1; i<=n/2-1; i++)
        {
        integr2 += 2*(2*exp((a+(2*i-1)*h))+exp((a+2*i*h)));
        }
    integr2 += exp(a)+exp(b)+4*exp(b-h);
    integr2 *= h/3;
    }
printf("\nIntegrāļa vērtība, izmantojot Simpsona metodi: %.2f\n", integr2);
printf("Izpildīto ciklu skaits dotās metodes aprēķinā: %.2d\n", i);
}
```
### Rezultāts:

![](https://github.com/agurdziels/RTR105/blob/main/4.LD.%20integral/rezult%C4%81ts.png)

### Wolframalpha rezultāts:

![](https://github.com/agurdziels/RTR105/blob/main/4.LD.%20integral/wolframalpha.png)

### Grafiks:

![](https://user-images.githubusercontent.com/90239365/148620387-1ffd9ff9-294a-4363-a220-1a6810d4ef53.png)

