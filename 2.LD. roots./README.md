# 2.LD roots

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
![Rezultats2](https://user-images.githubusercontent.com/90239365/148659708-a66230cf-53b1-4775-855b-050281bbcf0b.png)
### Grafiks:
![grafiks2](https://user-images.githubusercontent.com/90239365/148659715-c96ce9e4-1799-4ad8-b5d8-a22196154505.png)

