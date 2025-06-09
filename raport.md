# Opis problemu
Projekt przedstawia problem wielokryterialny jakim jest wybór systemu operacyjnego dla studenta informatyki. Odpowiednio dobrany system operacyjny stanowi solidny fundament do zbudowania odpowiedniej wiedzy i umiejętności informatyka. Warto zaznaczyć, że powinno zapoznać się z podstawowymi funkcjonalnościami każdego z nich, ale zazwyczaj bazuje się na jednym. Systemy, które będą porównywane w badaniu znacznie różnią się tym co oferują swoim użytkownikom, tym bardziej ważne jest by znaleźć  te cechy, które pozwolą na opis każdego. Nasz zespół wybrał 10 kryteriów spośród wielu by przypisać badanym systemom wartości możliwe do porównania.

# Alternatywy decyzyjne

Rozważane są cztery możliwe systemy operacyjne:

- **Ubuntu** – popularna dystrybucja Linuxa oparta na Debianie, znana z łatwości obsługi i szerokiej społeczności.
- **Fedora** – nowoczesna dystrybucja Linuxa wspierana przez Red Hat, często stosowana do nauki i testowania nowych technologii.
- **Windows** – system firmy Microsoft, powszechnie wykorzystywany w edukacji i przemyśle.
- **macOS** – system operacyjny Apple, używany głównie na sprzęcie Mac, ceniony za stabilność i środowisko programistyczne dla iOS/macOS.



# Kryteria oceny alternatyw

Każda alternatywa zostanie oceniona względem następujących kryteriów:

 Kryterium                | Opis |
--------------------------|--------------------|
 Stabilność               | Odporność systemu na awarie, stabilność działania w czasie. |
 Wydajność                 | Efektywność działania na sprzęcie studenckim, zarządzanie zasobami. |
 Bezpieczeństwo           |  Wbudowane mechanizmy ochrony danych i systemu przed zagrożeniami. |
 Łatwość obsługi          |  Intuicyjność interfejsu i niski próg wejścia. |
 Oprogramowanie           |  Dostępność aplikacji użytkowych i pakietów biurowych. |
 Narzędzia programistyczne|  Dostępność specyficznych narzędzi programistycznych. |
 Społeczność i wsparcie   |  Dostępność forów, dokumentacji, tutoriali, aktywność społeczności. |
 Kompatybilność           |  Możliwość współpracy z innymi systemami, sprzętem i platformami. |
 Koszt                    |  Całkowity koszt systemu i sprzętu wymaganego do jego uruchomienia. |
 Personalizacja           |  Możliwość modyfikacji systemu pod własne potrzeby. |



# Cel decyzyjny i model problemu

Celem decydenta (studenta informatyki) jest wybranie takiego systemu operacyjnego, który najlepiej spełnia jego oczekiwania względem powyższych kryteriów.

Formalizacja:

- Zbiór alternatyw: `A = {Ubuntu, Fedora, Windows, macOS}`
- Zbiór kryteriów: `K = {K1, K2, ..., K10}`

Dla każdej alternatywy `Ai` wyznaczamy wektor ocen `(k_i1, k_i2, ..., k_i10)`.

 Funkcja oceny (metoda wagowa)

```math
U(A_i) = ∑(w_j * k_ij)
```
Gdzie:

- ` w_j ` – waga przypisana kryterium ` K_j `, wyrażająca jego względną ważność,
- ` k_{ij} `– ocena alternatywy ` A_i ` względem kryterium ` K_j `,
- ` U(A_i) ` – suma ważona ocen dla alternatywy `A_i `.

Alternatywa, która uzyska najwyższy wynik ` U(A_i) `, uznawana jest za najlepszą.

# Założenia problemu

W analizie przyjmuje się następujące założenia:

- Student potrafi korzystać z każdego z ocenianych systemów operacyjnych.
- Wszystkie systemy są dostępne dla użytkownika (technicznie możliwe do zainstalowania i używania).
- Preferencje decydenta można odwzorować poprzez przypisanie wag kryteriom.
- Kryteria są wzajemnie niezależne, rozłączne i kompletne.



# Możliwe rozszerzenia problemu

Problem decyzyjny można rozszerzyć o dodatkowe aspekty:

