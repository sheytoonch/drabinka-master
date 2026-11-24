# Drabinka Master - poprawki do samouczka

Stan wyjściowy: v2.1.8. Lista odczytana z kodu samouczka (src/modules/45-tutorial.js). Materiał roboczy, nie zatwierdzona specyfikacja.

Możesz zmieniać kolejność, łączyć, dzielić i usuwać lekcje oraz dopisywać nowe. Identyfikatory w nawiasach służą powiązaniu zmian z kodem i historią poznanych funkcji.

## Zasady wspólne - do uzupełnienia

- Kolejność grup i lekcji:
- Położenie okna samouczka:
- Kolejność przycisków:
- Co wskazywać obramowaniem, kiedy otwierać menu lub panel:
- Wygląd i rozmiar demonstracji:
- Tempo animacji i przerw:
- Zachowanie przy zapętleniu:
- Inne zasady:

Obecnie: obrys 3 px, jedno mignięcie (1200 ms), obrys pozostaje do zmiany kroku, o ile cel jest widoczny. Demonstracje: zwykły etap 1000 ms, ostatni 1700 ms, przeciąganie 750 ms, automatyczne zapętlenie. Przyciski lekcji: Wstecz, Pomiń, Dalej/Zakończ. Przyciski demonstracji: poprzedni etap, Od początku, następny etap. Systemowa preferencja ograniczenia ruchu wyłącza automatyczne odtwarzanie demonstracji.

# Lekcje - obecna kolejność GRAF

## Rozpoczęcie projektu

### 01. Nazwa projektu (`project-name`)

Obecny tekst: Kliknij podwójnie nazwę projektu, aby ją zmienić. Zacznij od nazwania swojej historii.

Obecny cel wskazania (selektor w kodzie): `.project-name`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 02. Dwa niezależne projekty (`workspace`)

Obecny tekst: Środek aplikacji to plansza wydarzeń. Po lewej znajduje się opis, po prawej podsumowanie, a na dole biblioteka etykiet. GRAF porządkuje wydarzenia według relacji, SIATKA według rozdziałów i wierszy. Przełącznik w górnym pasku otwiera drugi, niezależny projekt; nie konwertuje danych.

