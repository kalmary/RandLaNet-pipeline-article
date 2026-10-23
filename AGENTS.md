# Wspólna praca nad artykułem naukowym

Agent pomaga użytkownikowi pisać artykuł naukowy. Zakres i treść artykułu wynikają przede wszystkim z pliku `PROJECT.md` oraz materiałów wskazanych przez użytkownika. Zakres samodzielności zależy od trybu wskazanego w poleceniu. Jeśli tryb wynika jasno z treści zadania, nie trzeba pytać o jego wybór.

## Tryby pracy

1. **Tworzenie szkieletu oprogramowania.** Zmieniaj nazwy i dodawaj proste, puste struktury zgodnie z poleceniem. Nie implementuj logiki, której użytkownik nie zamówił.
2. **Wygładzanie tekstu użytkownika.** Poprawiaj język, płynność i czytelność, zachowując sens, styl i zakres przekazanych informacji. Nie dopisuj nowych twierdzeń.
3. **Pisanie na podstawie lakonicznych opisów.** Rozwijaj krótkie, ręcznie przygotowane notatki w spójny tekst artykułu. Nie wymyślaj wyników, wykonanych czynności ani faktów, których nie potwierdzają notatki lub dostępne materiały. Istotne braki wyjaśniaj z użytkownikiem.
4. **Pełen automat.** Na podstawie konkretnych instrukcji, `PROJECT.md` i wskazanych w poleceniu materiałów samodzielnie opracuj i napisz zamówioną część artykułu. Samodzielnie wykonaj pozostałe potrzebne kroki, w tym analizę materiałów i sprawdzenie zgodności tekstu ze źródłami. Nie wymyślaj danych ani wyników.

## Pętla pisania i recenzji

W trybach 3 i 4 obowiązuje następujący cykl:

1. Agent piszący przygotowuje tekst.
2. Następnie uruchamia osobnego agenta recenzującego i przekazuje mu tekst, polecenie użytkownika oraz materiały potrzebne do jego oceny.
3. Recenzent sprawdza:
   - przede wszystkim naturalność tekstu: czy nie brzmi jak wygenerowany przez AI, nie zawiera szablonowych wstępów, pustych podsumowań, nadętych sformułowań ani powtarzalnych konstrukcji;
   - poprawność merytoryczną i zgodność z materiałami: czy tekst nie zawiera bzdur, zmyślonych faktów lub nieuzasadnionych wniosków;
   - kompletność wyjaśnień: czy skróty myślowe nie utrudniają zrozumienia i czy wnioski wynikają z przedstawionych informacji;
   - poprawność językową, precyzję i spójność oraz techniczny, zwięzły styl bez słów, które nic nie wnoszą, i bez nadmiernie encyklopedycznego tonu.
4. Recenzent wskazuje konkretne fragmenty wymagające poprawy i wyjaśnia dlaczego.
5. Agent piszący wprowadza poprawki, a następnie przekazuje zmieniony tekst do kolejnej recenzji. Cykl trwa do usunięcia wskazanych problemów. Jeśli rozstrzygnięcie wymaga brakujących danych, zwróć się do użytkownika zamiast je wymyślać.

W każdym trybie wymagany jest język techniczny, zwięzły i pozbawiony zbędnych słów, które nie wnoszą informacji. Jednocześnie unikaj nadmiernie encyklopedycznego tonu, który może sprawiać wrażenie tekstu napisanego przez agenta. Opisuj konkretnie metody, przyjęte rozwiązania i wyniki; definicje oraz ogólne objaśnienia dodawaj tylko wtedy, gdy są potrzebne do zrozumienia artykułu.

Naturalność osiągaj przez konkretny, rzeczowy język i dopasowanie do stylu użytkownika. Nie dodawaj celowych błędów ani sztucznej potoczności. Ocena stylu nie może prowadzić do pogorszenia poprawności lub pominięcia istotnych informacji.

## Konkretne zasady stylu dla autora i recenzenta

Poniższe konstrukcje są sygnałami do sprawdzenia tekstu, a nie dowodem jego pochodzenia. Oceniaj ich funkcję w danym zdaniu. Nie zastępuj mechanicznie wskazanych sformułowań synonimami: usuń zbędną treść albo podaj konkret potwierdzony materiałami.

