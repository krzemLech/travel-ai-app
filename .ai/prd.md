# Dokument wymagań produktu (PRD) - VibeTravels

## 1. Przegląd produktu

VibeTravels to aplikacja webowa umożliwiająca użytkownikom zamianę uproszczonych notatek o miejscach i celach podróży na konkretne plany wycieczek przy wykorzystaniu sztucznej inteligencji. Aplikacja skierowana jest głównie do młodych użytkowników indywidualnych lub grup koleżeńskich planujących wycieczki krajowe i międzynarodowe.

Aplikacja będzie działać na zasadzie połączenia systemu zarządzania profilami użytkowników, ich preferencjami turystycznymi oraz systemu generacji planów wycieczek opartego o duże modele językowe AI (Anthropic lub OpenAI).

VibeTravels w wersji MVP będzie aplikacją darmową, pisaną w JavaScript, z przygotowaną nieaktywną stroną przedstawiającą przyszłe modele subskrypcji.

## 2. Problem użytkownika

Planowanie angażujących i interesujących wycieczek jest trudne i czasochłonne. Użytkownicy często spędzają wiele godzin na:

- Wyszukiwaniu wartościowych atrakcji i aktywności w danym miejscu
- Planowaniu realistycznego harmonogramu uwzględniającego odległości i czas
- Dopasowaniu planu do indywidualnych preferencji i ograniczeń
- Organizacji szczegółów logistycznych (transport, posiłki)
- Oszacowaniu kosztów

VibeTravels rozwiązuje te problemy poprzez wykorzystanie potencjału AI do automatyzacji procesu planowania, uwzględniając indywidualne preferencje użytkowników, budżet, harmonogram oraz potrzeby logistyczne.

## 3. Wymagania funkcjonalne

### 3.1. System kont użytkowników

- Rejestracja i logowanie przez email lub autoryzacja przez Supabase
- Dwustopniowy formularz rejestracyjny:
  - Dane osobowe (imię, nazwisko, email, telefon, płeć, wiek, lokalizacja/adres)
  - Podstawowe preferencje wyjazdowe (preferowane cele podróży, preferowane aktywności)
- Profil użytkownika umożliwiający przeglądanie i edycję podstawowych preferencji turystycznych

### 3.2. Zarządzanie notatkami o wycieczkach

- Tworzenie nowych notatek o planowanych wycieczkach
- Przeglądanie istniejących notatek
- Edycja notatek
- Usuwanie notatek
- Wprowadzanie podstawowych danych:
  - Daty wyjazdu
  - Budżet
  - Liczba osób
  - Lokalizacja (opcjonalnie)
- Wprowadzanie szczegółowych preferencji dla konkretnej wycieczki:
  - Preferowane aktywności
  - Zainteresowania
  - Preferowany klimat
  - Preferencje żywieniowe
  - Ograniczenia zdrowotne
  - Posiadanie prawa jazdy
  - Inne specyficzne preferencje związane z konkretną wycieczką
- Dwa podejścia do wprowadzania danych:
  - Formularz z konkretnymi polami
  - Jedno duże pole tekstowe interpretowane przez AI

### 3.3. Generowanie planów wycieczek przez AI

- Integracja z dużym modelem językowym (Anthropic lub OpenAI)
- Generowanie planów wycieczek z podziałem na dni
- Uwzględnienie w planie:
  - Sugerowanych aktywności
  - Miejsc na posiłki
  - Sposobów transportu
  - Orientacyjnych kosztów dla poszczególnych elementów
- Walidacja planu pod kątem:
  - Odpowiedniej intensywności
  - Zgodności z preferencjami użytkownika
  - Sugestie 2-3 atrakcji poza strefą komfortu użytkownika

### 3.4. Zarządzanie planami wycieczek

- Możliwość edycji wygenerowanego planu
- Możliwość ponownego generowania planu
- Eksport planu do formatu PDF
- System ocen gwiazdkowych dla wygenerowanych planów

## 4. Granice produktu

### 4.1. Co wchodzi w zakres MVP