- **Plany zawodowe studenta** (np. chęć tworzenia aplikacji iOS może premiować macOS),
- **Specyfika zajęć na uczelni** (np. wymagane środowiska programistyczne),
- **Sprzętowe ograniczenia użytkownika** (RAM, CPU, dysk, dostępność komputera Mac),
- **Dynamika technologiczna** – aktualizacje, nowe wersje, zmieniające się potrzeby użytkownika.


# Metodyki
W celu rozwiązania problemu dla każdego systemu przypisaliśmy odpowiednie wartości (1-9) dla każdej kategorii. To jaka wartość została nadana zależy od benchmarków, oceny własnej lub wypowiedzi użytkowników serwisów tematycznych. Każdej z kategorii przy pomocy metody AHP (Analytic Hierarchy Process) przypisano odpowiednią wagę. Następnie wykorzystaliśmy metodę TOPSIS (Technique for Order Preference by Similarity to Ideal Solution) by wyłonić najlepszy system.

### AHP (Analytic Hierarchy Process):
Decyzja zostaje rozbita na hierarchię składającą się z:
- celu głównego, w naszym przypadku wybrania najlepszego systemu operacyjnego
- kryteriów, przedstawionych w poniższej tabeli
- podkryteriów (opcjonalne)
- alternatyw (kandydatów)

**Skala Saaty'ego**
Zapisane w tablicy kryteria porównujemy parami przypisyjąc im znaczenie w skali Saaty'ego. 
* 1: równie ważne
* 3: umiarkowanie ważniejsze
* 5: zdecydowanie ważniejsze
* 7: bardzo silnie ważniejsze
* 9: absolutnie ważniejsze
Oto działanie AHP, krok po kroku. 
 
|    Kryteria   | Koszt | Wydajność | Stabilność |                  
|---------------|------|---------|---------------|
| Koszt          |   1  |    4    |       2       |
| Wydajność       |  1/4 |    1    |       1/3       |
| Stabilność |  1/2 |   3   |       1       |

Dla osoby wybierającej system *koszt* jest umiarkowanie ważniejszy niż *wydajność*, więc w pole koszt/wydajność wpisujemy 3, a w pole odwrotne - odwrotność liczby 3.
Następnie liczby ułamkowe zostają przekonwertowane na liczby dziesiętne a dla każdej kolumny obliczna jest ich suma. 

|    Kryteria   | Koszt | Wydajność | Stabilność |                    
|---------------|------|---------|---------------|
| Koszt          |   1  |    4    |       2       |
| Wydajność       |  0,25 |    1    |       0,33       |
| Stabilność | 0,5 |   3   |       1       |
| Suma          | 1,75 |   8   |       3,3      |

Każdy z elementów tabeli jest dzielony przez sumę swojej kolumny, a następnie obliczana jest średnia dla każdego rzędu, która jest naszą wagą.


|    Kryteria   | Koszt | Wydajność | Stabilność |    Waga |               
|---------------|------|---------|---------------|-------|
| Koszt          |   0,57  |    0,5  |       0,6       | 0,56 |
| Wydajność       |  0,14 |   0,13    |       0,1       | 1,22 |
| Stabilność | 0,29 |   0,38   |       0,3       | 0,32 |

W kolejnym kroku mnożymy wartości komórek razy wagę i sumujemy wiersze.


|    Kryteria   | Koszt | Wydajność | Stabilność  |    Suma / Waga |
|---------------|-------------|------------|---------------|--------|
| Waga | 0,56 | 1,22 | 0,32 |  |  |
| Koszt          | 0,57 * 0,56        | 0,13 * 1,22        |     0,6 * 0,32     | 1,03    |
| Wydajność       | 0,14 * 0,56  | 1 * 1,22   |       0,1 * 0,32 |     1,04  |
| Stabilność | 0,29 * 0,56 | 0,38  * 1,22 |        0,3 * 0,32|   0,94   |

