# Notatki dla uczestników

## Pojęcia
* Unit test - test uruchamiający jedną ścieżkę w kodzie i weryfikujący jej wynik
* Test double (atrapa) - zamiennik prawdziwego komponentu (np. obiektu), używany do testowania
* Stub - prosty test double, który zwraca gotową odpowiedź
* Mock - test double, który weryfikuje zachowanie, np. wywoływane na nim metody (behavior verification)
* Fake - implementacja uproszczona, np. baza danych w pamięci, wirtualny filesystem, message bus na lokalnym EventEmitterze

## Charakterystyka testów jednostkowych
* Jedna interakcja i wynik będące przedmiotem testu
* Szybkie wykonanie
* Niezależność od środowiska (determinizm)
* Separacja od innych testów
* Wgląd w kod

## Dlaczego piszemy testy jednostkowe
* Ustanowienie i utrzymanie kontraktu w kodzie
* Pomoc przy refactoringu
* Przykłady wykorzystania
* Praktykowanie Continuous Integration
* Sterowanie implementacją - Test-Driven Development

## Techniki testowania jednostkowego
* Classical vs mockist testing:
    * Classical - używanie test doubles tylko, gdy prawdziwa implementacja byłaby problematyczna
        * Zaleta: nie tworzymy bytów nad potrzeby
        * Wada: mniejsza precyzja testów - problemy z zależnością potrafią zepsuć test jednostki
    * Mockist - zastępowanie wszystkiego, czego się da, atrapami
        * Zaleta: lepsza izolacja testów
        * Wada: konieczność implementacji wielu zastępczych funkcjonalności
* State verification vs behavior verification:
    * State verification - sprawdzanie stanu po wywołaniach
        * Zaleta: prostsze, mniej związane z implementacją testowanego komponentu
        * Wada: może wymagać dodania syntetycznych getterów; 
    * Behavior verification - sprawdzanie wywołań w momencie ich robienia
        * Zaleta: sprawdzanie integracji z innymi komponentami w toku testu
        * Wada: trudniejszy refactoring całych hierarchii komponentów

## Artykuły
* Rodzaje obiektów testowych (test doubles): [Martin Fowler - Mocks Aren't Stubs](https://martinfowler.com/articles/mocksArentStubs.html)
* Testy integracyjne i historia vs. współczesność: [Martin Fowler - Integration Test](https://martinfowler.com/bliki/IntegrationTest.html)
* Wyznaczanie jednostki w unit testingu: [Rui Figueiredo - What exactly is a "unit" in unit testing?](https://www.blinkingcaret.com/2016/04/27/what-exactly-is-a-unit-in-unit-testing/)

## Kod źródłowy
* https://github.com/rkaw92/warsawjs-workshop-50-unit-testing/

## Biblioteki
* Node.js assert - weryfikacja stanu
* sinon.js - spy/stub/mock
    * https://github.com/sinonjs/sinon/issues/2272
