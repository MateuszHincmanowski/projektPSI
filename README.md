# Royal-bets – System Informatyczny Firmy Bukmacherskiej

## Spis treści
1. [Opis domeny](#opis-domeny)
2. [Funkcjonalność modelu](#funkcjonalność-modelu)
3. [Możliwości analityczne i raportowe](#możliwości-analityczne-i-raportowe)
4. [Struktura encji biznesowych](#struktura-encji-biznesowych)
5. [Uzasadnienie relacji biznesowych](#uzasadnienie-relacji-biznesowych)

---

## Opis domeny

System informatyczny firmy **Royal-bets** stanowi główną platformę obsługi klientów w obszarze zakładów wzajemnych i gier losowych.  
Baza danych oraz logika systemowa zostały zaprojektowane w celu sprawnego zarządzania procesami rejestracji graczy oraz utrzymywania uporządkowanego katalogu dostępnych gier i zdarzeń.

System wspiera pełen cykl życia transakcji:
- od momentu zawarcia zakładu,
- przez monitorowanie terminów,
- aż po końcowe rozliczenie i aktualizację statusu wypłaty.

---

## Funkcjonalność modelu

Model biznesowy przewiduje podział uprawnień dla dwóch głównych grup użytkowników:

### Dla klienta

- **Rejestracja w systemie**  
  Założenie konta użytkownika umożliwiającego korzystanie z usług platformy.

- **Zawieranie zakładów**  
  Tworzenie nowych rekordów transakcji dla wybranych zdarzeń.

- **Obsługa gier losowych**  
  Korzystanie z dostępnego katalogu gier oraz sprawdzanie wyników.

- **Podgląd historii**  
  Dostęp do historii wszystkich zawartych zakładów i transakcji.

- **Monitorowanie terminów**  
  Sprawdzanie dat rozliczenia i terminów płatności dla kuponów.

---

### Dla pracownika (bukmachera / obsługi)

- **Zarządzanie ofertą**  
  Dodawanie nowych pozycji do katalogu oraz przypisywanie parametrów do gier i zdarzeń.

- **Zarządzanie kontami klientów**  
  Tworzenie, weryfikacja oraz nadzorowanie kont użytkowników.

- **Rozliczanie transakcji**  
  Rejestrowanie wyników oraz aktualizowanie statusów zakładów.

- **Wypłacanie wygranych**  
  Autoryzacja wypłat oraz aktualizacja dat rozliczenia.

- **Identyfikacja ryzyk**  
  Wykrywanie przeterminowanych transakcji oraz monitorowanie nietypowej aktywności graczy.

---

## Możliwości analityczne i raportowe

System **Royal-bets** umożliwia generowanie raportów wspierających procesy biznesowe oraz analizę działalności platformy.

- **Statystyki aktywności**  
  Zliczanie liczby transakcji dokonanych przez poszczególnych klientów.

- **Analiza popularności**  
  Identyfikacja najczęściej wybieranych gier i zdarzeń.

- **Monitoring oferty**  
  Raportowanie pozycji z katalogu, które nigdy nie zostały wybrane przez klientów.

- **Zarządzanie płatnościami**  
  Identyfikacja klientów posiadających nierozliczone lub przeterminowane transakcje.

---

## Struktura encji biznesowych

System opiera się na kluczowych encjach reprezentujących strukturę działalności firmy:

### Klient (Reader)

Przechowuje dane identyfikacyjne użytkownika:
- unikalny adres email
- dane konta
- datę rejestracji w systemie

---

### Zakład (Loan)

Rejestruje informacje o zawartej transakcji:

- data zawarcia zakładu
- przewidywany termin rozliczenia
- opcjonalna data faktycznej wypłaty wygranej

---

### Gra / Zdarzenie (Book)

Przechowuje informacje o wydarzeniach lub grach:

- nazwa / tytuł zdarzenia
- identyfikator (ID)
- dostawca usługi

---

## Uzasadnienie relacji biznesowych

### Klient – Zakład (1:N)

Jeden klient może zawrzeć wiele zakładów, jednak każdy zakład należy dokładnie do jednego klienta.

---

### Zdarzenie – Zakład (1:N)

Jedno zdarzenie lub gra może być przedmiotem wielu zakładów zawieranych przez różnych klientów.

---

### Spójność danych

Każda transakcja finansowa w systemie musi być powiązana z istniejącym klientem, co zapewnia pełną rozliczalność operacji.

---

## Projekt

**Royal-bets System**

Dokumentację przygotowali:  
**Mateusz Hincmanowski i Patryk Błażejewski**
