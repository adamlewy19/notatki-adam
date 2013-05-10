### Wyklady Niedziela 24-03-2013.

##Obsluga Matlab'a.

***Podstawowe komendy***

* ans - odpowiedz
* foramt compact - wydruk jest bardziej zwarty bez wolnych lini, steruje postacia wydruku
* a=2+2 - przypisanie zmiennej 
* whos  - pokazuje wlasciwosci naszej funkcji
* format short - ustawia wyswietlanie wynik na króki format wydrku
* format long - wynik przedstawiony bedzie w wiekszej precyzji.
* help format - wyswietla pomoc i podstawowe komendy dla format
* realmax - najwieksza liczba reprezentowana dokldanie, to nie jest najwieksza liczba jaka możemy osiagnać.
* inf - informacja o przepelnieniu, wyszlismy poza skale
* realmin - najmniejsza wartosc reprezentowana dokladnie
* eps - epsiolon maszynowy --- najmniejsza liczba ktora dodana do jedynki daje wieksza liczbe od jedynki 1+E>1 (pierwsi sasiedzi kolo jedynki)
* sqrt(_argument_) - obliczanie pierwiastka
* sin(pi) -  sinus pi
* sind(30) - pokazuje w stopniach
* asin() - funkcja odworotna
* [ np 1 2 3 ] - definiowanie vectora, zamiast spacji można sotosować przecinek. Vector wierszowy
* [; ; ;] - vector kolumnowy gdy odzielamy arguenty srednikiem ;
* 1:3 - też wygeneruje vector, sluzy bardziej do ciagów
* ; - gdy odajemy go na koncu obliczen wsytrzymuje wydruk
* plot(x,y) - otwiera okno do rysowania funkcji, okno graficzne
* plot(x,y,'o') - rysowanie za pomoca kólek
* plot(x,y,'o-') - kólka polaczone linia
* plot(x,y,'g-o',x,y1,'r-')  - narysuje dwie funkcje nachodzace sie na siebie kazda w innym kolorze
* >> x=-2*pi:0.1:2*pi;
  >> y=sin(x);
  >> plot(x,y,'o')  ***przykladowa procedura rysowania funkcji
* ezplot('x^2+y^2=4') - narysuje nam kolo o promieniu 4
* clear('zmienna') - usuwa zmienna z pamieci
* ' - transpozycja w obliczeniach algebry liniowej
* .* - monożenie wektora i poswstaje wetor. operacje z kropkami licznie element po elemencie. Tak samo można przeprowadzać inne dzialania matemayczne.
   x=[1 2 3 ]
  x =
     1     2     3
  >> y=[4 5 6]
  y =
     4     5     6
  >> x.*y
  ans =
     4    10    18
* factorial(np10)  - oblicza silnie
* primes(np120) - rozklad na lczby pierwsze
* max(x) - najwieksza wartosc w wektorze
* roots() - obliczanie pierwiasków

* . -kropka
* , -przecinek znak oddzielajacy w strukrze, kilka operacji w jednej linijce:
  >> x=2,y=3
  x =
     2
  y =
     3
* ; - srednik umieszczany na koncu lini wstrzymuje wydruk
* : -dwukropek separator w poleceniu tworzenia wektora
* () - nawiasy okragle, zawieraja indeksy elementu macierzy
* [] - nawiasy kwadratowe, tworza tablice liczb lub lancuchów znaków.
* xlabel('funkcja x y') - podisywnie osi x, gdy wstawimy y podpisze y.
* % - oznacza poczatek komentarza
* %{ - zawiera blok linii komentarza
* ... - wielokropek nastepna linia jest kontynuacja natepnej linii
* @ - tworzy uchwyt funkcji np @nazwa
* \ - ukosnik lewy macierzowy operator matematyczny oraz używany do generacji greckich liter i symbolo matematycznych w gafice
* disp - drukuje wyniki
* clc - usówa wszystko z okna Command Window
* clear all - usuówa wszytskie zmienne
* close all - zamyka wszystkie okienka graficzne jeżeli byly pootwierane
* ctr+c - zatrzymuje zadanie gdy sie zapetli
* length(x) - dlugosc elementa wektora
* linespace() - nastepujace polecenie utworzy wektor o n rownoleglych wartosciach np. x=linspace(x0.xk.n)


Możemy sami definiować zmienne

Wszyskie obliczenia sa prowadzone w podwójnej precyzji tybu double.

Program rozróżnia male i Wielkie litery.

## Wyklady po przerwie.

Liczby zapisywane sa w systemie dwójkowym.

znak__mantys_wykladnik

Matysa - skończona liczba liczb

Aby zmienić dokladnosc wyswietlania liczb w MatLab.
File->Preferences->Window Command-> (**short** zminiamy na ***long***)

W Matlabie można przeciazac oberatory.

iloczyn skalarny - x1y1+x2y2+x3y3

W MATLABie nie piszemy programów tylko ***skrypt***.
Matlab jest interpreterem polecen nie potrzebuje kompilatora
Skrypty mozna uruchmiać wpisujac ich nazwe w *Window Command*

Aby zlokalizować pierwistek potrzeba kilka kroków:

f(a)f(b)<0

1. Lokalizacja

2. metoda numeryczna

a) bisekcja

    x1=(b-a)/2 /|f(x)|<E
  
    f(a)f(xi)>0
    
    f(xi)f(b)<0
    
    a=x2
    
b) metoda iteracji prostej
  
    f(x)=0
    
    x=g(x)
    
    xn+1=y(xn)
    
    x2=xp
    
c) regula falsi 
  
    patrzymy w kórym przedziale jest pierwiastek i puszczam sieczna
    
d) Metoda sieczna
  
e) Metoda Newtona-Raphsona - styczna
  
    f(x+h)=f(x)+1/1!hf'(x)+1/2!hf''(x)...
    
    f(x+x1-x)=f(x)+hf'(x)=0
    
    0=f(x+x1-x)=f(x)+hf'(x) --> x2=x-(f(x)/f'(x))
    
    
  
## Petla w Matlab'ie
  
  Petla FOR: 
  
    for s=0.0:0.01:1.0
        disp(s)
    end

  Warunek IF:
  
    r=5
    c=5
    
    if r == c
      disp('sylwek');
      else
         disp('zonk');
      end


