##Laboratorium 7

1\. W bieżącym katalogu zamienić rozszerzenia wszystkich plików z rozszerzeniem htm na html. Jeżeli w nazwie pliku istnieje spacja, to należy zamienić ją na znak podkreślenia.

```sh````
#!/bin/bash

FOUND=0

for filename in *
do
     echo "$filename" | grep -q " "
     if [ $? -eq $FOUND ]
     then
       fname=$filename
       n=$(echo $fname | sed -e "s/ /_/g")
       mv "$fname" "$n"
     fi
done
for filename in *
do
     echo "$filename" | grep -q ".htm$"
     if [ $? -eq $FOUND ]
     then
       fname=$filename
       n=$(echo $fname | sed -e "s/.htm/.html/g")
       mv "$fname" "$n"
     fi
done

exit 0
```sh```

2\. Napisać skrypt zawierający funkcję obliczającą silnię. Następnie należy obliczyć silnię z liczby, która jest argumentem skryptu. W przypadku niepoprawnego argumentu należy wypisać odpowiedni komunikat.

```sh```
#!/bin/bash
echo "Podaj argument silni:"
read arg
for arg in $arg
do
    WYNIK=1
    LICZNIK=1
    if [ $arg -ge 0 ];
    then
    while [ $LICZNIK -le $arg ]; 
    do
        WYNIK=$[ $WYNIK * $LICZNIK ]
        LICZNIK=$[ $LICZNIK + 1]
    done
    echo "Silnia dla $arg = $WYNIK"
    else
    echo "$arg nie jest poprawnym argumentem!"
    fi

done
exit 0 
```sh```

3\. Napisać skrypt zbierający jak najwięcej informacji o użytkowniku, którego login jest argumentem skryptu. Jeżeli skrypt nie ma argumentu, to należy użyć login osoby uruchamiającej skrypt.

#!/bin/bash
ISTNIEJE=0
if [ "$1" == "" ]
then
        uzytkownik=`whoami`
else
        uzytkownik=$1
fi
echo "Informacje o uzytkowniku $uzytkownik:"
who | grep -w "$uzytkownik" > /dev/null 2> /dev/null
if [ $? -eq $ISTNIEJE ]
then
czas=`who |grep -w "$uzytkownik"| tr -s " " | cut -f 4 -d " "`
data=`who |grep -w "$uzytkownik"| tr -s " " | cut -f 3 -d " "`
adresip=`who |grep -w "$uzytkownik"| tr -s " " | cut -f 5 -d " "`

        echo "$uzytkownik jest zalogowany"
        echo "$uzytkownik zalogowal sie o godzinie: $czas, dnia: $data"
        echo "Adres IP uzytkownika $uzytkownik to: $adresip"
else
        echo "$uzytkownik nie jest zalogowany"
fi

exit 0
```sh```

4\. Napisz skrypt usuwający z katalogu domowego i jego podkatalogów wszystkie pliki zwykłe o nazwie 'core' starsze niż 3 dni.

```sh```
#!/bin/bash

file=`find ~ -name "core" -ctime -3  -type f` 
rm "$file"
exit 0
```sh```
