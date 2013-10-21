## Zadania ze Środowiska Programisty.
# Laboratorium 2.

1\. Wyświetl na ekran 2 pierwsze wiersze pliku program.c. (head)

```sh
head -n 2 program.c
```

2\. Wyświetl na ekran 4 ostatnie wiersze pliku program.c. (head, tail)

```sh
head
tail -n 4 program.c
```

3\. W pliku program.c znajdź wszystkie wiersze z wystąpieniem słowa „main”. (grep)

```sh
grep 'main' program.c
```

4\. Plikowi program.c nadaj następujące uprawnienia: właściciel – czytanie, pisanie, grupa – czytanie, pozostali użytkownicy: brak uprawnień. (chmod)

```sh