- System kont użytkowników z podstawową autoryzacją
- Profil użytkownika z podstawowymi preferencjami turystycznymi
- Zapisywanie, odczytywanie, przeglądanie i usuwanie notatek o wycieczkach
- Wprowadzanie szczegółowych preferencji dla konkretnej wycieczki
- Generowanie planów wycieczek przez AI z uwzględnieniem preferencji
- Edycja i eksport planów w formacie PDF
- System ocen dla wygenerowanych planów
- Wycieczki krajowe i międzynarodowe
- Plany na maksymalnie 7 dni
- Uwzględnienie zmian czasu w różnych strefach czasowych

### 4.2. Co NIE wchodzi w zakres MVP

- Współdzielenie planów wycieczkowych między kontami
- Bogata obsługa i analiza multimediów (np. zdjęć miejsc do odwiedzenia)
- Zaawansowane planowanie czasu i logistyki
- Szczegółowe przeliczanie walut
- Dodawanie własnych zdjęć i notatek do planu
- Zapisywanie poprzednich wersji planu (historia modyfikacji)
- Wersje premium i płatne subskrypcje (będą tylko przygotowane wizualnie)
- Integracje z systemami rezerwacji

## 5. Historyjki użytkowników

### US-001: Rejestracja nowego użytkownika

- Jako nowy użytkownik, chcę założyć konto w aplikacji, aby korzystać z jej funkcjonalności.
- Kryteria akceptacji:
  - Użytkownik może zarejestrować się podając email i hasło
  - Użytkownik może alternatywnie skorzystać z autoryzacji przez Supabase
  - Po rejestracji użytkownik jest przekierowany do pierwszego kroku formularza profilowego
  - System weryfikuje unikalność adresu email

### US-002: Uzupełnienie danych osobowych

- Jako nowy użytkownik, chcę wprowadzić moje dane osobowe, aby dokończyć proces rejestracji.
- Kryteria akceptacji:
  - Użytkownik może wprowadzić: imię, nazwisko, email, telefon, płeć, wiek, lokalizację/adres
  - System waliduje poprawność wprowadzonych danych
  - Użytkownik może przejść do następnego kroku po uzupełnieniu wymaganych pól
  - Dane są zapisywane w profilu użytkownika

### US-003: Uzupełnienie podstawowych preferencji wyjazdowych

- Jako nowy użytkownik, chcę określić moje podstawowe preferencje wyjazdowe, aby otrzymywać ogólne rekomendacje.
- Kryteria akceptacji:
  - Użytkownik może określić preferowane cele podróży i preferowane aktywności
  - System zapisuje podstawowe preferencje w profilu użytkownika
  - Użytkownik jest przekierowany do głównej strony aplikacji po zakończeniu procesu

### US-004: Logowanie do aplikacji

- Jako zarejestrowany użytkownik, chcę zalogować się do aplikacji, aby uzyskać dostęp do moich danych i planów.
- Kryteria akceptacji:
  - Użytkownik może zalogować się podając email i hasło
  - Użytkownik może skorzystać z autoryzacji przez Supabase
  - System weryfikuje poprawność danych logowania
  - Po udanym logowaniu użytkownik jest przekierowany do głównej strony aplikacji
  - W przypadku błędnych danych system wyświetla odpowiedni komunikat

### US-005: Edycja profilu użytkownika

- Jako zalogowany użytkownik, chcę edytować mój profil, aby zaktualizować moje dane i podstawowe preferencje.
- Kryteria akceptacji:
  - Użytkownik może modyfikować wszystkie swoje dane osobowe
  - Użytkownik może aktualizować podstawowe preferencje wyjazdowe
  - System zapisuje zmiany po zatwierdzeniu przez użytkownika
  - System wyświetla potwierdzenie zapisania zmian

### US-006: Tworzenie nowej notatki o wycieczce

- Jako zalogowany użytkownik, chcę utworzyć nową notatkę o planowanej wycieczce, aby rozpocząć proces planowania.
- Kryteria akceptacji:
  - Użytkownik może wprowadzić podstawowe dane: daty wyjazdu, budżet, liczba osób
  - Użytkownik może opcjonalnie podać lokalizację wycieczki
  - System zapisuje notatkę i wyświetla opcje wprowadzenia szczegółowych preferencji
  - System wyświetla notatkę na liście notatek użytkownika

