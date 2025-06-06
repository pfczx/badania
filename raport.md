# Wprowadzenie
Projekt przedstawia problem wielokryterialny jakim jest wybór systemu operacyjnego dla studenta informatyki. Odpowiednio dobrany system operacyjny stanowi solidny fundament do zbudowania odpowiedniej wiedzy i umiejętności informatyka. Warto zaznaczyć, że powinno zapoznać się z podstawowymi funkcjonalnościami każdego z nich, ale zazwyczaj bazuje się na jednym. Systemy, które będą porównywane w badaniu znacznie różnią się tym co oferują swoim użytkownikom, tym bardziej ważne jest by znaleźć  te cechy, które pozwolą na opis każdego. Nasz zespół wybrał 10 kryteriów spośród wielu by przypisać badanym systemom wartości możliwe do porównania.
# Opis problemu
#tu dodac jakie systemy mozna wyvrac (dlaczegop te ktore mamy) dlczego i jakie sa kryteria itd

# Metodyki
W celu rozwiązania problemu dla każdego systemu przypisaliśmy odpowiednie wartości (0-9) dla każdej kategorii. To jaka wartość została nadana zależy od benchmarków, oceny własnej lub wypowiedzi użytkowników serwisów tematycznych. Każdej z kategorii przy pomocy metody AHP (Analytic Hierarchy Process) przypisano odpowiednią wagę. Następnie wykorzystaliśmy metodę TOPSIS (Technique for Order Preference by Similarity to Ideal Solution) by wyłonić najlepszy system.
# Model 
#opisac ten model formalny cos jak f-> min itd tak jak na zajeciach, opisac ahp i topsisa na naszych danych
#dodac model z r 
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
print(weights$weighting)
print(weights$Saaty)
```
Ustalenie najlepszego systemu operacyjnego za pomocą TOPSIS
```r
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
| **Stabilność / awaryjność**   |      0.21707540    |    7    |   6     |    6     |   8    |
| **Wydajność**                 |     0.05497388     |    6    |    8    |     3    |    7   |
| **Bezpieczeństwo**            |     0.05497388     |     8   |    8    |    6     |     8  |
| **Łatwość obsługi**           |     0.03274678     |     5   |     4   |     9    |    7   |
| **Dostępność oprogramowania** |      0.05497388    |     6   |     6   |    9     |     8  |
| **Narzędzia deweloperskie**   |      0.21707540    |    8    |     9   |      6   |     8  |
| **Wsparcie / społeczność**    |    0.03274678      |    8    |     6   |    8     |     8  |
| **Kompatybilność ze sprzętem**|     0.05497388     |     7   |    7    |     9    |    5   |
| **Koszt licencji**            |      0.14023006    |     9   |    9    |     4    |    2   |
| **Personalizacja**            |      0.14023006    |     7   |    9    |      4  |    5   |






