# Laboratorium 1 – Wprowadzenie do QGIS i Copernicus Browser oraz analiza wskaźnika NDVI

## 1. Cel laboratorium

Celem pierwszego laboratorium było zapoznanie się z podstawowymi narzędziami wykorzystywanymi w analizie danych przestrzennych oraz zobrazowań satelitarnych.

W ramach zajęć skupiono się na przygotowaniu środowiska pracy, pozyskaniu danych satelitarnych z platformy Copernicus Browser oraz ich dalszym przetwarzaniu w programie QGIS.

Głównym zadaniem praktycznym było obliczenie wskaźnika NDVI (*Normalized Difference Vegetation Index*), który umożliwia ocenę stanu i intensywności roślinności na podstawie danych satelitarnych.

## 2. Wykorzystane narzędzia

Podczas realizacji laboratorium wykorzystano następujące narzędzia:

- **QGIS** – oprogramowanie GIS typu open source, umożliwiające wizualizację, przetwarzanie i analizę danych przestrzennych, w tym obrazów rastrowych.
- **Copernicus Browser** – internetową platformę umożliwiającą wyszukiwanie, przeglądanie oraz pobieranie zobrazowań satelitarnych pochodzących m.in. z satelitów Sentinel.
- **Dane satelitarne Sentinel-2** – zobrazowania wielospektralne wykorzystywane do obserwacji powierzchni Ziemi, monitorowania roślinności i analizy zmian środowiskowych.

## 3. Przebieg laboratorium

### 3.1. Instalacja i konfiguracja QGIS

Pierwszym etapem laboratorium było pobranie oraz zainstalowanie programu QGIS.

Instalacja zakończyła się powodzeniem, co umożliwiło rozpoczęcie pracy z danymi przestrzennymi. Zapoznano się z podstawowym interfejsem aplikacji, w szczególności z panelem warstw, obszarem mapy oraz narzędziami do obsługi danych rastrowych.

Program QGIS został przygotowany do dalszych działań związanych z importowaniem i analizą zobrazowań satelitarnych.

### 3.2. Logowanie do Copernicus Browser

Kolejnym etapem było uzyskanie dostępu do platformy Copernicus Browser.

Logowanie zakończyło się pomyślnie. Następnie zapoznano się z interfejsem platformy, możliwościami przeglądania zobrazowań satelitarnych oraz dostępnymi sposobami prezentacji danych wielospektralnych.

Platforma pozwala na analizowanie zobrazowań przy użyciu różnych kompozycji i kanałów spektralnych, co jest szczególnie przydatne podczas monitorowania powierzchni Ziemi.

### 3.3. Pobranie danych satelitarnych

W trakcie laboratorium udało się pobrać cztery rodzaje zobrazowań i danych z platformy Copernicus Browser:

**1. B04 – pasmo czerwone (Red)**

Pasmo B04 rejestruje promieniowanie elektromagnetyczne w zakresie światła czerwonego, w przybliżeniu przy długości fali 665 nm.

Jest ono wykorzystywane między innymi do analizowania roślinności oraz obliczania wskaźników spektralnych. Zdrowa roślinność stosunkowo silnie pochłania promieniowanie czerwone ze względu na obecność chlorofilu.

**2. B08 – pasmo bliskiej podczerwieni (NIR)**

Pasmo B08 odpowiada zakresowi bliskiej podczerwieni, w przybliżeniu 842 nm.

Jest szczególnie istotne w badaniach roślinności, ponieważ zdrowe liście zazwyczaj silnie odbijają promieniowanie w tym zakresie.

Połączenie informacji z pasm B04 i B08 umożliwia obliczenie wskaźnika NDVI.

**3. NDVI – znormalizowany różnicowy wskaźnik wegetacji**

Pobrano również zobrazowanie przedstawiające wskaźnik NDVI dostępny na platformie Copernicus Browser.

Wskaźnik ten pozwala na ocenę aktywności fotosyntetycznej i kondycji roślinności na podstawie różnicy pomiędzy odbiciem promieniowania w paśmie czerwonym i bliskiej podczerwieni.

**4. TRUE COLOR – kompozycja barw naturalnych**

Pobrano także zobrazowanie TRUE COLOR, przedstawiające powierzchnię Ziemi w kolorach zbliżonych do tych, które są widoczne dla ludzkiego oka.

Kompozycja powstaje poprzez połączenie trzech pasm satelitarnych:

- B04 – czerwonego (Red),
- B03 – zielonego (Green),
- B02 – niebieskiego (Blue).

Obraz TRUE COLOR ułatwia wizualną interpretację badanego obszaru i identyfikację takich elementów jak roślinność, zabudowa, zbiorniki wodne czy tereny niezagospodarowane.