Następnie obliczamy *Consistency Index* (C.I.). 
![image](https://github.com/user-attachments/assets/ec153b32-734f-4bdc-b58d-f60d25fdef31)
gdzie
λmax to średnia wartości **Suma * Waga** każdego wiersza, a **n** to liczba kryteriów. 

Consistency Ratio = CI/RI (Random Index)

Tablica Random Index

| n   | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   |
|-----|------|------|------|------|------|------|------|------|------|------|
| RI  | 0.00 | 0.00 | 0.58 | 0.90 | 1.12 | 1.24 | 1.32 | 1.41 | 1.45 | 1.49 |

Jeśli CR jest mniejsze od 0.1, możemy założyć, że nasza macierz jest spójna.

### TOPSIS
|Atrybut | Koszt |Wydajność | Stabilność | 
|------------------------|---------------|----------------|--------|
| Ubuntu          |    9      | 7          |6  | 
| Fedora         | 9    | 5        | 8 | 
| Windows         | 4    | 6          | 9 | 
| macOS         |  4        | 3          | 7  |
| **Σ X^2**           | **194**   | **119**    | **77** |

By otrzymać znormalizowaną macierz decyzji, dzielimy wartości pól przez sumy ich kolumn. Następnie mnożymy razy wagi. 

|Atrybut |  Koszt |Wydajność | Stabilność | 
|------------------------|---------------|----------------|--------|
| Waga | 0,33  | 0,33  | 0,33 | 
| Ubuntu         | 9 / Σ X^2 * Waga         | 7 / Σ X^2 * Waga         | 6 / Σ X^2 * Waga  | 
| Fedora           | 9 / Σ X^2 * Waga         | 5 / Σ X^2 * Waga  | 8 / Σ X^2 * Waga   | 
| Windows          | 4 / Σ X^2 * Waga     | 6 / Σ X^2 * Waga  | 9 / Σ X^2 * Waga  | 
| macOS          |  4 / Σ X^2 * Waga   | 3 / Σ X^2 * Waga          | 7 / Σ X^2 * Waga |  


W ten sposób otrzymujemy znormalizowaną, ważoną macierz decyzji, dla każdej kolumny określamy V+j (najwyższą wartość) oraz V-j (najniższą wartość) i na ich podstawie obliczamy odległość euklidesową.

![image](https://github.com/user-attachments/assets/072b3798-6a68-4dc1-9b23-4d1ce63efaa5)

Oraz obliczamy *Performance Score*

![image](https://github.com/user-attachments/assets/116f05ec-a8c9-45c3-9e6d-e88d2b840d7c)


|Atrybut |  Koszt |Wydajność | Stabilność |  S⁺ | S⁻ | Pi |
|---------|-------|----------|------------|------|-----|-----| 
| Ubuntu  | 0.015309| 0.019412| 0.025714| 0       | 0.018992| 0.018992| 1       |        
| Fedora  | 0.015309| 0.013866| 0.012857| 0.014002| 0.010154| 0.024156| 0.420338|    
| Windows     | 0.006804| 0.016639| 0.017143| 0.012389| 0.009358| 0.021748| 0.430313|         
| macOS     | 0.006804| 0.008319| 0.017143| 0.016397| 0.004286| 0.020682| 0.207216|         
| V⁺ⱼ     | 0.015309| 0.019412| 0.025714|         |         |         |         |         
| V⁻ⱼ     | 0.006804| 0.008319| 0.012857|         |         |         |         |         


Po tych obliczeniach możemy posortować nasze alternatywy po *Performance score* i otrzymać najlepszy wybór. Jak widać ograniczając się do 3 kryteriów, Ubuntu deklasuje inne opcje. 


Wykorzystanie AHP do ustalenia wag w kategoriach
```r
m <- matrix(c(
  # Kryteria:   Sta  Wyd  Bez  Obs  Opr  Narz Społ Komp Koszt Pers
  1,            4,   4,   5,   4,   1,   5,   4,   2,   2,      # Stabilność
  
  1/4,          1,   1,   2,   1,   1/4, 2,   1,   1/3, 1/3,    # Wydajność
  
  1/4,          1,   1,   2,   1,   1/4, 2,   1,   1/3, 1/3,    # Bezpieczeństwo

  1/5,          1/2, 1/2, 1,   1/2, 1/5, 1,   1/2, 1/4, 1/4,    # Łatwość obsługi
  
  1/4,          1,   1,   2,   1,   1/4, 2,   1,   1/3, 1/3,    # Oprogramowanie
  
  1,            4,   4,   5,   4,   1,   5,   4,   2,   2,      # Narzędzia
  
  1/5,          1/2, 1/2, 1,   1/2, 1/5, 1,   1/2, 1/4, 1/4,    # Społeczność
  
  1/4,          1,   1,   2,   1,   1/4, 2,   1,   1/3, 1/3,    # Kompatybilność
  
  1/2,          3,   3,   4,   3,   1/2, 4,   3,   1,   1,      # Koszt
  
  1/2,          3,   3,   4,   3,   1/2, 4,   3,   1,   1       # Personalizacja
), nrow = 10, byrow = TRUE)

weights <- ahp(m)

```
Ustalenie najlepszego systemu operacyjnego za pomocą TOPSIS
```r

#Topsis
decision_matrix <- matrix(c(
  7, 6, 9, 5, 5, 8, 8, 7, 9, 7,     # Ubuntu
  5, 8, 9, 4, 5, 9, 6, 7, 9, 9,     # Fedora
  6, 3, 3, 9, 9, 4, 6, 9, 4, 4,     # Windows
  9, 7, 8, 6, 8, 7, 6, 3, 2, 5      # macOS
), nrow = 4, byrow = TRUE)

alternatives <- c("Ubuntu", "Fedora", "Windows", "macOS")

#Normalizacja 
norm_matrix <- decision_matrix / sqrt(colSums(decision_matrix^2))

#Pomnożenie przez wagi
weighted_matrix <- norm_matrix * as.numeric(weights$weighting)

#Ideał (max) i antyideał (min)
ideal_best <- apply(weighted_matrix, 2, max)
ideal_worst <- apply(weighted_matrix, 2, min)

#Dystanse do ideału i antyideału
distance_to_best <- sqrt(rowSums((weighted_matrix - matrix(ideal_best, nrow=4, ncol=10, byrow=TRUE))^2))
distance_to_worst <- sqrt(rowSums((weighted_matrix - matrix(ideal_worst, nrow=4, ncol=10, byrow=TRUE))^2))

#Wartość TOPSIS
topsis_score <- distance_to_worst / (distance_to_best + distance_to_worst)

#Ranking
ranking <- order(topsis_score, decreasing = TRUE)

#Wyniki
result <- data.frame(
  System = alternatives,
  TopsisScore = topsis_score
)

```
# Porównania dla AHP
### 1.Stabilność / awaryjność

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Stabilność** | 1 | 4 | 4 | 5 | 4 | 1 | 5 | 4 | 2 | 2 |

---

### 2. Wydajność

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Wydajność** | 1/4 | 1 | 1 | 2 | 1 | 1/4 | 2 | 1 | 1/3 | 1/3 |

---

### 3. Bezpieczeństwo

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Bezpieczeństwo** | 1/4| 1 | 1 | 2 | 1 | 1/4 | 2 | 1 | 1/3| 1/3 |

---

### 4. Łatwość obsługi

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Łatwość obsługi** | 1/5 | 1/2 | 1/2 | 1 | 1/2 | 1/5 | 1 | 1/2 | 1/4 | 1/4 |

---

### 5. Dostępność oprogramowania

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Oprogramowanie** | 1/4 |1| 1 | 2 | 1 | 1/4 | 2 | 1| 1/3 | 1/3 |

---

### 6. Narzędzia deweloperskie

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Narzędzia** | 1 |4 |4 | 5 |4 | 1 | 5 | 4 | 2 | 2 |

---

### 7. Wsparcie / społeczność

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Społeczność** | 1/5 | 1/2 | 1 | 1/2 | 1/5 | 1 | 1/2 | 1/2 | 1/4 | 1/4 |

---

### 8.Kompatybilność ze sprzętem

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Kompatybilność** | 1/4| 1 | 1 | 2 | 1 | 1/4 | 2 | 1 | 1/3 | 1/3 |

---

### 9. Koszt licencji

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Koszt** | 1/2 | 3 | 3 | 4 |3 | 1/2 |4 |3 | 1 | 1 |

---

### 10. Personalizacja

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Personalizacja** | 1/2| 3 | 3 | 4 | 3 | 1/2 | 4 | 3 | 1 | 1 |

---
Jakość porównań zmierzono współczynnikiem spójności Saatye`ego (Consistency Ratio).
W naszym przypadku wyniósł 0.008365929 co wskazuje na wysoką jakość udzielonych odpowiedzi.



# Ocena liczbowa dla systemów
| Kryterium                     | Waga (%) | Ubuntu | Fedora | Windows | macOS |
|-------------------------------|:----------:|:--------:|:--------:|:---------:|:-------:|
| **Stabilność / awaryjność**   |      0.21707540    |    7    |   5     |    6     |   9    |
| **Wydajność**                 |     0.05497388     |    6    |    8    |     3    |    7   |
| **Bezpieczeństwo**            |     0.05497388     |     9   |    9    |    3     |     8  |
| **Łatwość obsługi**           |     0.03274678     |     5   |     4   |     9    |    6   |
| **Dostępność oprogramowania** |      0.05497388    |     5   |     5   |    9     |     8  |
| **Narzędzia deweloperskie**   |      0.21707540    |    8    |     9   |      4   |     7  |
| **Wsparcie / społeczność**    |    0.03274678      |    8    |     6   |    6     |     6  |
| **Kompatybilność ze sprzętem**|     0.05497388     |     7   |    7    |     9    |    3   |
| **Koszt licencji**            |      0.14023006    |     9   |    9    |     4    |    2   |
| **Personalizacja**            |      0.14023006    |     7   |    9    |      4  |    5   |

# Wyniki
Na podstawie analizy TOPSIS uzyskaliśmy następujące wyniki:
| Rank | System | TOPSIS Score | 
|:------:|:----------:|:--------------:| 
| 1 | Ubuntu | 0.4898 |
| 2 | Fedora | 0.4797 |
| 3 | Windows | 0.4260 |
| 4 | macOS | 0.3392 |

Na podstawie analizy metodą TOPSIS, systemy Ubuntu i Fedora uzyskały najwyższe oceny, co wskazuje na ich wysoką ogólną jakość w kontekście zdefiniowanych kryteriów. Ubuntu osiągnęło najwyższy wynik , wyprzedzając Fedorę  jedynie nieznacznie, co oznacza, że oba systemy oferują bardzo zbliżony poziom atrakcyjności. Windows uplasował się na trzecim miejscu, głównie dzięki dobremu wynikowi w łatwości obsługi oraz kompatybilności. MacOS uzyskał najniższy wynik, co może wynikać z jego relatywnie wysokiego kosztu oraz ograniczonej możliwości personalizacji. Warto zauważyć, że najwyższe wagi przypisano kryteriom stabilności i narzędzi deweloperskich, w których zarówno Ubuntu, jak i Fedora uzyskały bardzo dobre oceny. Ostateczny ranking potwierdza, że systemy open-source — szczególnie Ubuntu — najlepiej spełniają potrzeby studenta informatyki przy uwzględnieniu najistotniejszych kryteriów decyzyjnych.

# Analiza wrażliwości

Przeanalizowaliśmy wrażliwość wyników na zmiany wag trzech kluczowych kryteriów: Bezpieczeństwo, Łatwość obsługi i Wydajność.

Ubuntu i Fedora utrzymują przewagę przy wszystkich wartościach wagi, macOS i Windows są wyraźnie słabsze w badanym kryterium. 
#upieks![Bezpieczenstwo](https://github.com/user-attachments/assets/d3cfd521-23bd-480c-bd2d-83bdccf0bd90)

Windows ma najlepsze wyniki w tym kryterium, przy dużym zwiększeniu wagi, Windows może zbliżyć się do liderów.
![Wydajnosc](https://github.com/user-attachments/assets/a56ae617-deaf-40a2-8ced-2a9625b6f5ff)

Fedora wyraźnie zyskuje przy zwiększeniu wagi wydajności. Ubuntu pozostaje konkurencyjne, ale traci część przewagi.
![Latwosc_Obslugi](https://github.com/user-attachments/assets/88c7022b-f35e-4608-b64a-edb0374de138)

# Rekomendacje dla decydenta
Dla użytkowników potrzebujących stabilności i bezpieczeństwa Ubuntu i Fedora będą najlepszym wyborem. (Ubuntu ma lekką przewagę w stabilności, Fedora w wydajności)
Dla użytkowników potrzebujących łatwej obsługi systemu najlepszym wyborem będzie Windows.
Dla użytkowników wymagających wysokiej wydajności Fedora staje się najlepszym wyborem.
macOS średnio wypada w większości kryteriów.

# Źródła
https://go.lightnode.com/tech/linux-fedora-vs-ubuntu
https://fedoraproject.org/wiki/Security_Features#:~:text=SELinux
https://www.inapps.net/ubuntu-vs-mac-os-2022/#:~:text=,and%20low%20vulnerability%20to%20viruses
https://blog.udemy.com/ubuntu-vs-windows/#:~:text=8,Cumbersome
https://blog.udemy.com/ubuntu-vs-windows/#:~:text=9.%20User
https://medium.com/@nomannayeem/choosing-the-right-os-mac-windows-or-linux-a-programmers-guide-2d128c40fc73
https://www.reddit.com/
https://www.phoronix.com/
https://discourse.ubuntu.com/
https://fedoraproject.org/