### US-007: Wprowadzanie szczegółowych preferencji wycieczki przez formularz

- Jako zalogowany użytkownik, chcę wprowadzić szczegółowe preferencje dotyczące konkretnej wycieczki poprzez formularz, aby precyzyjnie określić moje oczekiwania.
- Kryteria akceptacji:
  - Formularz zawiera pola dla wszystkich istotnych preferencji (aktywności, zainteresowania, klimat, preferencje żywieniowe, ograniczenia zdrowotne, itp.)
  - System waliduje poprawność wprowadzonych danych
  - Użytkownik może zapisać częściowo wypełniony formularz
  - System zapisuje szczegółowe preferencje dla danej wycieczki

### US-008: Wprowadzanie preferencji wycieczki przez pole tekstowe

- Jako zalogowany użytkownik, chcę wprowadzić moje preferencje dotyczące wycieczki w formie swobodnego tekstu, aby szybko opisać moje oczekiwania.
- Kryteria akceptacji:
  - System udostępnia duże pole tekstowe do wprowadzenia opisu
  - AI analizuje i interpretuje wprowadzony tekst
  - System ekstrahuje kluczowe informacje z tekstu (aktywności, zainteresowania, preferencje żywieniowe, ograniczenia zdrowotne, itp.)
  - Użytkownik otrzymuje podsumowanie zinterpretowanych preferencji do weryfikacji

### US-009: Przeglądanie notatek o wycieczkach

- Jako zalogowany użytkownik, chcę przeglądać moje zapisane notatki o wycieczkach, aby zarządzać moimi planami.
- Kryteria akceptacji:
  - System wyświetla listę wszystkich notatek użytkownika
  - Lista zawiera podstawowe informacje o każdej wycieczce (daty, lokalizacja, status)
  - Użytkownik może sortować i filtrować listę
  - Użytkownik może wybrać notatkę do podglądu szczegółów

### US-010: Edycja notatki o wycieczce

- Jako zalogowany użytkownik, chcę edytować istniejącą notatkę o wycieczce, aby zaktualizować moje plany.
- Kryteria akceptacji:
  - Użytkownik może modyfikować wszystkie dane notatki
  - Użytkownik może modyfikować szczegółowe preferencje dla wycieczki
  - System zapisuje zmiany po zatwierdzeniu przez użytkownika
  - System wyświetla potwierdzenie zapisania zmian

### US-011: Usuwanie notatki o wycieczce

- Jako zalogowany użytkownik, chcę usunąć notatkę o wycieczce, aby pozbyć się nieaktualnych planów.
- Kryteria akceptacji:
  - Użytkownik może wybrać notatkę do usunięcia
  - System wymaga potwierdzenia przed usunięciem
  - Po usunięciu notatka znika z listy
  - System wyświetla potwierdzenie usunięcia

### US-012: Generowanie planu wycieczki przez AI

- Jako zalogowany użytkownik, chcę wygenerować szczegółowy plan wycieczki na podstawie mojej notatki i preferencji, aby otrzymać spersonalizowany harmonogram.
- Kryteria akceptacji:
  - Użytkownik może zainicjować proces generowania planu dla wybranej notatki
  - System komunikuje się z modelem AI, przekazując wszystkie istotne dane i preferencje
  - System wyświetla komunikat o postępie generowania
  - Po zakończeniu generowania system wyświetla wygenerowany plan

### US-013: Przeglądanie wygenerowanego planu wycieczki

- Jako zalogowany użytkownik, chcę przeglądać szczegóły wygenerowanego planu wycieczki, aby zapoznać się z propozycjami.
- Kryteria akceptacji:
  - Plan jest prezentowany z podziałem na dni
  - Dla każdego dnia wyświetlane są: aktywności, miejsca na posiłki, transport, orientacyjne koszty
  - Interfejs umożliwia łatwe nawigowanie między dniami
  - Użytkownik może zobaczyć podsumowanie całego planu

### US-014: Edycja wygenerowanego planu wycieczki

- Jako zalogowany użytkownik, chcę edytować wygenerowany plan, aby dostosować go do moich potrzeb.
- Kryteria akceptacji:
  - Użytkownik może modyfikować poszczególne elementy planu
  - Użytkownik może dodawać, usuwać lub przenosić aktywności
  - System zapisuje zmiany wprowadzone przez użytkownika
  - System wyświetla potwierdzenie zapisania zmian

