# Drabinka Master — odłożone koncepcje rozwojowe

**Data:** 24.11.2026  
**Baza aplikacji:** v2.0.0, schemat danych 3  
**Status:** PASS / odłożone do późniejszego rozważenia (nie jest to wynik testu QA).  
**Zakres:** zapis dyskusji projektowej, bez zmian w kodzie i bez zobowiązania do wdrożenia.

## 1. Kontekst i decyzje

- Etap restrukturyzacji zakończono na v1.2.98. W v2.0.0 zrezygnowano z migracji wcześniejszych zapisów.
- Zachować obecny wygląd, samodzielny HTML offline, układ GRAFU, szybkość SIATKI, stabilność kamery, historię i ochronę bieżących danych.
- Rozważano dwie nowe funkcje: zamknięte sekwencje wydarzeń oraz poziome podziały wewnątrz rozdziałów.
- Użytkownik zdecydował najpierw odłożyć sekwencje, a następnie również poziome podziały. Obie koncepcje pozostają w backlogu, nie w planie bieżącego wydania.
- Poniższe warianty to propozycje do weryfikacji, a nie zatwierdzona specyfikacja.

## 2. Zamknięte sekwencje chronologiczne (odłożone)

### 2.1. Potrzeba użytkownika

Możliwość wskazania wydarzeń, które występują dokładnie po sobie, również pomiędzy różnymi wątkami. Pomiędzy kolejnymi momentami takiej sekwencji nie powinno być dodatkowego, odrębnego momentu należącego do tej samej ustalonej chronologii. Możliwe pozostają wydarzenia równoczesne z jej elementami.

Przykładowa sekwencja wskazana przez użytkownika: **C4 – A1 – C5 – A4**. Kolejne elementy przechodzą naprzemiennie przez wątki C i A.

### 2.2. Rozważany model logiczny

- `before`: zwykłe następstwo, dopuszczające dodatkowe momenty między wydarzeniami.
- `equal`: równoczesność, wspólny moment chronologiczny.
- `next` (nazwa robocza): bezpośrednie następstwo, bez dodatkowego momentu w zamkniętym przedziale.
- `next` powinno działać między momentami/grupami równoczesności, a nie wyłącznie między pojedynczymi kafelkami.
- Łańcuchy mogą przechodzić między wątkami; przejścia między rozdziałami również rozważano, ale nie ustalono sposobu pogodzenia ich z nagłówkami i przestrzeniami międzyrozdziałowymi.
- Sama geometria nie tworzy relacji. Przynależność do sekwencji powinna wynikać ze świadomej decyzji użytkownika, nie z położenia kafelka.
- Rozważano rozszerzenie istniejącego menu relacji o bezpośrednie następstwo, z jednoznacznym kierunkiem od źródła do celu.

### 2.3. Preferowana geometria (kierunek użytkownika)

Użytkownik nie był przekonany do podwójnych strzałek. Zamiast nich zaproponował wyrażanie bezpośredniego następstwa samą geometrią kafelków:

| Relacja | Proponowana geometria |
|---|---|
| Zwykłe następstwo | Dotychczasowy minimalny odstęp 18 px |
| Bezpośrednie następstwo | 0 px odstępu pionowego; dolna krawędź poprzedniego momentu na wysokości górnej krawędzi następnego |
| Równoczesność | Rozważane wspólne górne i dolne krawędzie oraz wysokość równa najwyższemu kafelkowi danego momentu |
| Niezależne wydarzenia | Brak wymuszonej synchronizacji; przypadkowe wyrównanie nie tworzy relacji |

Przykład (kolejne pasma pionowe; każda granica wewnętrzna sekwencji ma odstęp 0 px):

| Moment | Wątek A | Wątek C |
|---|---|---|
| 1 | — | C4 |
| 2 | A1 | — |
| 3 | — | C5 |
| 4 | A4 | — |

Przy różnej ilości tekstu krótsze kafelki równoczesne mogłyby być rozciągane do wysokości najwyższego, bez centrowania tekstu w pionie. Kolejne momenty nie muszą mieć jednakowej wysokości. Rozważano też alternatywę wyrównania wysokości całej sekwencji, ale nie przyjęto jej jako wymagania. Zmiana długości tekstu powinna przeliczać układ z zachowaniem połączenia krawędzi i stabilności kamery.

