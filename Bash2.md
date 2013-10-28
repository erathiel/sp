## Zadania ze Środowiska Programisty.
# Laboratorium 2.

1\. Wyświetl na ekran 2 pierwsze wiersze pliku program.c. (head)

```sh
head -n 2 program.c
```

2\. Wyświetl na ekran 4 ostatnie wiersze pliku program.c. (head, tail)

```sh
tail -n 4 program.c
```

3\. W pliku program.c znajdź wszystkie wiersze z wystąpieniem słowa „main”. (grep)

```sh
grep 'main' program.c
grep -v main program.c
grep 'main\b' program.c
```

4\. Plikowi program.c nadaj następujące uprawnienia: właściciel – czytanie, pisanie, grupa – czytanie, pozostali użytkownicy: brak uprawnień. (chmod)

```sh
chmod 620 program.c
```

5\. Będąc w katalogu tmp przenieś katalog wazne-sprawy do katalogu praca.

```sh
cd ../../
mv dom/wazne-sprawy praca
```

6\. Zarchiwizuj cały katalog tmp. (zip i tar)

```sh
tar -cf tmp.tar tmp
zip tmp.zip ~/tmp/
```

7\. Usuń katalog tmp.

```sh
rm -r tmp
```

8\. Odtwórz z archiwum katalog tmp. (unzip i tar)

```sh
tar -xf tmp.tar
unzip tmp.zip
```

9\. Posprzątaj na swoim koncie.

```sh
rm tmp.tar
rm tmp.zip
```
10\. (Dodatkowe) Linijki ze środka tekstu od przodu.

```sh
head -n4 program.c | tail -n2
```

11\. (Dodatkowe) Linijki ze środka tekstu od tyłu.

```sh
tail -n 6 program.c | head -n 2
tac program.c | head -n 7 | tail -n 3 | tac
```
