~~~c
dď»ż#include <stdio.h>
#define MAXLINE 40 /* definiuje zmiennÄ… globalnÄ… - max dĹ‚ugoĹ›Ä‡ sĹ‚owa */

int getline(char line[], int maxline);   /* deklaracja funkcji wczytujÄ…cej sĹ‚owo */

/* gĹ‚Ăłwna funkcja wyĹ›wietla wynik */
main()
{
   char line[MAXLINE]; /* bieĹĽÄ…cy wyraz z wejĹ›cia */
   
   printf("\n*** PROGRAM DZIELACY NA SYLABY ***\n\n");
   printf("Podaj slowo, ktore chcesz podzielic na sylaby.\n\n");
   printf("Po wprowadzeniu wyrazu nacisnij ENTER.\n\n");
   printf("Podaj slowo: ");

   getline(line, MAXLINE);  /*wywoĹ‚anie funkcji wczytujacej sĹ‚owo oraz dzielacej go na sylaby */

   printf("%s", line);  /* wyĹ›wietlenie wyniku */
   return 0;
}

/* getline: wczytaj sĹ‚owo do tablicy s oraz dzielaca wyraz na sylaby */
int getline(char s[], int lim)
{
   int c, i, p;
   p = 0;
   
   for (i = 0; i < lim-1 && (c = getchar()) != EOF && c != '\n' && c != ' '; ++i) {    /* wczytuj znak za znakiem, a nastÄ™pnie przekazuj go do analizy */
      s[i] = c;      /* wstaw atualnÄ… literÄ™ do tablisy s na pozycjÄ™ i */
      if (s[i] == 'a' || s[i] == 'e' || s[i] == 'i' || s[i] == 'o' || s[i] == 'y' || s[i] == 'u') {  /* szuka samogĹ‚osek i zwiÄ™ksza wartosc p jesli jakÄ…Ĺ› znajdzie */
         ++p;
      }
      if (p > 1 && (s[i] == 'a' || s[i] == 'e' || s[i] == 'i' || s[i] == 'o' || s[i] == 'y' || s[i] == 'u')) { /*sprawdza czy aktualny znak jest samogĹ‚oskÄ… i czy jest to juĹĽ ktĂłraĹ› z kolei samogĹ‚oska */
         if (s[i-1] == 'a' || s[i-1] == 'e' || s[i-1] == 'i' || s[i-1] == 'o' || s[i-1] == 'y' || s[i-1] == 'u') {   /* sprawdza czy poprzedni znak tez byĹ‚ samogĹ‚oskÄ… */
            if (s[i] == 'u') {  /* jeĹ›li aktualny znak to 'u' to nie dziel na sylaby */
               --p;
            } else if ((s[i-1] == 'i') && (s[i] != 'i')) {  /*jeĹ›li poprzedni znak to 'i', a poprzedni to inna samogĹ‚oska niĹĽ 'i', to nie dziel na sylaby */
               --p;
            } else { /* w przeciwnym wypadku podziel pomiedzy samogĹ‚oskami*/
               s[i] = '-';
               ++i;
               s[i] = c;
               --p;
            }
         } else if (s[i-2] == 'a' || s[i-2] == 'e' || s[i-2] == 'i' || s[i-2] == 'o' || s[i-2] == 'y' || s[i-2] == 'u') { /*jeĹ›li poprzednie warunki sie nie zgadzaĹ‚y sprawdza czy samogĹ‚oska byĹ‚a dwa znaki temu, jesli tak odpowiedni dzieli na sylaby po samogĹ‚osce */
            s[i+1] = s[i];
            s[i] = s[i-1];
            s[i-1] = '-';
            ++i;
            --p;
         } else if (p >1 && (s[i-3] == 'a' || s[i-3] == 'e' || s[i-3] == 'i' || s[i-3] == 'o' || s[i-3] == 'y' || s[i-3] == 'u')) { /*jeĹ›li poprzednie warunki nie byĹ‚y speĹ‚nione sprawdza czy samogĹ‚oska byĹ‚a trzy znaki temu, jeĹ›Ĺ‚i tak dzieli na sylaby */
            if ((s[i-1] == 'z' && (s[i-2] == 'c' || s[i-2] == 'r' || s[i-2] == 'd' || s[i-2] == 's')) || (s[i-1] == 'h' && s[i-2] == 'c')) { /*sprawdza czy nie ma dwuznakĂłw, tak by ich nie rozdzieliÄ‡ */
               s[i+1] = s[i];
               s[i] = s[i-1];
               s[i-1] = s[i-2];
               s[i-2] = '-';
               ++i;
               --p;
            } else {
               s[i+1] = s[i];
               s[i] = s[i-1];
               s[i-1] = '-';
               ++i;
               --p;
            }
         } else if (p >1 && (s[i-4] == 'a' || s[i-4] == 'e' || s[i-4] == 'i' || s[i-4] == 'o' || s[i-4] == 'y' || s[i-4] == 'u')) { /*jeĹ›li poprzednie warunki nie byĹ‚y speĹ‚nione speĹ‚nione sprawdza czy samogĹ‚oska byĹ‚a cztery znaki temu, jeĹ›li tak dzieli odpowiednio */
            if ((s[i-2] == 'z' && (s[i-3] == 'c' || s[i-3] == 'r' || s[i-3] == 'd' || s[i-3] == 's')) || (s[i-2] == 'h' && s[i-3] == 'c')) { /*uwaĹĽa na dwuznaki */
               s[i+1] = s[i];
               s[i] = s[i-1];
               s[i-1] = '-';
               ++i;
               --p;
            } else {
               s[i+1] = s[i];
               s[i] = s[i-1];
               s[i-1] = s[i-2];
               s[i-2] = '-';
               ++i;
               --p;
            }
         }
      }
   }
   if (c == '\n') { /*dodaje nowy akapit na koniec tablicy, by Ĺ‚adniej wyĹ›wietlaÄ‡ */
      s[i] = c;
      ++i;
   }
   s[i] = '\0';
   return i;
}
```c
