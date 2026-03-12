# Royal-bets – System Informatyczny Firmy Bukmacherskiej

## Spis treści
1. [Opis Domeny](#opis-domeny)
2. [Funkcjonalność Modelu](#funkcjonalność-modelu)
3. [Możliwości Analityczne i Raportowe](#możliwości-analityczne-i-raportowe)
4. [Struktura Encji Biznesowych](#struktura-encji-biznesowych)
5. [Uzasadnienie Relacji Biznesowych](#uzasadnienie-relacji-biznesowych)

---

## Opis Domeny
System informatyczny firmy **Royal-bets** stanowi główną platformę obsługi klientów w obszarze zakładów wzajemnych i gier losowych.
Baza danych i logika systemowa zostały zaprojektowane w celu sprawnego zarządzania procesami rejestracji graczy oraz utrzymywania strukturalnego katalogu dostępnych gier i zdarzeń.
System wspiera pełen cykl życia transakcji, od momentu zawarcia zakładu, przez monitorowanie terminów, aż po końcowe rozliczenie i aktualizację statusu zwrotu.

## Funkcjonalność Modelu
Model biznesowy przewiduje podział uprawnień i akcji dla dwóch głównych grup użytkowników:

### Dla Klienta:
**Rejestracja w systemie**: założenie konta użytkownika w celu uzyskania dostępu do usług.
**Zawieranie zakładów**: tworzenie nowych rekordów transakcji dla wybranych zdarzeń.
**Obsługa gier losowych**: korzystanie z dostępnego katalogu gier systemowych.
**Podgląd historii**: dostęp do osobistej historii wszystkich zawartych transakcji.
**Monitorowanie terminów**: sprawdzanie dat rozliczenia i terminów płatności dla posiadanych zakładów.

### Dla Pracownika (Bukmachera/Obsługi):
**Zarządzanie ofertą**: rejestracja nowych pozycji w katalogu oraz przypisywanie parametrów do gier.
**Zarządzanie kontami**: tworzenie oraz nadzorowanie kont klientów.
**Rozliczanie transakcji**: rejestracja i aktualizacja statusów transakcji po ich zakończeniu.
**Wypłacanie wygranych**: autoryzacja wypłat środków oraz aktualizacja dat zwrotu.
**Identyfikacja ryzyk**: wykrywanie przeterminowanych transakcji oraz monitorowanie aktywności.

## Możliwości Analityczne i Raportowe
System **Royal-bets** umożliwia generowanie raportów wspierających procesy biznesowe:
**Statystyki aktywności**: zliczanie liczby transakcji dokonanych przez poszczególnych klientów.
**Analiza popularności**: identyfikacja najczęściej wybieranych gier i zdarzeń.
**Monitoring oferty**: raportowanie pozycji, które nigdy nie zostały wybrane przez klientów.
**Zarządzanie płatnościami**: identyfikacja klientów z nierozliczonymi lub przeterminowanymi transakcjami.

## Struktura Encji Biznesowych
System opiera się na kluczowych encjach odzwierciedlających strukturę działalności firmy:
**Klient (Reader)**: przechowuje dane identyfikacyjne, unikalny adres email oraz datę rejestracji w systemie.
**Zakład (Loan)**: rejestruje datę zawarcia transakcji, przewidywany termin rozliczenia oraz opcjonalną datę wypłaty.
**Gra/Zdarzenie (Book)**: zawiera informacje o tytule, parametrach identyfikacyjnych oraz podmiocie odpowiedzialnym za dostarczenie usługi.

## Uzasadnienie Relacji Biznesowych
**Klient – Zakład (1:N)**: każdy klient może zawrzeć wiele zakładów, jednak każda transakcja musi być przypisana do dokładnie jednego konta gracza.
**Zdarzenie – Zakład (1:N)**: dane zdarzenie lub gra może być przedmiotem wielu transakcji dokonywanych przez różnych klientów.
**Spójność danych**: każda transakcja finansowa w systemie musi posiadać powiązanie z istniejącym klientem, co gwarantuje, że proces rozliczenia nie może istnieć bez podmiotu odpowiedzialnego.

---
**Projekt**: Royal-bets System
Autor dokumentacji: Mateusz Hincmanowski, Patryk Błażejewski
Projekt: Royal-bets System
