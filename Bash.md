### Laboratorium 1

1\. Używając linii poleceń stwórz strukturę katalogów:

```sh
mkdir -p dom nauka/{c,logo,pascal} praca/{dokumenty,zlecenia/{niezrealizowane,zrealizowane}}
```

2\. Przejdź do katalogu dom i utwórz katalog wazne-sprawy.

```sh
cd dom
mkdir wazne-sprawy
```

3\. Wejdź do katalogu wazne-sprawy i utwórz tam pusty plik rachunki.txt.

```sh
cd wazne-sprawy
touch rachunki.txt
```

4\. Będąc w katalogu wazne-sprawy skopiuj plik rachunki.txt do katalogu zrealizowane.

```sh
cp rachunki.txt ../../praca/zlecenia/zrealizowane
```

5\. Przejdź do katalogu zrealizowane i zmień nazwę pliku rachunki.txt na wykonano.txt.

```sh
cd ../../praca/zlecenia/zrealizowane
mv rachunki.txt wykonano.txt
```

6\. Utwórz plik wykonano.txt wielkości 11 bajtów, następnie podziel go pliki wielkości 5 bajtów. W ten sposób otrzymasz 3 pliki. (split)

```sh
cat>wykonano.txt
0123456789
split --bytes=5 wykonano.txt
```

7\. Będąc w katalogu logo skopiuj powyżej otrzymane 3 pliki do katalogu dokumenty.

```sh
cd nauka/logo
cp -p ../../praca/zlecenia/zrealizowane/{xaa,xab,xac} ../../praca/dokumenty
```

8\. Będąc w katalogu dokumenty połącz skopiowane 3 pliki w plik odtworzono.txt, tak aby otrzymać plik o zawartości identycznej z wykonano.txt. Następnie plik odtworzono.txt skopiuj do katalogu wazne-sprawy.

```sh
cd ../../praca/dokumenty
cat xaa xab xac > odtworzono.txt
cp odtworzono.txt ../../dom/wazne-sprawy
```

9\. Będąc w katalogu wazne-sprawy sprawdź, czy są jakieś różnice w zawartości plików wykonano.txt i odtworzono.txt.

```sh
cd ../../dom/wazne-sprawy
diff ./odtworzono.txt ../../praca/zlecenia/zrealizowane/wykonano.txt
```

10\. Wyświetl kalendarz na październik 2013 r. (cal)

```sh
cal 10 2013
```

Wyświetl kalendarz na wrzesień, październik i listopad 2013 r. z miesiącami obok siebie (cal):

```sh
cal 11 2013 -B2
```

Wyświetl kalendarz na październik, listopad i grudzień 2013 r. w taki sposób:

```sh
cal 11 2013 -A1 -B1
```

I jeszcze raz na wrzesień i październik oraz na październik i listopad 2013 r z miesiącami obok siebie (cal, cut?):

```sh
cal -3 11 2013 | cut -c 1-43
```

11\. Jaki był dzień tygodnia 25 maja 1975 r. (cal i date):

```sh
date -d 1975-05-25 +%A
cal 05 1975 -H 1975-05-25
```