### US-015: Ponowne generowanie planu wycieczki

- Jako zalogowany użytkownik, chcę ponownie wygenerować plan wycieczki, aby otrzymać alternatywne propozycje.
- Kryteria akceptacji:
  - Użytkownik może zainicjować ponowne generowanie planu
  - System umożliwia wprowadzenie dodatkowych wskazówek przed ponownym generowaniem
  - System wyświetla komunikat o postępie generowania
  - Po zakończeniu generowania system wyświetla nowy plan

### US-016: Ocenianie wygenerowanego planu

- Jako zalogowany użytkownik, chcę ocenić wygenerowany plan, aby przekazać feedback.
- Kryteria akceptacji:
  - Użytkownik może przyznać ocenę w skali gwiazdkowej (np. 1-5)
  - Użytkownik może opcjonalnie dodać komentarz do oceny
  - System zapisuje ocenę i powiązuje ją z planem
  - System potwierdza zapisanie oceny

### US-017: Eksport planu do PDF

- Jako zalogowany użytkownik, chcę wyeksportować plan wycieczki do formatu PDF, aby mieć do niego dostęp offline.
- Kryteria akceptacji:
  - Użytkownik może zainicjować eksport planu do PDF
  - System generuje plik PDF zawierający wszystkie elementy planu
  - PDF zawiera podział na dni, aktywności, miejsca na posiłki, transport i koszty
  - Użytkownik może pobrać wygenerowany plik PDF

### US-018: Wylogowanie z aplikacji

- Jako zalogowany użytkownik, chcę wylogować się z aplikacji, aby zabezpieczyć moje dane.
- Kryteria akceptacji:
  - Użytkownik może wylogować się z dowolnego miejsca w aplikacji
  - Po wylogowaniu użytkownik jest przekierowany do strony logowania
  - Sesja użytkownika jest poprawnie zamykana
  - Dostęp do danych użytkownika jest blokowany po wylogowaniu

### US-019: Przeglądanie informacji o subskrypcjach

- Jako użytkownik, chcę zobaczyć dostępne plany subskrypcji, aby poznać potencjalne korzyści z wersji premium.
- Kryteria akceptacji:
  - System wyświetla stronę z różnymi modelami subskrypcji
  - Każdy plan zawiera informacje o funkcjach i ograniczeniach
  - Strona zawiera informację o niedostępności płatnych planów w wersji MVP
  - Interfejs jest przejrzysty i atrakcyjny wizualnie

### US-020: Zarządzanie bezpieczeństwem konta

- Jako użytkownik, chcę zarządzać bezpieczeństwem mojego konta, aby chronić moje dane.
- Kryteria akceptacji:
  - Użytkownik może zmienić hasło
  - System wymaga podania obecnego hasła przed zmianą
  - System waliduje siłę nowego hasła
  - System potwierdza zmianę hasła

## 6. Metryki sukcesu

### 6.1. Metryki zaangażowania użytkowników

- 90% użytkowników posiada wypełnione podstawowe preferencje turystyczne w swoim profilu
- 75% użytkowników generuje 3 lub więcej planów wycieczek na rok
- Średni czas spędzony w aplikacji przez użytkownika wynosi minimum 10 minut na sesję
- Współczynnik powrotu użytkowników (retention rate) na poziomie minimum 40% po miesiącu

### 6.2. Metryki jakości produktu

- Średnia ocena wygenerowanych planów na poziomie minimum 4/5 gwiazdek
- Mniej niż 20% użytkowników korzysta z opcji ponownego generowania planu
- Minimum 70% wygenerowanych planów jest eksportowanych do PDF
- Mniej niż 5% użytkowników zgłasza problemy techniczne

### 6.3. Metryki biznesowe

- Wzrost liczby użytkowników o minimum 15% rocznie
- Minimum 30% użytkowników odwiedza stronę z modelami subskrypcji
- Koszt pozyskania użytkownika (CAC) nie przekracza zakładanej wartości
- Średni czas rozwoju MVP nie przekracza jednego miesiąca
