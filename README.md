# Projekt_pogladowy_Arkadiusz_Kozlowski

<img width="1299" height="741" alt="image" src="https://github.com/user-attachments/assets/45c0397b-8372-4f9a-b07b-8363fb97c4cd" />

# Walmart Retail Sales Analysis - Power BI Dashboard

## 📌 O projekcie

Projekt przedstawia interaktywny dashboard analityczny zbudowany w programie **Power BI**, oparty na historycznych danych sprzedażowych sieci detalicznej Walmart.

Głównym celem biznesowym projektu jest analiza wydajności sprzedaży, identyfikacja kluczowych trendów w czasie, zbadanie wpływu dni świątecznych na przychody oraz weryfikacja korelacji między wynikami sklepów a czynnikami makroekonomicznymi (inflacja/CPI). Projekt został zrealizowany jako demonstracja pełnego procesu analitycznego: od pobrania i oczyszczenia surowych danych, przez modelowanie, aż po wizualizację (Business Intelligence).

## 🛠 Wykorzystane technologie i narzędzia

* **Narzędzie główne:** Power BI Desktop
* **Proces ETL:** Power Query
* **Język obliczeniowy:** DAX (Data Analysis Expressions)
* **Źródło danych:** Zbiór "Walmart Sales in Retail" (Kaggle) - plik CSV / Excel

## ⚙️ Metodologia i etapy pracy (Data Pipeline)

**1. Pobieranie i transformacja danych (ETL - Power Query)**

* Import surowego pliku płaskiego z zachowaniem odpowiednich ustawień regionalnych (parsowanie amerykańskich formatów liczbowych).
* Czyszczenie danych, weryfikacja typów kolumn oraz transformacja wartości binarnych (np. przekształcenie kolumny `Holiday_Flag` na czytelne kategorie biznesowe: "Tydzień świąteczny" / "Zwykły tydzień").

**2. Modelowanie Danych (Data Modeling)**

* Odejście od płaskiej tabeli na rzecz modelu relacyjnego.
* Zbudowanie dedykowanej tabeli wymiaru `Kalendarz` za pomocą języka DAX w celu poprawnej obsługi analizy w czasie (Time Intelligence).
* Utworzenie aktywnej relacji typu **jeden do wielu (1:*)** pomiędzy tabelą kalendarza a tabelą faktów sprzedaży.

**3. Obliczenia analityczne (DAX)**
Utworzenie zestawu dynamicznych miar (Measures) dostosowujących się do kontekstu filtrowania, m.in.:

* `Łączna sprzedaż ($)` - suma wszystkich wygenerowanych przychodów.
* `Średnia sprzedaż tygodniowa ($)` - uśredniona wartość przychodów na tydzień.
* `Liczba sklepów` - unikalna liczba badanych placówek.

**4. Wizualizacja Danych (Data Visualization)**

* **Karty KPI:** Błyskawiczny pogląd na najważniejsze liczby biznesowe.
* **Wykres liniowy:** Monitorowanie trendu sprzedaży w ujęciu wieloletnim z możliwością drążenia danych (Drill-down) do poziomu miesięcy/kwartałów.
* **Wykres kolumnowy:** Wykazanie różnicy w średniej sprzedaży między tygodniami ze świętami a zwykłymi tygodniami.
* **Wykres punktowy (Scatter plot):** Zbadanie korelacji między sumą sprzedaży a poziomem wskaźnika CPI (Consumer Price Index).
* **Filtry (Slicers):** Dynamiczne filtrowanie całego raportu po numerze konkretnego sklepu (Store).

## 💡 Kluczowe wnioski biznesowe (Insights)

* **Sezonowość:** Wykres trendu wyraźnie wskazuje powtarzalne piki sprzedażowe w określonych miesiącach (czwarty kwartał), co jest kluczowe dla planowania łańcucha dostaw.
* **Wpływ świąt:** Dane potwierdzają zauważalną różnicę w średnich przychodach podczas tygodni oznaczonych jako świąteczne w porównaniu do standardowego okresu.
* **Czynniki makro:** Zestawienie wskaźnika CPI ze sprzedażą na wykresie punktowym pozwala zaobserwować, jak zmiany inflacyjne przekładają się na skłonność konsumentów do zakupów.

## 📂 Struktura repozytorium

* **Walmart_Sales_Analysis.pbix – Główny plik modelu relacyjnego i raportu Power BI.

* **Walmart_Sales.csv – Surowy zbiór danych pobrany z platformy Kaggle.

