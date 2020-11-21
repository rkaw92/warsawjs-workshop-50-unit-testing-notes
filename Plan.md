# Wprowadzenie
* Cel testów
* Przedstawmy się
* Nagrywanie - tak/nie, uruchomienie tego ustrojstwa

# Rozgrzewka
* (Scenariusz: system marketingowy - przyjmuje dane klientów i odsiewa nieobsługiwane pola)
* (Checkout: `before-warmup`)
* Szybki test jednej funkcji: `filterProperties`
* Szybki test drugiej funkcji: `diffKeys`
* Test obu funkcji razem w połączeniu: `mapFields`
    * Czy to był test jednostkowy, czy integracyjny? (o tym w następnym punkcie)
    * (Checkout: `in-warmup-have-tests`)
* Naprawa buga
    * Regression test dla `filterProperties`
    * (Checkout: `in-warmup-bug-confirmed`)
    * Fix
* (Opcjonalny checkout: `after-warmup-bug-fixed`)

# Co to są testy jednostkowe
* Problem z wyznaczeniem jednostki
* Definicja jednostki: jedna ścieżka w kodzie, weryfikacja jednego wyniku
* (Checkout: `before-unit`)
* (Scenariusz: komponent aukcji - przyjmuje oferty i wyłania zwycięzców)
* Pokazanie cech testów jednostkowych na przykładzie
    * Zazwyczaj to white-box testing, z dostępnym kodem źródłowym (odniesienie do rozgrzewki i odkrytego buga)
    * Jedna interakcja lub jej wynik podlegająca weryfikacji, nawet jeśli przy okazji skorzystamy z zależności; odseparowany od innych testów - rozbijamy test na jednostki
    * (Checkout: `in-unit-done-1-split`)
    * Szybkie wykonanie, niezależny od środowiska - podmieniamy Notifier na mock dzięki sinon.js
    * Dyskusja: mock, behavior verification
* (Guideline testowy: 3 testy)
    1. Odrzucanie od razu takiej samej lub niższej kwoty
    2. Wyrzucanie ostatniej oferty, kiedy pojawi się lepsza
    3. Uwzględnianie zamiany j.w. przy ogłaszaniu wyników
        * Problem z biblioteką sinon.js
        * Własna implementacja mocka - jeśli czas pozwoli
* (Checkout: after-unit)
* Omówienie: co można by zrobić lepiej; co testy nam powiedziały o możliwych ulepszeniach w kodzie
    * API async → sync: usunięcie logiki powiadamiania z Auction, staging
    * Wpisanie generowania powiadomień w większą logikę Unit of Work (persystencja)

# Strategie testowania - czego do tej pory użyliśmy
* State testing vs behavior testing
* Classical vs mockist

# Checkpoint: czy omówiliśmy już te terminy?
* Test double
* Stub
* Mock
* Fake

# Do czego służą testy jednostkowe
* Wsparcie przy dochowywaniu kontraktu
* Pomoc przy refactoringu
* Praktykowanie Continuous Integration
* Sterowanie implementacją - Test-Driven Development

# Test-Driven Development: praktyka
* (Checkout: `before-tdd-practice`)
* (Scenariusz: koszyk zakupowy - obsługuje dodawanie produktów i kody rabatowe)
* Omówienie cyklu: red/green/refactor
* 3 reguły:
    * Piszemy kod produkcyjny tylko po to, żeby test przechodził
    * Piszemy tylko tyle testu, ile jest konieczne do jego niepowodzenia
    * Piszemy tylko tyle kodu produkcyjnego, ile jest konieczne do naprawienia aktualnego testu
* Przekładanie specyfikacji na testy
    * Specyfikacja w osobnym dokumencie
    * Test: tworzenie zamówienia
    * Test: dodawanie produktu
    * Test: obliczanie kwoty (brutto)
    * Test: Stosowanie kuponu zniżkowego
    * Test: Zmniejszenie kwoty na podstawie użytego kuponu
    * Test: Nadpisanie poprzedniego kuponu następnym
* Dyskusja: jak wyszedł kod, jakie napotkaliśmy wyzwania
    * Przewidywanie: narzekanie na nierówny design effort wymagany do każdego testu
* (Checkout: `after-tdd-practice`)

# Bonus (jeśli wystarczy czasu)
* Wzmianka o property-based testing

# Podsumowanie
* Prośba do uczestników, żeby podsumowali, jak rozumieją pojęcia:
    * State-based verification
    * Behavior verification
    * Mock, stub, fake
* Luźna dyskusja o testowaniu (jeśli zostało dużo czasu)
* Feedback
* Info o notatkach dla uczestników i podziękowania
