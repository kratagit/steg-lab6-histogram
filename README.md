# steg-lab6-histogram

# Laboratorium 6

### Instructions

## Detekcja steganografii LSB przy użyciu analizy histogramu

### Cel zadania
Implementacja narzędzia w Pythonie lub MATLABie do detekcji steganografii LSB (Least Significant Bit) poprzez analizę histogramu obrazu.

### Kroki realizacji
1. Generowanie obrazów testowych: czysty i ze steganografią
2. Wczytywanie obrazu
3. Obliczanie histogramu dla każdego kanału koloru (R, G, B)
4. Wizualizacja histogramów
5. Implementacja prostej metryki do wykrywania anomalii w histogramach

### Algorytm
1. **Generowanie obrazów testowych:**
   * Utwórz czysty obraz o wymiarach 256x256 pikseli z losowymi wartościami.
   * Stwórz kopię obrazu i wprowadź do niej ukrytą wiadomość metodą LSB.
2. **Wczytywanie obrazu:**
   * Użyj odpowiedniej funkcji do wczytania obrazu (np. `imread` w MATLABie lub PIL w Pythonie).
3. **Obliczanie histogramu:**
   * Dla każdego kanału koloru (R, G, B) oblicz histogram wartości pikseli.
   * Zwróć uwagę na pary wartości (2i, 2i+1) dla i = 0, 1, ..., 127.
4. **Wizualizacja histogramów:**
   * Stwórz wykres słupkowy dla każdego kanału koloru.
   * Porównaj histogramy obrazu czystego i ze steganografią.
5. **Implementacja metryki detekcji:**
   * Oblicz sumę różnic bezwzględnych między sąsiednimi parzystymi i nieparzystymi wartościami histogramu.
   * Ustal próg, powyżej którego obraz zostanie uznany za zawierający ukryte dane.

### Kryteria akceptacji
1. Program poprawnie generuje obrazy testowe.
2. Histogramy są prawidłowo obliczane i wizualizowane.
3. Implementacja zawiera prostą metrykę do wykrywania anomalii w histogramach.
4. Program podaje jasną decyzję o obecności lub braku ukrytych danych.

### Przypadki testowe
1. **Test na czystym obrazie:**
   * Wejście: Wygenerowany czysty obraz
   * Oczekiwany wynik: Brak wykrycia steganografii
2. **Test na obrazie ze steganografią (25% pojemności):**
   * Wejście: Obraz z wbudowaną wiadomością LSB wykorzystującą 25% pojemności
   * Oczekiwany wynik: Wykrycie steganografii
3. **Test na obrazie rzeczywistym:**
   * Wejście: Rzeczywiste zdjęcie bez ukrytej wiadomości
   * Oczekiwany wynik: Brak wykrycia steganografii (z możliwymi fałszywymi alarmami)

### Dodatkowe uwagi
* Analiza histogramu jest szczególnie skuteczna w wykrywaniu sekwencyjnej steganografii LSB.
* Metoda może dawać fałszywe wyniki dla obrazów o nietypowych rozkładach histogramu.
* W przypadku obrazów kolorowych, należy rozważyć analizę każdego kanału osobno.
