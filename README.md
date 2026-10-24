# Laboratorium 1.5 – Analiza ortofotomapy CIR i statystyki strefowe NDVI w QGIS

## 1. Cel laboratorium

Celem laboratorium 1.5 było rozwinięcie umiejętności związanych z pozyskiwaniem, przetwarzaniem i analizą danych przestrzennych w programie QGIS.

Głównym zadaniem było pobranie ortofotomapy CIR (*Color Infrared*) z serwisu Geoportal, obliczenie na jej podstawie znormalizowanego różnicowego wskaźnika wegetacji NDVI (*Normalized Difference Vegetation Index*), a następnie przeprowadzenie analizy statystycznej dla wybranych fragmentów badanego obszaru.

W ramach ćwiczenia wykorzystano również narzędzie **Zonal Statistics (Statystyki strefowe)**, umożliwiające obliczanie podstawowych statystyk danych rastrowych w granicach wyznaczonych poligonów.

Laboratorium stanowiło kontynuację wcześniejszych zajęć dotyczących analizy danych teledetekcyjnych i wykorzystania programu QGIS.

## 2. Wykorzystane narzędzia i dane

Podczas realizacji laboratorium wykorzystano następujące narzędzia:

- **QGIS** – oprogramowanie GIS typu open source, umożliwiające wizualizację, przetwarzanie oraz analizę danych przestrzennych.
- **Geoportal Krajowy** – serwis internetowy udostępniający dane przestrzenne, w tym ortofotomapy, mapy topograficzne i inne informacje geograficzne.
- **Ortofotomapa CIR (Color Infrared)** – zobrazowanie lotnicze w kompozycji barw fałszywych, zawierające informacje z zakresu bliskiej podczerwieni, światła czerwonego i zielonego.
- **Kalkulator rastra** – narzędzie QGIS umożliwiające wykonywanie obliczeń matematycznych na danych rastrowych.
- **Zonal Statistics (Statystyki strefowe)** – narzędzie pozwalające na obliczanie statystyk wartości rastra w obrębie obiektów wektorowych.
- **Warstwa wektorowa typu poligon** – wykorzystana do wyznaczenia fragmentów badanego obszaru przeznaczonych do analizy.

### 2.1. Charakterystyka danych wejściowych

