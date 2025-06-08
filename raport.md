# Wprowadzenie
Projekt przedstawia problem wielokryterialny jakim jest wybór systemu operacyjnego dla studenta informatyki. Odpowiednio dobrany system operacyjny stanowi solidny fundament do zbudowania odpowiedniej wiedzy i umiejętności informatyka. Warto zaznaczyć, że powinno zapoznać się z podstawowymi funkcjonalnościami każdego z nich, ale zazwyczaj bazuje się na jednym. Systemy, które będą porównywane w badaniu znacznie różnią się tym co oferują swoim użytkownikom, tym bardziej ważne jest by znaleźć  te cechy, które pozwolą na opis każdego. Nasz zespół wybrał 10 kryteriów spośród wielu by przypisać badanym systemom wartości możliwe do porównania.
# Opis problemu
Na rynku dostępne są następujące systemu operacyje: 
- System Windows firmy Microsoft, najbardziej popularny wybór, to na tym systemie ludzie uczą się korzystać z komputera. Stosunkowo intuicyjny, jednak posiadający swoje mankamenty, które zaczynają być zauważane nie tylko przez informatyków, ale także zwyczajnych użytkowników.
- System macOS firmy Apple, w użytkowaniu podobny do produktu firmy Microsoft, elegancki i intuicyjny. Istotną cechą tego systemu jest fakt, iż przeznaczony jest on tylko i wyłącznie na urządzenia firmy Apple, co zapewnia wysoki poziom integracji sprzętu i oprogramowania. Z powodu ograniczenia dystrybucji tego systemu wielu użytkowników nie może pozwolić sobie na choć przetestowanie tej propozycji.
- System Linux, a raczej rodzina jego dystrybucji jest przykładem wolnego i otwartego oprogramowania. Jego kod źródłowy jest ogólnodostępny, a system jest darmowy. Każda z dystrubucji systemu jest inna co zapewnia, że każdy konsument znajdzie odpowiednią wersję. Linux oferuje wysoką wydajność, personalizację oraz cenioną przez wielu wolność od korporacji. Wadą tego systemu jest ograniczony dostęp do oprogramowania, jednak z powodu rosnącej społeczności budującej Linux'a pojawiają się nowe rozwiązania poprawiające doświadczenia z korzystania z tego systemu. Z powodu na różnorodność zdecydowaliśmy się na wybranie dwóch dystrybucji - Ubuntu oraz Fedora.

# Metodyki
W celu rozwiązania problemu dla każdego systemu przypisaliśmy odpowiednie wartości (0-9) dla każdej kategorii. To jaka wartość została nadana zależy od benchmarków, oceny własnej lub wypowiedzi użytkowników serwisów tematycznych. Każdej z kategorii przy pomocy metody AHP (Analytic Hierarchy Process) przypisano odpowiednią wagę. Następnie wykorzystaliśmy metodę TOPSIS (Technique for Order Preference by Similarity to Ideal Solution) by wyłonić najlepszy system.
# Model 
#opisac ten model formalny cos jak f-> min itd tak jak na zajeciach, opisac ahp i topsisa na naszych danych
### AHP (Analytic Hierarchy Process):
**1) Decyzja zostaje rozbita na hierarchię składającą się z:**
- celu głównego, w naszym przypadku wybrania najlepszego systemu operacyjnego
- kryteriów, przedstawionych w poniższej tabeli
- podkryteriów (opcjonalne)
- alternatyw (kandydatów)

**2) Porównanie kryteriów.**
Zapisane w tablicy kryteria porównujemy parami przypisyjąc im znaczenie w skali Saaty'ego. 
* 1: równie ważne
* 3: umiarkowanie ważniejsze
* 5: zdecydowanie ważniejsze
* 7: bardzo silnie ważniejsze
* 9: absolutnie ważniejsze
Oto przykład tego kroku dla wyboru telewizora.
 
|               | Cena | Rozmiar | Rozdzielczość |                  
|---------------|------|---------|---------------|
| Cena          |   1  |    3    |       7       |
| Rozmiar       |  1/3 |    1    |       5       |
| Rozdzielczość |  1/7 |   1/5   |       1       |

Dla osoby wybierającej telewizor *rozmiar* jest zdecydowanie ważniejszy niż *rozdzielczość*, więc w pole rozmiar/rozdzilczość wpisujemy 5, a w pole odwrotne - odwrotność liczby 5.




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

Na podstawie analizy metodą TOPSIS, systemy Ubuntu i Fedora uzyskały najwyższe oceny, co wskazuje na ich wysoką ogólną jakość w kontekście zdefiniowanych kryteriów. Ubuntu osiągnęło najwyższy wynik , wyprzedzając Fedorę  jedynie nieznacznie, co oznacza, że oba systemy oferują bardzo zbliżony poziom atrakcyjności. Windows uplasował się na trzecim miejscu (0.4260), głównie dzięki dobremu wynikowi w łatwości obsługi oraz kompatybilności. MacOS uzyskał najniższy wynik, co może wynikać z jego relatywnie wysokiego kosztu oraz ograniczonej możliwości personalizacji. Warto zauważyć, że najwyższe wagi przypisano kryteriom stabilności i narzędzi deweloperskich, w których zarówno Ubuntu, jak i Fedora uzyskały bardzo dobre oceny. Ostateczny ranking potwierdza, że systemy open-source — szczególnie Ubuntu — najlepiej spełniają potrzeby studenta informatyki przy uwzględnieniu najistotniejszych kryteriów decyzyjnych.

# Analiza wrażliwości
#dodac analize wlsciwosci i opisac ja dokladnie z radami dla decydenta jesli np potrzbuje czegos innego troche itd policzyc ale nie wklejac juz wiecej kodu do prezentacji dorobic to w r

#dodac jakies rzeczy ktorych moglem zapomniec 
#upiekszyc dodac np zdjecia czy zrzut ekranu systemow podopisywac cos ewentualnie

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