### 2.4. Problem A2 i A3 — nierozstrzygnięty

W sekwencji C4 – A1 – C5 – A4 kafelki A2 i A3 nie zostały ręcznie dodane. Nie wolno ich automatycznie uznać za członków sekwencji ani nadawać im relacji `equal` tylko z powodu wyrównania położenia.

Rozważano:

- pozostawienie A2 i A3 jako niepowiązanych wydarzeń, wizualnie między A1 i A4, jeśli semantyka lokalnej sekwencji na to pozwoli;
- wypchnięcie ich przed lub po sekwencji, o ile istniejące relacje na to pozwalają;
- zgłoszenie konfliktu, jeśli wcześniej obowiązuje kolejność A1 – A2 – A3 – A4, a nowe ograniczenie nie pozwala jej zachować.

Nie uzgodniono, który wariant ma być domyślny. Nie należy po cichu zmieniać ręcznie ustalonej chronologii ani ukrywać wydarzeń. Trzeba również rozróżnić kolejność w obrębie wątku od samych identyfikatorów A1/A2 itd.

### 2.5. Kilka niezależnych sekwencji

Przykład:

- S1: A1 – B1 – A2 – B2 (ewentualnie A3).
- S2: C1 – D1 – C2.

Dopóki nie ma między nimi relacji, powinny zachować niezależność. Mogą znajdować się obok siebie i pokrywać pionowo; nie oznacza to równoczesności. Nie powinny blokować się wzajemnie tylko z powodu zamkniętego charakteru.

Pierwotna koncepcja globalnego zakazu wstawiania czegokolwiek między elementy `next` okazała się niewystarczająca. Potrzebne jest rozstrzygnięcie zakresu, w jakim sekwencja narzuca chronologię innym wydarzeniom.

### 2.6. Synchronizacja i tożsamość sekwencji

Rozważano ustawienie `B1 = C1` pomiędzy S1 i S2. W modelu wspólnych momentów i bezpośredniego następstwa może to wymuszać wyrównanie kolejnych momentów (A2 z D1, B2 z C2), ale tylko jeśli tak zostanie zdefiniowana semantyka. Nie należy traktować tego automatycznego wyrównania jako zatwierdzonego wymagania.

Użytkownik wskazał, że po powiązaniu dwóch dłuższych sekwencji nie wiadomo już wizualnie, gdzie kończy się jedna, a zaczyna druga. Powiązanie chronologiczne nie powinno automatycznie scalać ich członkostwa.

Rozważane rozwiązania:

- jawna tożsamość sekwencji (identyfikator i uporządkowana lista członków) zamiast wyłącznie łańcucha relacji;
- subtelny boczny pasek wspólny dla członków;
- identyfikator i pozycja w sekwencji, np. S1 · 2/5;
- oznaczenie początku i końca;
- podświetlenie całej sekwencji po najechaniu, ewentualnie pomocnicze prowadnice widoczne tylko podczas interakcji.

Nie wybrano żadnego rozwiązania. Preferencja użytkownika: nie dodawać strzałek i nie zaśmiecać grafu. Wcześniejsza sugestia asystenta dotycząca strzałek pozostaje odrzuconym kierunkiem wizualnym, nie wymaganiem.

### 2.7. Konflikty i przyszłe testy

Przy próbie wstawienia niedozwolonego momentu lub sprzecznym połączeniu rozważano komunikat z opcjami: anuluj, ustaw równocześnie z jednym z sąsiednich momentów albo świadomie zmień `next` na `before`. Nie rozrywać sekwencji automatycznie. Potencjalne operacje: dodawanie na obu końcach, usuwanie połączenia, świadome scalanie sekwencji, cofanie i ponawianie.

Przed wdrożeniem należy ustalić semantykę konfliktów, grup równoczesności, niezależnych sekwencji, zwykłych relacji między nimi, kolejności w wątku, rozdziałów, zachowania SIATKI oraz solvera. Testy powinny obejmować m.in. cykle, wieloelementowe łańcuchy, relacje między wątkami, usuwanie członków, zmianę wysokości tekstu, zapis/odczyt, import/eksport, Ctrl+Z/Y i kamerę. To zakres do przyszłego projektowania, nie wykonane testy.

## 3. Poziome podziały wewnątrz rozdziałów (odłożone)