Obecny cel wskazania (selektor w kodzie): `.upper-scroll||[data-action="switch-project-type"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 03. Panele i przewijanie (`panels`)

Obecny tekst: Dostosuj przestrzeń roboczą przed rozpoczęciem pracy. Kliknij nagłówki OPIS, PODSUMOWANIE lub ETYKIETY, aby zwinąć albo rozwinąć panele. Przeciągnij krawędzie, aby zmienić ich rozmiary. Dolna szyna przewija planszę poziomo.

Obecny cel wskazania (selektor w kodzie): `.upper-head`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

## Bezpieczeństwo projektu

### 04. Autozapis i zamknięcie karty (`backup`)

Obecny tekst: Pomarańczowy dolny pasek oznacza niezapisane zmiany, zielony oznacza brak zmian od zapisu JSON. Przeglądarka przechowuje dane robocze, ale może je usunąć lub nadpisać. Przy zamykaniu karty może poprosić o potwierdzenie. Dlatego zapisuj projekt do JSON.

Obecny cel wskazania (selektor w kodzie): `.app-footer`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 05. Zapis projektu (`json`)

Obecny tekst: W Opcjach wybierz Eksport JSON (zapisz). Zachowaj pobrany JSON jako edytowalną kopię projektu.

Obecny cel wskazania (selektor w kodzie): `.toolbar-menu [data-action="export"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 06. Wczytanie projektu (`json-import`)

Obecny tekst: W Opcjach wybierz Import JSON (wczytaj), a następnie wskaż zapisany JSON. Przed zastąpieniem projektu zachowaj jego kopię.

Obecny cel wskazania (selektor w kodzie): `.toolbar-menu [data-action="import"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 07. PDF to wizualizacja (`pdf`)

Obecny tekst: Obok zapisu JSON znajdziesz Eksport PDF. To wizualizacja, nie kopia edytowalnego projektu. PDF nie zastępuje JSON.

Obecny cel wskazania (selektor w kodzie): `.toolbar-menu [data-action="export-pdf"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

## Budowanie fabuły

### 08. Wątki (`threads`)

Obecny tekst: Wątki to kolumny planszy. Dodaj wątek przyciskiem + obok nagłówków. Przeciągaj nagłówki, aby zmieniać kolejność; PPM otwiera opcje wątku. Puste wątki zajmują mniej miejsca.

Obecny cel wskazania (selektor w kodzie): `.head-clip`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 09. Rozdziały w GRAFIE (`graph-chapters`)

Obecny tekst: Włącz rozdziały w narzędziach GRAFU. Przyciski + na szynie wstawiają rozdział; zaznaczone wydarzenia można objąć rozdziałem. Przeciągnięcie do przestrzeni zmienia przypisanie.

Obecny cel wskazania (selektor w kodzie): `[data-action="graph-chapters"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 10. Tworzenie wydarzeń (`event-add`)

Obecny tekst: Kliknij podwójnie w wolnym miejscu planszy, aby dodać wydarzenie. Kliknij podwójnie kafelek, aby edytować jego treść. W GRAFIE możesz też użyć przycisków dodawania przy wątku.

Obecna prezentacja: miniatura na fikcyjnych danych, bez obramowania rzeczywistego projektu. Etapy:

1. Kliknij podwójnie w pustym miejscu.
2. Wpisz treść nowego wydarzenia.
3. Kliknij podwójnie kafelek, aby poprawić treść.
4. Zmieniona treść pozostaje na kafelku.

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 11. Edycja i przenoszenie (`event-menu`)

Obecny tekst: Gdy masz już wydarzenia, kliknij kafelek PPM, aby otworzyć jego menu. Przeciągnij go, aby zmienić położenie. Ctrl+Z i Ctrl+Y cofają i ponawiają zmiany.

Obecna prezentacja: miniatura na fikcyjnych danych, bez obramowania rzeczywistego projektu. Etapy:

1. Kliknij PPM na kafelku, aby zobaczyć menu.
2. Przeciągnij kafelek w inne miejsce.
3. Kafelek zmienia położenie.
4. Ctrl+Z przywraca poprzedni stan.

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 12. Relacje w GRAFIE (`graph-relations`)

Obecny tekst: Zaznacz dwa kafelki z różnych wątków (Ctrl lub Cmd) i użyj narzędzia łączenia. Relacje wcześniejsze/późniejsze i równoczesność wyznaczają chronologię. Aplikacja sprawdza konflikty.

Obecna prezentacja: miniatura na fikcyjnych danych, bez obramowania rzeczywistego projektu. Etapy:

1. Zaznacz dwa kafelki z różnych wątków.
2. Kliknij narzędzie łączenia i wybierz kolejność.
3. 1 przed 2: klucz przed otwarciem drzwi.
4. Na równi: oba wydarzenia w tym samym momencie.
5. Usuń połączenie: oba kafelki pozostają.

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 13. Podsumowanie z szyny rozdziałów (`rail-summary`)

Obecny tekst: Kliknij tytuł lub wolny fragment szyny na wysokości rozdziału, aby zobaczyć opis i statystyki. Kliknięcie przestrzeni między rozdziałami pokazuje jej wydarzenia i etykiety, bez opisu. + dodaje rozdział, a PPM na + pokazuje podsumowanie przerwy.

Obecny cel wskazania (selektor w kodzie): `.graph-chapter-rail||[data-action="graph-chapters"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 14. Rozdziały w SIATCE (`grid-chapters`)

Obecny tekst: W SIATCE przyciski + dodają rozdziały, a wiersze organizują wydarzenia. Rozdziały możesz zwijać i porządkować.

Obecny cel wskazania (selektor w kodzie): `.grid-rail-integrated .center-cap||.app:not(.graph-mode-active) .upper-scroll`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

## Etykiety

### 15. Biblioteka etykiet (`labels`)

Obecny tekst: Twórz kategorie i etykiety w dolnym panelu. Przeciągnij etykietę na kafelek. PPM > Edytuj zmienia jej nazwę, a PPM > Odepnij etykietę usuwa przypisanie bez usuwania jej z biblioteki. Opcja Usuń w bibliotece kasuje etykietę w całym projekcie.

Obecna prezentacja: miniatura na fikcyjnych danych, bez obramowania rzeczywistego projektu. Etapy:

1. Etykieta Trop znajduje się w bibliotece.
2. Przeciągnij etykietę z biblioteki na kafelek.
3. Etykieta jest przypięta do wydarzenia.
4. PPM na etykiecie > Edytuj.
5. Wpisz nową nazwę: Wskazówka.
6. Nowa nazwa pojawia się także na kafelku.
7. PPM na przypiętej etykiecie > Odepnij etykietę.
8. Przypisanie usunięte. Etykieta nadal jest w bibliotece.

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 16. Widoczność etykiet (`label-display`)

Obecny tekst: Etykiety pomagają odnaleźć powiązane wydarzenia. Tym przyciskiem możesz je ukryć lub pokazać na kafelkach, bez usuwania przypisań.

Obecny cel wskazania (selektor w kodzie): `[data-action="toggle-tile-labels"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 17. Wyszukiwanie w bibliotece etykiet (`dock-search`)

Obecny tekst: Wpisz nazwę etykiety lub kategorii w polu nad biblioteką. Filtr nie zmienia przypisań ani projektu. Wyczyść pole, aby pokazać wszystkie etykiety.

Obecny cel wskazania (selektor w kodzie): `.dock-search-input`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

## Notatki i encyklopedia

### 18. Notatki i encyklopedia (`notes`)

Obecny tekst: Przycisk książki otwiera wspólny panel dokumentacji. Notatki służą do własnych materiałów i pomysłów, a Encyklopedia zbiera hasła powiązane z etykietami.

Obecny cel wskazania (selektor w kodzie): `[data-action="notes-toggle"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 19. Praca z notatkami (`notes-edit`)

Obecny tekst: W zakładce Notatki przycisk + dodaje sekcję, np. pomysły lub plan świata. Spis treści pomaga poruszać się po dokumencie.

Obecny cel wskazania (selektor w kodzie): `.notes-widget.is-open [data-action="notes-add"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 20. Formatowanie notatek (`notes-format`)

Obecny tekst: Zaznacz tekst i użyj paska formatowania. Możesz dodawać nagłówki, listy i obrazy oraz przenosić obrazy myszą.

Obecny cel wskazania (selektor w kodzie): `.notes-widget.is-open .notes-formatbar`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 21. Encyklopedia projektu (`wiki-overview`)

Obecny tekst: Zakładka Encyklopedia grupuje hasła według kategorii etykiet. Każde hasło ma własny edytowalny opis, a spis treści pozwala szybko odnaleźć wpis.

Obecny cel wskazania (selektor w kodzie): `.notes-widget.is-open [data-tab="wiki"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 22. Przejście do wpisu encyklopedii (`wiki-jump`)

Obecny tekst: Każda nazwana etykieta ma odpowiadające jej hasło w encyklopedii. Kliknij etykietę PPM i wybierz „Pokaż w encyklopedii”. Aplikacja otworzy wpis i podświetli jego nagłówek.

Obecna prezentacja: miniatura na fikcyjnych danych, bez obramowania rzeczywistego projektu. Etapy:

1. PPM na etykiecie Wskazówka.
2. Wybierz Pokaż w encyklopedii.
3. Encyklopedia wskazuje właściwe hasło.

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 23. Kopiowanie i podświetlanie encyklopedii (`wiki-copy-select`)

Obecny tekst: W otwartej encyklopedii przycisk kopiowania u góry kopiuje wszystkie kategorie, hasła i opisy jako tekst. Możesz też kopiować kategorię lub wpis osobno. Kliknij nazwę hasła, aby wyróżnić etykietę i powiązane wydarzenia; ponowne kliknięcie wyłącza wyróżnienie.

Obecna prezentacja: miniatura na fikcyjnych danych, bez obramowania rzeczywistego projektu. Etapy:

1. Przypnij ponownie Wskazówkę do kafelka.
2. Kliknij nazwę hasła Wskazówka.
3. Powiązany kafelek i etykieta są wyróżnione.
4. Kopiuj wszystko: kategorie, hasła i opisy jako tekst.

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

## Nawigacja i widok

### 24. Wyszukiwanie (`search`)

Obecny tekst: Ctrl+F lub przycisk lupy pozwala wyszukać wydarzenia, wątki i etykiety. Kliknij wynik, aby przejść do wydarzenia.

Obecny cel wskazania (selektor w kodzie): `[data-action="search-toggle"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 25. Nawigator i minimapa (`navigator`)

Obecny tekst: Nawigator pomaga odnaleźć wydarzenia. W GRAFIE pokazuje sieć powiązań, a w SIATCE prowadzi po wydarzeniach. Możesz zmienić jego rozmiar i położenie.

Obecny cel wskazania (selektor w kodzie): `[data-action="graph-nav-toggle"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 26. Filtr wątków (`filters`)

Obecny tekst: Wybierz, które wątki mają być widoczne, i zatwierdź wybór. Ukrycie wątku nie usuwa danych. Pokaż wszystkie przywraca pełną planszę.

Obecny cel wskazania (selektor w kodzie): `[data-action="track-filter-toggle"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 27. Widok kompaktowy (`compact`)

Obecny tekst: Przełącz widok pełny i kompaktowy. W GRAFIE przełączasz też stosy i układ relacyjny.

Obecny cel wskazania (selektor w kodzie): `[data-action="toggle-compact"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

## Pozostałe opcje

### 28. Wygląd i ustawienia (`appearance`)

Obecny tekst: W Opcjach znajdziesz motyw jasny/ciemny, pełny ekran oraz dostępne ustawienia oznaczeń i obramowań. Przeglądarka zapamiętuje ustawienia widoku.

Obecny cel wskazania (selektor w kodzie): `.toolbar-menu [data-action="theme-toggle"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 29. Projekt testowy i reset (`qa-reset`)

Obecny tekst: W Opcjach możesz wczytać projekt testowy FENIKS lub zresetować bieżący projekt. Obie operacje zastępują dane po potwierdzeniu. Najpierw zapisz własny projekt do JSON.

Obecny cel wskazania (selektor w kodzie): `.toolbar-menu [data-action="test-project"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

### 30. Samouczek i nowe funkcje (`tutorial-controls`)

Obecny tekst: W Opcjach możesz wznowić niepoznane lekcje, odtworzyć całość, zresetować historię lub wyłączyć automatyczny samouczek.

Obecny cel wskazania (selektor w kodzie): `.toolbar-menu [data-tutorial-action="resume"]`

**Moje poprawki:**

- Kolejność / tytuł:
- Tekst:
- Co pokazać / gdzie wskazać:
- Animacja (stan początkowy, akcje, rezultat, tempo) lub brak animacji:

# Różnice w kolejności SIATKI

Obecna kolejność różni się w grupie Budowanie fabuły. W SIATCE występują kolejno:

- Wątki (`threads`)
- Rozdziały w SIATCE (`grid-chapters`)
- Tworzenie wydarzeń (`event-add`)
- Edycja i przenoszenie (`event-menu`)
- Rozdziały w GRAFIE (`graph-chapters`)
- Relacje w GRAFIE (`graph-relations`)
- Podsumowanie z szyny rozdziałów (`rail-summary`)

Lekcje drugiego typu projektu nie przełączają automatycznie otwartego projektu.

**Moje poprawki dotyczące SIATKI:**

# Dodatkowe funkcje / lekcje do dopisania

-
-
-

# Uwagi końcowe

-

Źródło: moduł 45-tutorial.js oraz style 20-responsive.css z v2.1.8. Lista odzwierciedla kod, nie ocenę jakości wizualnej. Kod aplikacji nie został zmieniony.