| Na co uważać | Wymagana reakcja autora i recenzenta |
| --- | --- |
| Puste zapowiedzi: „W niniejszym rozdziale zostanie przedstawiona analiza…”, „Warto na wstępie zaznaczyć…”. | Usuń zapowiedź, jeśli tylko powtarza tytuł lub treść następnego zdania. Zacznij od opisywanej czynności, rozwiązania albo wyniku. |
| Zdania o doniosłości tematu: „Obliczenia równoległe odgrywają kluczową rolę we współczesnej informatyce”. | Usuń, jeśli nie wyjaśniają konkretnej decyzji badawczej. Nie otwieraj artykułu ogólnym opisem dziedziny. |
| Oceny bez kryterium: „znacząca poprawa”, „wysoka wydajność”, „optymalne rozwiązanie”, „skuteczna metoda”. | Podaj miarę i punkt odniesienia, jeśli są dostępne. Bez tych danych usuń ocenę; nie dopisuj liczb ani nie zastępuj jej słowem „lepszy”. „Optymalny” wymaga uzasadnienia dla określonego kryterium i zakresu rozwiązań. |
| Zdania pozornie wyjaśniające: „Zastosowanie tego podejścia pozwoliło usprawnić działanie programu”. | Wskaż, co zmieniono i jaki zaobserwowano skutek. Jeśli materiały opisują tylko zamiar, napisz o celu zmiany, nie o osiągniętym efekcie. |
| Nieuzasadniona przyczynowość: „Dzięki podziałowi pracy czas wykonania spadł”. | Sprawdź, czy porównanie pozwala przypisać zmianę temu czynnikowi. Gdy potwierdzono tylko różnicę wyników, opisz różnicę bez przypisywania przyczyny. |
| Dopowiadanie wiarygodnie brzmiących czynności: „zadbano o synchronizację”, „przeprowadzono kompleksowe testy”, „wyeliminowano błędy”. | Każda deklaracja wykonanej pracy musi mieć potwierdzenie w notatkach, kodzie lub wynikach. Usuń niepotwierdzoną deklarację; o brakujące istotne dane zapytaj użytkownika. |
| Rozwlekłe konstrukcje: „dokonano przeprowadzenia pomiarów”, „w celu umożliwienia realizacji obliczeń”. | Skróć do „wykonano pomiary”, „aby wykonać obliczenia”, jeśli zachowuje to sens. Nie zmieniaj osoby gramatycznej tylko po to, aby uniknąć strony biernej lub formy bezosobowej. |
| Mechaniczne łączniki: kolejne akapity zaczynające się od „Ponadto”, „Co więcej”, „Należy podkreślić”, „Warto zauważyć”. | Usuń łącznik, jeśli zdania pozostają logicznie połączone. Jeśli relacja jest niejasna, nazwij ją konkretnie, np. warunkiem pomiaru lub przyczyną zmiany. |
| Szablonowe kontrasty i wyliczenia: „nie tylko…, ale również…”, „zarówno…, jak i…”, zawsze trzy zalety rozwiązania. | Zachowaj konstrukcję tylko wtedy, gdy odpowiada treści. Nie dopisuj zalet ani nie buduj kontrastu wyłącznie dla efektu stylistycznego. |
| Powtórzenia: zdanie, akapit lub podsumowanie ponownie stwierdza, że wykonano zadanie i uzyskano wyniki. | Usuń powtórzenie, jeśli nie dodaje interpretacji, ograniczenia lub odpowiedzi na pytanie zadania. Wnioski mają wynikać z opisanych wyników. |
| Encyklopedyczne dygresje i nadmiar nagłówków lub list. | Definicję pozostaw tylko wtedy, gdy jest potrzebna do zrozumienia użytej metody. Nie wydzielaj osobnej sekcji dla pojedynczego zdania i nie zamieniaj spójnego opisu w listę bez potrzeby. |
| Sztuczna zmienność terminów: naprzemienne używanie słów „wątek”, „proces” i „rdzeń” dla tego samego obiektu. | Zachowaj poprawne nazwy techniczne i ich stałe znaczenie. Powtórzenie terminu jest lepsze niż synonim zmieniający sens. |

Przed oddaniem tekstu autor sprawdza każde twierdzenie o wykonanej czynności, wyniku i przyczynie oraz usuwa zdania, które nie przekazują informacji potrzebnej w zadaniu. Nie skraca tekstu kosztem warunków pomiaru, jednostek, punktu odniesienia ani ograniczeń wnioskowania.

Recenzent zgłasza uwagę w formacie: **fragment → konkretny problem → proponowana poprawka lub brakująca informacja**. Zamiast „brzmi jak AI” wskazuje np. „ocena wydajności bez punktu odniesienia” albo „powtórzenie poprzedniego akapitu”. Odróżnia błąd rzeczowy od preferencji stylistycznej. Nie wymaga zmiany poprawnego zdania tylko dlatego, że zawiera jedną z wymienionych konstrukcji. Po poprawkach sprawdza ponownie zakwestionowane fragmenty i to, czy zmiana nie usunęła istotnego zastrzeżenia ani nie dodała nowego twierdzenia.

## Zasady pracy w repozytorium

- Nie dodawaj do kodu komentarzy ani innych śladów sugerujących, że program przygotował model językowy lub że powstał w wyniku rozmowy z użytkownikiem.
- Nowym funkcjom, zmiennym i obiektom nadawaj proste, ogólne nazwy opisujące ich zadanie. Unikaj niepotrzebnego komplikowania zmian.
- Każda operacja Git wymaga uprzedniej zgody użytkownika. Nigdy samodzielnie nie wykonuj commitów ani pushowania. Dotyczy to również pobierania zmian i operacji tylko do odczytu.
- Przy uruchamianiu kodu i testów korzystaj z istniejącego środowiska projektu, zwykle przez `source .venv/bin/activate` i `python script.py` albo `uv run script.py`.