### 3.1. Potrzeba użytkownika

Wprowadzić poziome podziały w obrębie rozdziału GRAFU, uzyskując częściowo funkcjonalność SIATKI bez konieczności tworzenia dodatkowych rozdziałów. Wątki nadal stanowią kolumny, a poszczególne poziome obszary zawierają kafelki różnych wątków.

### 3.2. Rozważany wygląd i obsługa

- Delikatne poziome separatory w obrębie rozdziału, bez rozbudowanych dodatkowych paneli.
- Opcjonalne nazwy pasów/sekcji, np. Przygotowanie, Akcja równoległa, Konsekwencje; nazwy nie były wymaganiem użytkownika.
- Jeden rozdział bez dodatkowych podziałów zachowuje dotychczasowy układ.
- Rozważano przycisk `+` do dodawania podziału, możliwość dodawania nad/pod, usuwania pustych pasów, scalania i zmiany nazw.
- Kafelki mogłyby być przenoszone między pasami, wątkami i rozdziałami.
- Wysokość pasa powinna dostosowywać się do jego zawartości; dokładna geometria i odstępy pozostają do uzgodnienia.
- W obrębie pasa GRAF nadal korzystałby z elastycznego rozmieszczania, zamiast zamieniać się w sztywną tabelę.

### 3.3. Otwarte decyzje logiczne

Pierwotna sugestia asystenta: pasy wyłącznie porządkowe, nie tworzą automatycznej relacji `before`. Alternatywa: podziały stają się ograniczeniem chronologicznym (kolejne pasy określają następstwo) lub solver traktuje je jako preferencję, a nie twardą regułę.

To istotna nierozstrzygnięta kwestia: twarde ograniczenie geometryczne może być sprzeczne z istniejącą relacją `before` lub `equal` między pasami. Należy ustalić, co się dzieje przy przeciąganiu, dodawaniu podziału, relacji przez granicę pasa, usuwaniu/scalaniu i zmianie podziału rozdziału. Nie należy zakładać, że pasy są wyłącznie wizualne, bez rozstrzygnięcia tych przypadków.

Do wyboru pozostaje również sposób reprezentowania pasów w SIATCE, w podsumowaniu, na minimapie, w PDF, imporcie/eksporcie i historii. Rozważano wstępnie wdrożenie w GRAFIE, ale nie ustalono docelowego zakresu.

### 3.4. Makieta

Powstała poglądowa makieta ciemnego interfejsu: rozdział 02 — PIERWSZE SYGNAŁY, pięć kolumn wątków A–E, trzy poziome pasy (Przygotowanie, Akcja równoległa, Konsekwencje) i liczne kafelki różnej wysokości.

![Makieta poziomych pasów](drabinka_master_trzy_poziome_pasy_rozdziału.png)

Makieta nie jest projektem wykonawczym ani wiernym zrzutem aktualnej aplikacji. Zawiera przykładowe elementy nawigacji i etykiety, których użytkownik nie zatwierdził. Nie należy ich automatycznie wdrażać.

Po obejrzeniu makiety użytkownik zdecydował: na razie PASS, zapisać przemyślenia na później. Nie oceniono jeszcze, jak funkcja sprawdziłaby się w rzeczywistej pracy.

## 4. Warunki ewentualnego wznowienia prac

1. Najpierw wrócić do problemu użytkowego, a nie do automatycznego wdrażania obu koncepcji.
2. Dla wybranej funkcji uzgodnić otwarte reguły i przygotować czytelną makietę z większą liczbą kafelków oraz rzeczywistymi przypadkami konfliktów.
3. Dopiero potem przygotować specyfikację modelu danych, solvera i interfejsu, kryteria akceptacji oraz testy.
4. Zachować bieżącą bazę i SemVer: nowe kompatybilne funkcje mogą uzasadnić v2.1.0; zmiana łamiąca kompatybilność wymaga ponownej oceny numeru wydania. Nie przywracać historycznych migracji bez odrębnej decyzji.
5. Zachować zwykłe operacje, istniejącą chronologię, widoki, responsywność, wydajność i ochronę danych. Nie rozszerzać zakresu o kolejną restrukturyzację bez konkretnej potrzeby.

**Stan końcowy notatki:** obie koncepcje odłożone; brak implementacji, brak zmiany numeru aplikacji, brak nowych wyników testów.