W ramach laboratorium wykorzystano ortofotomapę pobraną z serwisu [Geoportal Krajowy](https://www.geoportal.gov.pl/).

| Parametr | Wartość |
|---|---|
| Źródło danych | Geoportal Krajowy |
| Rodzaj danych | Ortofotomapa |
| Oznaczenie arkusza | M-33-48-D-d-3-4 |
| Nazwa danych | M-33-48-D-d-3-4 2025 CIR |
| Rok danych | 2025 |
| Kompozycja | CIR (Color Infrared) |
| Oprogramowanie | QGIS |
| Cel wykorzystania | Obliczenie NDVI i analiza statystyk strefowych |

Ortofotomapa CIR przedstawia powierzchnię Ziemi w kompozycji barw fałszywych. W przeciwieństwie do standardowych obrazów RGB wykorzystuje pasmo bliskiej podczerwieni (NIR), co pozwala na łatwiejszą identyfikację obszarów pokrytych roślinnością.

Zdrowa roślinność charakteryzuje się stosunkowo wysokim odbiciem promieniowania w zakresie bliskiej podczerwieni, dlatego na typowych kompozycjach CIR jest widoczna w odcieniach czerwieni.

## 3. Przebieg laboratorium

### 3.1. Pobranie ortofotomapy CIR z Geoportalu

Pierwszym etapem laboratorium było pozyskanie odpowiednich danych przestrzennych z serwisu Geoportal Krajowy.

W tym celu skorzystano z funkcji pobierania ortofotomap i wybrano arkusz oznaczony jako:

**M-33-48-D-d-3-4 2025 CIR**

Pobrana ortofotomapa pochodziła z 2025 roku i przedstawiała wybrany obszar w kompozycji CIR.

Wykorzystanie tego rodzaju zobrazowania było istotne ze względu na możliwość analizy roślinności na podstawie wartości odbicia promieniowania elektromagnetycznego w różnych zakresach spektralnych.

Po pobraniu danych ortofotomapę wczytano do programu QGIS jako warstwę rastrową.

Zaimportowane dane stanowiły podstawę do dalszych obliczeń i analiz przestrzennych.

### 3.2. Analiza kanałów spektralnych ortofotomapy CIR

Kolejnym etapem było zapoznanie się z charakterystyką ortofotomapy CIR oraz wykorzystanymi kanałami spektralnymi.

Typowa ortofotomapa CIR składa się z trzech kanałów:

- **NIR (Near Infrared)** – pasmo bliskiej podczerwieni, wykorzystywane do identyfikacji i oceny roślinności.
- **R (Red)** – pasmo czerwone, w którym chlorofil zawarty w zdrowej roślinności silnie pochłania promieniowanie.
- **G (Green)** – pasmo zielone, wykorzystywane do wizualizacji powierzchni terenu.

Połączenie tych kanałów umożliwia przedstawienie roślinności w charakterystycznych odcieniach czerwieni oraz odróżnienie jej od terenów zabudowanych, dróg czy innych powierzchni.

Do dalszej analizy wykorzystano pasma NIR oraz R, które są niezbędne do obliczenia wskaźnika NDVI.

### 3.3. Obliczenie wskaźnika NDVI

Głównym zadaniem analitycznym laboratorium było obliczenie wskaźnika NDVI (*Normalized Difference Vegetation Index*) na podstawie pobranej ortofotomapy CIR.

NDVI jest jednym z najczęściej stosowanych wskaźników teledetekcyjnych, umożliwiających ocenę stanu, gęstości oraz aktywności fotosyntetycznej roślinności.

Wskaźnik oblicza się według wzoru:

**NDVI = (NIR − R) / (NIR + R)**

Gdzie:

- **NIR** – wartość odbicia promieniowania w paśmie bliskiej podczerwieni,
- **R** – wartość odbicia promieniowania w paśmie czerwonym.

W celu wykonania obliczeń wykorzystano narzędzie **Kalkulator rastra** dostępne w programie QGIS.

W odpowiednim wyrażeniu matematycznym zastosowano kanały spektralne odpowiadające zakresom NIR oraz R.

Po wykonaniu obliczeń uzyskano nową warstwę rastrową przedstawiającą wartości wskaźnika NDVI dla analizowanego obszaru.

### 3.4. Interpretacja i wizualizacja wskaźnika NDVI

Obliczony wskaźnik NDVI przyjmuje teoretycznie wartości w przedziale od -1 do +1.

Wartości te pozwalają na przybliżoną ocenę charakterystyki pokrycia terenu oraz kondycji występującej na nim roślinności.

| Wartość NDVI | Interpretacja |
|---|---|
| -1,0 do 0,0 | Najczęściej woda lub inne powierzchnie niewykazujące typowej odpowiedzi spektralnej roślinności |
| 0,0 do 0,2 | Tereny o niewielkim udziale roślinności lub pozbawione roślinności |
| 0,2 do 0,4 | Roślinność rzadka lub o umiarkowanej aktywności |
| 0,4 do 0,6 | Roślinność o stosunkowo dobrej kondycji |
| 0,6 do 1,0 | Zazwyczaj gęsta i aktywna fotosyntetycznie roślinność |

Przedstawione przedziały mają charakter orientacyjny, ponieważ wartości NDVI zależą między innymi od rodzaju roślinności, pory roku oraz warunków środowiskowych.

Po zakończeniu obliczeń wynik został wyświetlony w programie QGIS w postaci mapy rastrowej.

Uzyskana mapa umożliwiła wizualną analizę przestrzennego zróżnicowania wskaźnika NDVI na badanym obszarze.

### 3.5. Utworzenie tymczasowej warstwy wektorowej

Następnym etapem laboratorium było utworzenie tymczasowej warstwy wektorowej typu **poligon**.

Warstwa ta została przygotowana w programie QGIS i posłużyła do wyznaczenia fragmentów terenu, dla których miały zostać obliczone statystyki NDVI.

W ramach ćwiczenia ręcznie narysowano kilka poligonów obejmujących wybrane części analizowanego obszaru.

Każdy utworzony poligon stanowił osobną jednostkę analityczną, co umożliwiło przeprowadzenie porównania wartości wskaźnika NDVI pomiędzy różnymi fragmentami terenu.

Zastosowanie warstwy wektorowej pozwoliło połączyć dane rastrowe z konkretnymi obszarami przestrzennymi.

### 3.6. Obliczenie statystyk strefowych – Zonal Statistics

Po utworzeniu warstwy poligonowej przeprowadzono analizę statystyczną z wykorzystaniem narzędzia **Zonal Statistics (Statystyki strefowe)**.

Narzędzie to pozwala na obliczenie podstawowych parametrów statystycznych wartości pikseli rastra znajdujących się w granicach poszczególnych poligonów.

Do przeprowadzenia analizy wykorzystano:

- warstwę rastrową zawierającą obliczone wartości NDVI,
- tymczasową warstwę wektorową zawierającą utworzone poligony.

Dla każdego poligonu obliczono następujące statystyki:

**1. Wartość średnia (Mean)**

Średnia wartość NDVI określa przeciętną wartość wskaźnika w granicach danego poligonu. Pozwala na ogólną ocenę charakterystyki roślinności występującej na analizowanym fragmencie terenu.

**2. Wartość minimalna (Min)**

Minimalna wartość NDVI wskazuje najniższą zarejestrowaną wartość wskaźnika w obrębie poligonu. Może odpowiadać fragmentom o małej ilości roślinności lub powierzchniom niepokrytym roślinnością.

**3. Wartość maksymalna (Max)**

Maksymalna wartość NDVI przedstawia najwyższą wartość wskaźnika w granicach analizowanego poligonu. Może wskazywać na fragmenty o dużej aktywności fotosyntetycznej roślinności.

Po wykonaniu obliczeń uzyskane wyniki zostały dodane do tabeli atrybutów warstwy poligonowej.

### 3.7. Analiza wyników w tabeli atrybutów

Ostatnim etapem laboratorium było zapoznanie się z wynikami analizy statystycznej zapisanymi w tabeli atrybutów.

Dla każdego narysowanego poligonu uzyskano wartości średnie, minimalne oraz maksymalne wskaźnika NDVI.

Na podstawie tych danych możliwe było porównanie poszczególnych fragmentów badanego obszaru pod względem wartości NDVI.

Analiza tabeli atrybutów umożliwiła również ocenę zróżnicowania wartości wskaźnika w granicach poszczególnych poligonów.

Wykorzystanie statystyk strefowych pozwoliło rozszerzyć analizę z poziomu wizualnej interpretacji mapy do ilościowego porównania wyznaczonych obszarów.

## 4. Osiągnięte rezultaty

W ramach laboratorium 1.5 udało się zrealizować wszystkie zaplanowane zadania:

1. Pobrano z serwisu Geoportal Krajowy ortofotomapę **„M-33-48-D-d-3-4 2025 CIR”**.
2. Poprawnie zaimportowano pobrane dane rastrowe do programu QGIS.
3. Zapoznano się z charakterystyką kanałów spektralnych ortofotomapy CIR.
4. Obliczono wskaźnik NDVI na podstawie pasma bliskiej podczerwieni (NIR) oraz pasma czerwonego (R).
5. Uzyskano mapę przedstawiającą przestrzenne zróżnicowanie wartości wskaźnika NDVI.
6. Utworzono tymczasową warstwę wektorową typu poligon.
7. Ręcznie wyznaczono kilka fragmentów analizowanego obszaru.
8. Wykorzystano narzędzie Zonal Statistics do obliczenia średnich, minimalnych i maksymalnych wartości NDVI dla poszczególnych poligonów.
9. Uzyskane wyniki zapisano w tabeli atrybutów, umożliwiając porównanie wybranych fragmentów terenu.

## 5. Wnioski

Laboratorium 1.5 umożliwiło praktyczne zastosowanie danych teledetekcyjnych pozyskanych z Geoportalu Krajowego oraz rozwinięcie umiejętności pracy z programem QGIS.

Wykorzystanie ortofotomapy CIR pokazało, w jaki sposób informacje zapisane w różnych kanałach spektralnych mogą zostać zastosowane do analizy roślinności.

Obliczenie wskaźnika NDVI pozwoliło na przedstawienie zróżnicowania roślinności na badanym terenie, natomiast zastosowanie statystyk strefowych umożliwiło przeprowadzenie bardziej szczegółowej analizy ilościowej.

Istotnym elementem ćwiczenia było połączenie danych rastrowych i wektorowych. Dzięki temu możliwe było uzyskanie wartości statystycznych dla konkretnych fragmentów terenu, a nie tylko przedstawienie wyników w postaci mapy.

Zastosowanie narzędzia Zonal Statistics pozwoliło również zrozumieć, w jaki sposób można wykorzystywać dane rastrowe do oceny i porównywania wybranych obszarów przestrzennych.

Warto zaznaczyć, że interpretacja wyników NDVI zależy od charakterystyki wykorzystanych danych. W przypadku obliczeń wykonywanych bezpośrednio na wartościach pikseli ortofotomapy CIR, które nie zostały przeliczone na fizyczne wartości odbicia spektralnego, uzyskany wskaźnik należy traktować przede wszystkim jako narzędzie do względnego porównywania roślinności w obrębie analizowanego zobrazowania.

Zdobyte umiejętności mogą znaleźć zastosowanie w dalszych analizach teledetekcyjnych, monitorowaniu terenów zielonych, badaniu zmian środowiskowych oraz ocenie przestrzennego zróżnicowania roślinności.

## 6. Podsumowanie

**Laboratorium 1.5 zakończyło się pomyślnie.**

W trakcie zajęć udało się pobrać ortofotomapę CIR z Geoportalu Krajowego, wczytać ją do programu QGIS, obliczyć wskaźnik NDVI oraz przedstawić uzyskane wyniki w postaci mapy.

Dodatkowo utworzono warstwę wektorową zawierającą poligony i przeprowadzono analizę statystyk strefowych z wykorzystaniem narzędzia Zonal Statistics.

Wykonane ćwiczenia pozwoliły utrwalić wiedzę zdobytą podczas wcześniejszego laboratorium oraz rozszerzyć ją o analizę danych wektorowych i statystyczne opracowanie wyników.

## 7. Źródła

- [Geoportal Krajowy](https://www.geoportal.gov.pl/) – źródło ortofotomapy CIR z 2025 roku.
- [QGIS](https://qgis.org/) – oprogramowanie wykorzystane do analizy danych przestrzennych.
- [Dokumentacja QGIS](https://docs.qgis.org/) – dokumentacja narzędzi analizy rastrowej i statystyk strefowych.
