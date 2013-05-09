ď»ż#include <stdio.h>

#define MAXLINE 1000 /* max rozmiar wiersza */

int getline(char line[], int maxline);
void copy(char to[], char from[]);

/* wypisz najdĹ‚uĹĽszy wiersz */
main()
{
   int len;  /* dĹ‚. bieĹĽÄ…cego wiersza */
   int max;  /* poprzednia max dĹ‚ugoĹ›Ä‡ */
   char line[MAXLINE]; /* bieĹĽÄ…cy wiersz z wejĹ›cia */
   char longest[MAXLINE]; /* przechowuje max wiersz */
   
   printf("\n*** PROGRAM DZIELACY NA SYLABY ***\n\n");
   printf("Podaj slowo, ktore chcesz podzielic na sylaby.\n\n");
   printf("Po wprowadzeniu wyrazu nacisnij ENTER.\nAby wyswietlic wynik nacisnij Ctrl+z i potwierdz ENTERem\n\n");
   printf("Podaj slowo: ");

   max = 0;
   while ((len = getline(line, MAXLINE)) > 0) {
         max = len;
         copy(longest, line);
   }
      
   if(max > 0)  /* znaleziono wiersz */
      printf("%s", longest);
   return 0;
}

/* getline: wczytaj wiersz do s, podaj jego dĹ‚ugoĹ›Ä‡ */
int getline(char s[], int lim)
{
   int c, i;
   
   for (i = 0; i < lim-1 && (c = getchar()) != EOF && c != '\n' && c != ' '; ++i) {
      s[i] = c;
      if (s[i] == 'u') {
         if (s[i-1] == 'a' || 'e' || 'i' || 'o' || 'y') {
            ++i;
            s[i] = '-';
         } else {
            s[i] = '-';
            ++i;
            s[i] = c;
         }
      } else if (s[i-1] == 'a' || s[i-1] == 'e' || s[i-1] == 'o' || s[i-1] == 'y') {
         if (s[i-2] == 'i' && ((s[i-3] > 'a' && s[i-3] < 'e') || (s[i-3] > 'e' && s[i-3] < 'i') || (s[i-3] > 'i' && s[i-3] < 'o') 
         || (s[i-3] > 'o' && s[i-3] < 'u') || (s[i-3] > 'u' && s[i-3] < 'y') || (s[i-3] == 'z'))) {
            s[i] = '-';
            ++i;
            s[i] = c;
         } else {
            s[i] = '-';
            ++i;
            s[i] = c;
         }
      } else if ((s[i-2] == 'i') && (s[i-1] != 'a' || s[i-1] != 'e' || s[i-1] != 'o' || s[i-1] != 'y' || s[i-1] != 'u')) {
            s[i] = '-';
            ++i;
            s[i] = c;
      }
   }
   if (c == '\n') {
      s[i] = c;
      ++i;
   }
   s[i] = '\0';
   return i;
}

/* copy: przepisz from do to; */
/* to musi byÄ‡ dostatecznie duĹĽe */
void copy(char to[], char from[])
{
   int i;
   
   i = 0;
   while ((to[i] = from[i]) != '\0')
      ++i;
}
