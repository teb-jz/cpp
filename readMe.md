
# Spis treści
1. [Wprowadzenie](#wprowadzenie)
2. [Zmienna](#zmienna)
    - [Deklaracja zmiennej](#deklaracja-zmiennej)
3. [Podstawowe operatory](#podstawowe-operatory)
    - [Operator przypisania](#operator-przypisania)
    - [Operatory arytmetyczne](#operatory-arytmetyczne)
    - [Dodatkowe operatory przypisania](#dodatkowe-operatory-przypisania)
4. [Typy danych](#typy-danych)
    - [Typy liczbowe](#typy-liczbowe)
        - [Całkowite](#całkowite)
        - [Niecałkowite](#niecałkowite)
    - [Typ znakowy](#typ-znakowy)
    - [Typ logiczny](#typ-logiczny)
    - [Rzutowanie typów](#rzutowanie-typów)
    - [Stałe](#stałe)
5. [Wprowadzanie i wyprowadzanie danych](#wprowadzanie-i-wyprowadzanie-danych)
    - [Wyświetlanie danych](#wyświetlanie-danych)
        - [Znaki specjalne](#znaki-specjalne)
    - [Pobieranie danych](#pobieranie-danych)
6. [Instrukcje warunkowe](#instrukcje-warunkowe)
    - [Operatory relacyjne](#operatory-relacyjne)
    - [Operatory logiczne](#operatory-logiczne)

# Wprowadzenie

Podstawowy program składa się z funkcji `main`, która wywoływana jest po jego uruchomieniu. Wszelkie instrukcje, które mają się wykonać, zapisujemy w ciele tej funkcji &ndash; pomiędzy nawiasami klamrowymi. Należy mieć na uwadze, że instrukcja `return` kończy pracę funkcji, a co za tym idzie, pracę programu.

```cpp
int main () {

    // ...

    return 0;
}
```
<p align = "right">1.1. Podstawowy program</p>

# Zmienna

**Zmienna** to wydzielone miejsce w pamięci komputera, gdzie są przechowywane dane.

## Deklaracja zmiennej

Tworząc zmienną trzeba nadać jej **typ** oraz **nazwę symboliczną**, przez którą można odwoływać się do niej w programie.

```cpp
int a;
int b;
```
<p align = "right">2.1. Deklaracja zmiennej</p>

Jeżeli kilka zmiennych ma posiadać ten sam typ, zapis można skrócić korzystając z przecinka.

```cpp
int a, b;
```
<p align = "right">2.2. Deklaracja zmiennych</p>

# Podstawowe operatory

## Operator przypisania

Wykorzystywany do przypisywania wartości zmiennym. Oznaczony przez pojedynczy znak równości.

```cpp
int number;

number = 3;
```
<p align = "right">3.1. Przypisanie wartości</p>

W przypadku przypisania wartości zmiennej podczas jej deklarowania mowa o **inicjalizacji** zmiennej.

```cpp
int number = 3;
```
<p align = "right">3.2. Inicjalizacja zmiennej</p>

## Operatory arytmetyczne

Podobnie jak inne języki, *C++* oferuje kilka podstawowych operatorów arytmetycznych, znanych z matematyki:
- `+` &ndash; dodawanie,
- `-` &ndash; odejmowanie,
- `*` &ndash; mnożenie,
- `/` &ndash; dzielenie,
- `%` &ndash; dzielenie modulo (reszta z dzielenia).

## Dodatkowe operatory przypisania

Wartości często będą wymagały zmiany poprzez nadpisanie zmiennej.

```cpp
int i = 0;

i = i + 1;
i += 1;
i++;
```
<p align = "right">3.3. Nadpisanie wartości</p>

Powyższe trzy zapisy są równoważne. Każda z linijek odpowiada za zwiększenie wartości zmiennej `i` o jeden. Adekwatnie dla pozostałych operatorów:

- `+=`,
- `-=`,
- `*=`,
- `/=`,
- `%=`.

Wszystkie powyższe operatory są **binarne** (dwuargumentowe). Dodatkowo mamy do dyspozycji:
- `++`,
- `--`,

które odpowiadają **inkrementacji**, czyli zwiększeniu wartości o *1* oraz **dekrementacji** &ndash; zmniejszeniu wartości o *1*. Są to operatory **unarne** (jednargumentowe) i działają jedynie na zmiennych **całkowitoliczbowych**.

# Typy danych

## Typy liczbowe

- ### Całkowite

<div style = "padding-left: 30px">

|Nazwa typu|Zakres|
|---|:-:|
|`short`|*-2<sup>15</sup>* &ndash; *2<sup>15</sup>-1*|
|`int`|*-2<sup>31</sup>* &ndash; *2<sup>31</sup>-1*|
|`long long`|*-2<sup>63</sup>* &ndash; *2<sup>63</sup>-1*|
|`unsigned short`|*0* &ndash; *2<sup>16</sup>-1*|
|`unsigned int`|*0* &ndash; *2<sup>32</sup>-1*|
|`unsigned long long`|*0* &ndash; *2<sup>64</sup>-1*|

</div>

- ### Niecałkowite

<div style = "padding-left: 30px">

|Nazwa typu|Precyzja|
|---|:-:|
|`float`|*6* &ndash; *7* cyfr po przecinku|
|`double`|*15* &ndash; *16* cyfr po przecinku|
|`long double`|*19* &ndash; *20* cyfr po przecinku|

</div>

## Typ znakowy

Do zapisu znaków wykorzystywany jest **ASCII** (*American Standard Code for Information Interchange*), czyli system kodowania, który przyporządkowuje liczbom znaki, cyfry, symbole oraz polecenia sterujące.

|Nazwa typu|Zakres|
|---|:-:|
|`char`|*-128* &ndash; *128*|
|`unsigned char`|*0* &ndash; *255*|

Znaki zapisujemy przy pomocy apostrofów `'`.

```cpp
char c1 = 'a';
char c2 = 97;   // 'a'
```
<p align = "right">3.3. Zmienna znakowa</p>

## Typ logiczny

|Nazwa typu|Wartości|
|-|-|
|`bool`|`true` lub `false`|

```cpp
bool b1 = true; // 1
bool b2 = 3;    // 1
bool b3 = -4;   // 1
```
<p align = "right">3.4. Typ logiczny</p>

Wszystkie zmienne posiadają wartość prawdziwą.

> Każda niezerowa wartość jest interpretowana jako prawda.

## Rzutowanie typów

Czasami zachodzi konieczność **konwersji** pomiędzy danymi typami.

```cpp
float a = 9.84;
int b = (int)a; // 9
```
<p align = "right">3.5. Rzutowanie typów</p>

**Rzutowanie** typów odbywa się poprzez poprzedzenie wartości nazwą pożądanego typu, zapisaną w nawiasach okrągłych.

## Stałe

```cpp
const int x = 21;
```
<p align = "right">3.6. Deklaracja stałej</p>

Stała powinna zostać zainicjalizowana wartością podczas deklaracji.

# Wprowadzanie i wyprowadzanie danych

Do wyświetlania danych na ekran oraz ich wprowadzania służą obiekty zdefiniowane w bibliotece `iostream`.

## Wyświetlanie danych

```cpp
std::cout << "Hello world";
```
<p align = "right">4.1. Wyświetlanie tekstu</p>

Tekst zapisujemy przy pomocy cudzysłowów `"`.

```cpp
int number = 2;

std::cout
    << "Suma liczb " << number << " i " << 3
    << " wynosi " << number + 3 << ".";
```
<p align = "right">4.2. Wyświetlanie danych</p>

Poszczególne ciągi znaków, liczby, wartości zmiennych, czy wyrażenia możemy wypisywać po kolejnych znakach `<<`. Dla czytelności można rozbić zapis na kilka linii.

### Znaki specjalne

Przejście do nowej linii można zrealizować na dwa sposoby: `endl` lub `\n`.

```cpp
std::cout << "Przykładowy" << std::endl << "tekst";
std::cout << "Przykładowy\ntekst";
```
<p align = "right">4.3. Znak końca linii</p>

Kolejnym przydatnym znakiem specjalnym jest tabulacja `\t`.

```cpp
std::cout << "Przykładowy\ttekst";
```
<p align = "right">4.4. Znak tabulacji</p>

## Pobieranie danych

Do pobierania wartości z klawiatury służy `cin`. Należy zwrócić uwagę na przeciwny zwrot znaków `>>`.

```cpp
int number;

std::cin >> number;
```
<p align = "right">4.5. Wczytywanie danych</p>

`cin` pozwala na wczytanie więcej wartości.

```cpp
int a, b, c;

std::cin >> a >> b >> c;
```
<p align = "right">4.6 Wczytywanie wielu danych</p>

# Instrukcje warunkowe

**Instrukcję warunkową** rozpoczynamy od słowa kluczowego `if`, następnie w nawiasach okrągłych precyzujemy **warunek**, a instrukcje, które mają się wykonać, jeżeli będzie on spełniony, zapisujemy w ciele instrukcji warunkowej, wyznaczonej przez nawiasy klamrowe.

```cpp
bool flag = true;

if (flag) {

    std::cout << "Warunek spełniony";
}
```
<p align = "right">5.1. Instrukcja warunkowa</p>

W przypadku, gdy w ciele instrukcji warunkowej znajduje się tylko jedna linia kodu, możemy pominąć klamry.

```cpp
bool flag = true;

if (flag) std::cout << "Warunek spełniony";
```
<p align = "right">5.2. Krótka instrukcja warunkowa</p>

## Operatory relacyjne

Najczęstszym elementem **warunków logicznych** będą wszelkiego rodzaju porównania dwóch wartości. Możemy je realizować z wykorzystaniem **operatorów relacyjnych**:
- `==` &ndash; równe,
- `!=` &ndash; różne,
- `>` &ndash; większe niż,
- `>=` &ndash; większe lub równe,
- `<` &ndash; mniejsze niż,
- `<=` &ndash; mniejsze lub równe,

## Operatory logiczne

W przypadku bardziej precyzyjnych zagadnień pomocne okazują się **warunki złożone**, konstruowane przy pomocy **operatorów logicznych**:

|operator|nazwa|opis|
|:-:|:-:|---|
|`&&`|koniunkcja|*and*, *i*, *oraz* &ndash; oba warunki muszą być spełnione|
|`\|\|`|alternatywa|*or*, *lub* &ndash; przynajmniej jeden z warunków musi być spełnony|
|`!`|negacja|*not*, *zaprzeczenie* &ndash; odwrócenie wartości logicznej|
