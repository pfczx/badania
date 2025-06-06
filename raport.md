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
```
Ustalenie najlepszego systemu operacyjnego za pomocą TOPSIS
```r
```
# Porównania dla AHP
### 1. Stabilność

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Stabilność** | 1 | 2 | 3 | 4 | 2 | 3 | 2 | 3 | 4 | 5 |

---

### 2. Wydajność

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Wydajność** | 0.5 | 1 | 2 | 3 | 2 | 2 | 1 | 2 | 3 | 4 |

---

### 3. Bezpieczeństwo

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Bezpieczeństwo** | 0.3333333333333333 | 0.5 | 1 | 2 | 1 | 2 | 1 | 1 | 2 | 3 |

---

### 4. Łatwość obsługi

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Łatwość obsługi** | 0.25 | 0.3333333333333333 | 0.5 | 1 | 1 | 1 | 1 | 1 | 2 | 2 |

---

### 5. Oprogramowanie

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Oprogramowanie** | 0.5 | 0.5 | 1 | 1 | 1 | 2 | 2 | 1 | 2 | 3 |

---

### 6. Narzędzia

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Narzędzia** | 0.3333333333333333 | 0.5 | 0.5 | 1 | 0.5 | 1 | 1 | 1 | 2 | 2 |

---

### 7. Społeczność

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Społeczność** | 0.5 | 1 | 1 | 1 | 0.5 | 1 | 1 | 1 | 2 | 2 |

---

### 8. Kompatybilność

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Kompatybilność** | 0.3333333333333333 | 0.5 | 1 | 1 | 1 | 1 | 1 | 1 | 2 | 2 |

---

### 9. Koszt

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Koszt** | 0.25 | 0.3333333333333333 | 0.5 | 0.5 | 0.5 | 0.5 | 0.5 | 0.5 | 1 | 2 |

---

### 10. Personalizacja

| Kryterium     | Stabilność | Wydajność | Bezpieczeństwo | Łatwość obsługi | Oprogramowanie | Narzędzia | Społeczność | Kompatybilność | Koszt | Personalizacja |
|---------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Personalizacja** | 0.2 | 0.25 | 0.3333333333333333 | 0.5 | 0.3333333333333333 | 0.5 | 0.5 | 0.5 | 0.5 | 1 |

---



# Ocena liczbowa dla systemów
| Kryterium                     | Waga (%) | Ubuntu | Fedora | Windows | macOS |
|-------------------------------|:----------:|:--------:|:--------:|:---------:|:-------:|
| **Stabilność / awaryjność**   |          |    7    |   6     |    6     |   8    |
| **Wydajność**                 |          |    6    |    8    |     3    |    7   |
| **Bezpieczeństwo**            |          |     8   |    8    |    6     |     8  |
| **Łatwość obsługi**           |          |     5   |     4   |     9    |    7   |
| **Dostępność oprogramowania** |          |     6   |     6   |    9     |     8  |
| **Narzędzia deweloperskie**   |          |    8    |     9   |      6   |     8  |
| **Wsparcie / społeczność**    |          |    8    |     6   |    8     |     8  |
| **Kompatybilność ze sprzętem**|          |     7   |    7    |     9    |    5   |
| **Koszt licencji**            |          |     9   |    9    |     4    |    2   |
| **Personalizacja**            |          |     7   |    9    |      4  |    5   |






