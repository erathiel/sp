##Laboratorium 4

1\. Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże.

```sh
ls | tr [:lower:] [:upper:]
```

2\. Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę.

```sh
ls -hgoF --full-time | tr -s " " | cut -f 1,3,7 -d " " | sed -e '/[/]/d' | tr " " "\t"
```

3\. Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku.

```sh
ls -l -rhS | sed -e '/^d/d' | tr -s " " | cut -f 5,9 -d " "
```

4\. Wyświetl zawartość pliku /etc/passwd posortowaną według numerów UID w kolejności od największego do najmniejszego.

```sh
cat /etc/passwd | sort -r -t ":" -k 3 -n | head
```

5\. Wyświetl zawartość pliku /etc/passwd posortowaną najpierw według numerów GID w kolejności od największego do najmniejszego, a następnie UID.

```sh
cd /etc
cat passwd | sort -r -t : -k 4 -k 3
```

6\. Podaj liczbę plików każdego użytkownika.

```sh
find / -printf "%U\n" 2>/dev/null | sort | uniq -c | sort
```

7\. Sporządź statystykę praw dostępu (dla każdego z praw dostępu podaj ile razy zostało ono przydzielone).

```sh
find -printf "%m\n" | sort | uniq -c
```
