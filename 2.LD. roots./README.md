# 2.LD roots
Šajā labratorijas darbā tika realizēta programma, kas ar Dihotomijas metodi atrod funkcijas saknes, lietotāja izvēlētā intervālā. No šīs metodes izriet izteiksme f(x)-C=0. Koda svarīgākā daļa ir while cikls, kurš arī realizē Dihotomijas metodes algoritmu - pirmstam minēto izteiksmi. Rezultātā ieguvu patiesu sakni, kura sakrita ar funkcijas grafiku. 

### Uzrakstītais kods:
```
#include <stdio.h>
#include <math.h>

int main()
{
float a, b, c, x, delta_x, funkca, funkcb;
int i=0;

printf("Ievadi min robežas vērtību: ");
scanf("%f", &a);

printf("Ievadi max robežas vērtību: ");
scanf("%f", &b);

printf("Ievadi kādai c vērtībai aprēķināt x pēc vienādojuma - exp(x)=c: ");
scanf("%f", &c);

printf("Ievadi ar kādu precizitāti aprēķināt: ");
scanf("%f", &delta_x);

funkca = exp(x)-c;
funkcb = exp(x)-c;

while((b-a)>delta_x)
    {
    x=(a+b)/2.;
    if(funkca*(exp(x)-c)>0)
    a=x;
    else
    b=x;
    i++;
    }

printf("\nNorādītajā intervālā c = %.2f atrodas pie x=%.2f, jo exp(%.2f) = %.2f\n",c,x,x,exp(x));
printf("Iterāciju skaits, lai aprēķinātu šo x vērtību ar uzdoto precizitāti: %d\n", i);

return 0;
}
```

### Rezultāts:
![rezultats2 3](https://user-images.githubusercontent.com/90239365/148660850-c361eac7-764d-4bbc-a188-339d31d3bfbe.png)
### Grafiks:
![grafiks2 3](https://user-images.githubusercontent.com/90239365/148660827-2c65f244-361d-4177-877d-7a9160d4a82a.png)


