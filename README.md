# Royal-bets – System Informatyczny Firmy Bukmacherskiej

## Spis treści
1. [Opis Domeny](#opis-domeny)
2. [Funkcjonalność Modelu](#funkcjonalność-modelu)
3. [Możliwości Analityczne i Raportowe](#możliwości-analityczne-i-raportowe)
4. [Struktura Encji Biznesowych](#struktura-encji-biznesowych)
5. [Uzasadnienie Relacji Biznesowych](#uzasadnienie-relacji-biznesowych)

---

## Opis Domeny
[cite_start]System informatyczny firmy **Royal-bets** stanowi główną platformę obsługi klientów w obszarze zakładów wzajemnych i gier losowych[cite: 5]. [cite_start]Baza danych i logika systemowa zostały zaprojektowane w celu sprawnego zarządzania procesami rejestracji graczy oraz utrzymywania strukturalnego katalogu dostępnych gier i zdarzeń[cite: 6]. [cite_start]System wspiera pełen cykl życia transakcji, od momentu zawarcia zakładu, przez monitorowanie terminów, aż po końcowe rozliczenie i aktualizację statusu zwrotu[cite: 8, 11].

## Funkcjonalność Modelu
[cite_start]Model biznesowy przewiduje podział uprawnień i akcji dla dwóch głównych grup użytkowników[cite: 12]:

### Dla Klienta:
* [cite_start]**Rejestracja w systemie**: założenie konta użytkownika w celu uzyskania dostępu do usług[cite: 14].
* [cite_start]**Zawieranie zakładów**: tworzenie nowych rekordów transakcji dla wybranych zdarzeń[cite: 15].
* [cite_start]**Obsługa gier losowych**: korzystanie z dostępnego katalogu gier systemowych[cite: 5].
* [cite_start]**Podgląd historii**: dostęp do osobistej historii wszystkich zawartych transakcji[cite: 17].
* [cite_start]**Monitorowanie terminów**: sprawdzanie dat rozliczenia i terminów płatności dla posiadanych zakładów[cite: 18].

### Dla Pracownika (Bukmachera/Obsługi):
* [cite_start]**Zarządzanie ofertą**: rejestracja nowych pozycji w katalogu oraz przypisywanie parametrów do gier[cite: 20].
* [cite_start]**Zarządzanie kontami**: tworzenie oraz nadzorowanie kont klientów[cite: 22].
* [cite_start]**Rozliczanie transakcji**: rejestracja i aktualizacja statusów transakcji po ich zakończeniu[cite: 23].
* [cite_start]**Wypłacanie wygranych**: autoryzacja wypłat środków oraz aktualizacja dat zwrotu[cite: 11].
* [cite_start]**Identyfikacja ryzyk**: wykrywanie przeterminowanych transakcji oraz monitorowanie aktywności[cite: 24].

## Możliwości Analityczne i Raportowe
[cite_start]System **Royal-bets** umożliwia generowanie raportów wspierających procesy biznesowe[cite: 25]:
* [cite_start]**Statystyki aktywności**: zliczanie liczby transakcji dokonanych przez poszczególnych klientów[cite: 32].
* [cite_start]**Analiza popularności**: identyfikacja najczęściej wybieranych gier i zdarzeń[cite: 32].
* [cite_start]**Monitoring oferty**: raportowanie pozycji, które nigdy nie zostały wybrane przez klientów[cite: 33].
* [cite_start]**Zarządzanie płatnościami**: identyfikacja klientów z nierozliczonymi lub przeterminowanymi transakcjami[cite: 33].

## Struktura Encji Biznesowych
[cite_start]System opiera się na kluczowych encjach odzwierciedlających strukturę działalności firmy[cite: 35]:
* [cite_start]**Klient (Reader)**: przechowuje dane identyfikacyjne, unikalny adres email oraz datę rejestracji w systemie[cite: 37, 42].
* [cite_start]**Zakład (Loan)**: rejestruje datę zawarcia transakcji, przewidywany termin rozliczenia oraz opcjonalną datę wypłaty[cite: 74, 78].
* [cite_start]**Gra/Zdarzenie (Book)**: zawiera informacje o tytule, parametrach identyfikacyjnych oraz podmiocie odpowiedzialnym za dostarczenie usługi[cite: 57, 62].

## Uzasadnienie Relacji Biznesowych
* [cite_start]**Klient – Zakład (1:N)**: każdy klient może zawrzeć wiele zakładów, jednak każda transakcja musi być przypisana do dokładnie jednego konta gracza[cite: 134, 135].
* [cite_start]**Zdarzenie – Zakład (1:N)**: dane zdarzenie lub gra może być przedmiotem wielu transakcji dokonywanych przez różnych klientów[cite: 139, 140].
* [cite_start]**Spójność danych**: każda transakcja finansowa w systemie musi posiadać powiązanie z istniejącym klientem, co gwarantuje, że proces rozliczenia nie może istnieć bez podmiotu odpowiedzialnego[cite: 138, 143].

---
**Projekt**: Royal-bets System
[cite_start]**Inspiracja strukturą dokumentacji**: Radosław Fafiński [cite: 3]
