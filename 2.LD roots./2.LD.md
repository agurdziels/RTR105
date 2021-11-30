# 2.LD roots

## Uzrakstītais kods
```
#include<stdio.h>
#include<math.h>

int main()
{
 float a,c ,b ,x ,delta_x,funkca, funkcb, funkcx;
 int i=0;

  printf("Funkcijas saknes aprēķināšana: \n");

  printf("Ievadi sākuma robežu: ");
  scanf ("%f", &a);

  printf("Ievadi beigas robežu: ");
  scanf ("%f", &b);

  printf("Ievadi precizitāti: ");
  scanf ("%e", &delta_x);

  printf("Norādi kādam y vēlies aprēķināt x: ");
  scanf ("%f", &c);
  funkca = exp(a) - c; 
  funkcb = exp(b) - c;

  printf("exp(%7.3f) - %7.3f=%7.3f\t",a,a,c,funkca);
  printf("exp(%7.3f) - %7.3f=%7.3f\n",b,b,c,funkcb);

 while ((b-a)>delta_x){
  x = (a+b)/2.;
  if(funkca*(exp(x)-c)>0)
   a = x;
  else
   b = x;
  printf("exp(%7.3f) - %7.3f=%7.3f\t",a,a,c,funkca);
  printf("exp(%7.3f) - %7.3f=%7.3f\t",b,b,c,funkcb);
  printf("exp(%7.3f) - %7.3f=%7.3f\n",x,x,c,exp(x)-c);
   i++;
 }

 printf("\nIteraciju skaits: %d\n",i);
 printf("Sakne atrodas pie x=%.5f, jo exp(x) ir %.3f\n",x, exp(x));
 return 0;
}
```

### Rezultāts
```



```
### Grafiks
![Funkcijas grafiks:]
