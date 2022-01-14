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

funkca = exp(a)-c;
funkcb = exp(b)-c;

if(funkca*funkcb>0)
    {
    printf("Norādītajā intervālā exp(x) funkcijai ");
    printf("nav c = %f vērtība(vai tajā ir pāra c vērtību skaits)\n", c);
    return 1;
    }

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
printf("Iterāciju skaits, lai aprēķinātu šo x vērtību ar uzdoto precizitāti: %d\n",i);

return 0;
}
```

### Rezultāts:
![rezultats2](https://user-images.githubusercontent.com/90239365/149572246-6c60c13b-550b-4dde-9b89-05c7eac7bf63.png)
### Grafiks:
![grafiks2](https://user-images.githubusercontent.com/90239365/149572257-0d86b2be-cb25-4d71-aec8-63806d2a4742.png)