## 4. Obliczanie wskaźnika NDVI w QGIS

Najważniejszym zadaniem analitycznym laboratorium było samodzielne obliczenie wskaźnika NDVI na podstawie pobranych pasm spektralnych.

Po wczytaniu danych B04 i B08 do programu QGIS wykonano obliczenia rastrowe, wykorzystując odpowiednią zależność matematyczną.

Wskaźnik NDVI obliczany jest według wzoru:

**NDVI = (NIR − RED) / (NIR + RED)**

Gdzie:

- **NIR** – wartość odbicia promieniowania w paśmie bliskiej podczerwieni (B08),
- **RED** – wartość odbicia promieniowania w paśmie czerwonym (B04).

Do przeprowadzenia obliczeń wykorzystano możliwości przetwarzania rastrów dostępne w programie QGIS.

Wynikiem przeprowadzonych działań była nowa warstwa rastrowa zawierająca obliczone wartości wskaźnika NDVI dla analizowanego obszaru.

### 4.1. Interpretacja wartości NDVI

Wskaźnik NDVI przyjmuje teoretycznie wartości od -1 do +1. Jego interpretacja pozwala określić charakterystykę pokrycia terenu oraz przybliżony stan roślinności.

| Wartość NDVI | Interpretacja |
|---|---|
| -1,0 do 0,0 | Najczęściej woda, śnieg, chmury lub inne powierzchnie niewykazujące typowej odpowiedzi spektralnej roślinności |
| 0,0 do 0,2 | Obszary pozbawione roślinności lub o niewielkim jej udziale |
| 0,2 do 0,4 | Roślinność rzadka lub o umiarkowanej aktywności |
| 0,4 do 0,6 | Roślinność o stosunkowo dobrej kondycji |
| 0,6 do 1,0 | Zazwyczaj gęsta, aktywna fotosyntetycznie roślinność |

Podane przedziały mają charakter orientacyjny. Interpretacja NDVI zależy również od pory roku, rodzaju roślinności, warunków atmosferycznych i specyfiki badanego terenu.

### 4.2. Wizualizacja wyników

Po wykonaniu obliczeń uzyskany raster NDVI został zaprezentowany w programie QGIS w postaci mapy.

Wizualizacja danych umożliwiła przestrzenne przedstawienie zróżnicowania wartości wskaźnika i pokazanie, w jaki sposób dane satelitarne mogą zostać wykorzystane do analizy roślinności.

Przygotowanie mapy stanowiło końcowy etap części praktycznej laboratorium.

## 5. Osiągnięte rezultaty

W ramach pierwszego laboratorium udało się zrealizować wszystkie podstawowe zadania:

- Pomyślnie pobrano i zainstalowano program QGIS.
- Uzyskano dostęp do platformy Copernicus Browser.
- Zapoznano się z podstawowymi funkcjonalnościami obu narzędzi.
- Pobrano cztery zobrazowania i produkty satelitarne: B04, B08, NDVI oraz TRUE COLOR.
- Wczytano dane satelitarne do środowiska QGIS.
- Samodzielnie obliczono wskaźnik NDVI na podstawie pasm B04 i B08.
- Uzyskany wynik przedstawiono w formie mapy.

## 6. Wnioski

Pierwsze laboratorium pozwoliło zdobyć podstawową wiedzę praktyczną dotyczącą pozyskiwania i przetwarzania danych satelitarnych.

Przeprowadzone ćwiczenia pokazały, że ogólnodostępne narzędzia, takie jak Copernicus Browser i QGIS, umożliwiają samodzielne wykonywanie analiz przestrzennych bez konieczności korzystania z komercyjnego oprogramowania.

Szczególnie istotnym elementem było poznanie zależności pomiędzy wartościami rejestrowanymi w różnych pasmach spektralnych a możliwością określania kondycji roślinności.

Obliczenie wskaźnika NDVI pozwoliło lepiej zrozumieć, w jaki sposób informacje pochodzące z obrazów satelitarnych mogą zostać przekształcone w dane przydatne do monitorowania środowiska.

Zdobyte umiejętności stanowią podstawę do dalszych zajęć związanych z teledetekcją, analizą obrazów satelitarnych oraz wykorzystaniem systemów informacji geograficznej (GIS).

## 7. Podsumowanie

**Laboratorium 1 zakończyło się pomyślnie.** Udało się przygotować środowisko pracy, pozyskać niezbędne dane satelitarne, wykonać obliczenia wskaźnika NDVI oraz zaprezentować otrzymane rezultaty na mapie w programie QGIS.

Przeprowadzone działania stanowią wprowadzenie do dalszej pracy z danymi satelitarnymi i analizami teledetekcyjnymi.
