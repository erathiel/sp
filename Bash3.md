#Zadania ze Środowiska Programisty
##Laboratorium 3

1\. Wyświetl plik /etc/passwd z podziałem na strony przyjmując, że strona na 5 linii tekstu.

```sh
more -5 /etc/passwd
```

2\. Korzystając z polecenia cat utwórz plik tekst3.txt, który będzie składał się z zawartości pliku tekst1.txt, ciągu znaków podanego ze standardowego wejścia (klawiatury) i pliku tekst2.txt.

```sh
cat> tekst3.txt - tekst1.txt - tekst2.txt
```

3\. Wyświetl po 5 pierwszych linii wszystkich plików w swoim katalogu domowym w taki sposób, aby nie były wyświetlane ich nazwy.


4\. Wyświetl linie o numerach 3, 4 i 5 z pliku /etc/passwd.


5\. Wyświetl linie o numerach 7, 6 i 5 od końca pliku /etc/passwd.

```sh
tail -n 7 /etc/passwd | head -n 3 
```

6\. Wyświetl zawartość pliku /etc/passwd w jednej linii.

```sh
cat /etc/passwd/ | tr "\n" " "
```

7\. Za pomocą filtru tr wykonaj modyfikację pliku plik.txt, polegającą na umieszczeniu każdego słowa w osobnej linii.


8\. Zlicz wszystkie pliki znajdujące się w katalogu /etc i jego podkatalogach.

```sh
ls -a /etc | wc -l
```

9\. Napisać polecenie zliczające ilość znaków z pierwszych trzech linii pliku /etc/passwd.
