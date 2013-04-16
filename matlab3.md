```c
# Zajecia 14.04.2013 mala powtórka

### Zmienne zapisywane w systemie podwójnej precyzji:

* realmax
* realmin
* eps 1+eps>1

Skalarne a=1

Wektory 
        x=[1 2 3]
        y=[1;2;3]
Macierze 
        [1,2;2,3]

Polecenia:

        who wyswietla informcje o zmiennych
        whos
        clear all - czsci tabele
        
### Obliczenia numeryczne(symboliczne)

      okna:
        komendy
        grafika
        edytor dzielimy na skrypt i funkcje

Skrypty:
        Możemy tworzyć petle for, if, while
        Obliczać sumowania

Operacje:
      Algebra liniowa
        dodawnia +
        odejmowania -
        mnożenia *
      Tablicowe(kropkowe)
        element * element
        
Te operacje można realizować przez petle.

# Cwiczenia

### Cwiczenie 2 Operacje na liczbach 0blicz:

      x=(-log(2.4)+sqrt(sin(4)-4*exp(3.4)))/(2*pi)

      x=sqrt(4*exp(12.4))/(2*tan(pi*0.47))
      
***
### Sprawdzanie numeryczne tożsamosci trygonoetrycznej dla kilku wartosci katów alfa i beta np. pi/2, 0.366pi itp

       w=[]
    for b=0:0.1:1
       disp(b);

      c= cos(b).^2+sin(b).^2-1;
      w=[w,c]
    end
    w
***
### Zadanie z cos(alfa)+cos(beta)

    alfa=pi/2
    beta=0.366*pi
    z=(cos(alfa)+cos(beta))-(2*cos(0.5*(alfa+beta)))*(cos(0.5*(alfa-beta)))
    
***

### Generowanie wektorów, przetestuj wyrżenia:

    a=[1 2 3];
    b=[1,2,3];
    c=[1;2;3];
    y=b'
    c==y
    c(1)=5
    b(2)=6
    clc
    
### Przykład b)
    
    c==y
    d=[-1.3*sin(sqrt(5))*(log(6)-5)]
    e=[1:10]
    e=[1:.1:10]

***
### Zadanie - Dostep do elementów

### Przyklad a)

    a=[1:5]
    a(1),a(2)
    a(10)
    a(10)=123%co się stanie, przecież a ma rozmiar 5 
    Program pokaż blad bo tablica jest za mala, trzeba zamiast a=[1:5] wpisać a=[1:10]
    
### Przyklad b)

    b=[2:2:20]
    b/2
    2\b
    c=[1:10]
    b/c
    b./c
    
### Zadanie - Interpolacja
    
    x=[1,2,3]
    y=[3.20,3.29,3.32]
        
    p=polyfit(x,y,2)
    x1=1:0.1:3;
    y1=polyval(p,x1)
    plot(x,y,'o',x1,y1,'--')
    
### Aproksymacja 

    x=[1,2,3]
    y=[3.20,3.29,3.32]
        
    p=polyfit(x,y,2)
    p1=polyfit(x,y,1)
    x1=1:0.1:3;
    y1=polyval(p,x1)
    y2=polyval(p1,x1)
    plot(x,y,'o',x1,y1,'--',x1,y2)


## Macierze

      A=[1 2 3;4 5 6;7 8 9]
      B=A'
      A(2,3)
      C=[1:10;11:20;21:30;31:40]
      C(1:2,1:4)
      C(2:3,1:1)
      C(1:1,5:8)
      D=[C,[1;2;3;4]]
      Z=zeros(2,4)
      
      
      x=rand(4,4)
      F=5*ones(3,3)
      F=F*2
      F=F/5
      G=4*ones(3,3)
      G/F
      G./F
      G*F
      G.*F
      
### Operacje macierzowe

    z=rand(4,4)
    det(z)
    sum(z)
    min(z)
    max(z)
    x=inv(z)
    x*z
    diag(z)
    rank(z)
    
### Uklad równan liniowych

    a=[1 -4 3 5;3 1 -2 7;2 1 1 8;-1 -2 -5 -2];
    b=[-7;14;5;4];
    [x]=[a]\[b]
  
### Liczby zespolone

    a=4+3i
    b=5+2i
    a+b;a-b;a*b;a/b;
    real(a)
    imag(b)
    conj(a)
    abs(a)
    angle(a)
    c=5*(cos(0.6435)+i*sin(0.6435))
    d=5*exp(i*0.6435)
    
#Wykresy

### Dwuwymiarowy wykres

    x=-10:.005:40;
    y=[1.5*cos(x)+4*exp(-.01*x).*cos(x)+exp(.07*x).*sin(3*x)];
    plot(x,y)
    
### Wykres3D

    [x,y]=meshgrid(-3:.12:3);
    z=sin(x).*exp(y)+x.*y;
    mesh(x,y,z);
    
#Funkje

### Otwieranie funkcji z zapisanej w skrypcie w WindowCommand

    function[val]=kwadratowa(a,b,c,x)
    
    val=a*x.^2+b*x+c;
    end
    
Funkcje wywolujemy poleceniem>> kwadratowa(1,1,1[1 2 3])

```c


