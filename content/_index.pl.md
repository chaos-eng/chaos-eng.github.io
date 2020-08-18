+++
title = "ZASADY INŻYNIERII CHAOSU"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# ZASADY INŻYNIERII CHAOSU
Ostatnia modyfikacja: Sierpień 2019 

*Inżynieria Chaosu to zestaw praktyk, które polegają na wykonywaniu kontrolowanych eksperymentów na systemie w celu zidentyfikowania, analizy i usunięcia jego słabych punktów, tak aby później mógł on utrzymać pełną stabilność na produkcji pomimo pojawiających się problemów.*

Postęp w budowaniu rozproszonych systemów dużej skali zmienia zasady, którymi rządzą się procesy wytwarzania oprogramowania. Jako branża, musimy stosować kolejne ulepszenia, które pozwolą nam na większą elastyczność i szybsze wdrożenia oprogramowania na produkcję. Ciągła pogoń za szybkością wprowadzania zmian do naszego systemu pozostawia nas z pytaniem: jak dużą mamy pewność, że nasze złożone systemy będą spisywały się bez zastrzeżeń w dłuższej perspektywie?

Nawet jeżeli wszystkie usługi, które wchodzą w skład naszego rozproszonego systemu, działają poprawnie w izolacji, interakcje pomiędzy nimi mogą doprowadzić do nieprzewidywalnych skutków. Te z kolei, połączone z rzadkimi, ale zakłócającymi pracę zdarzeniami losowymi, powodują, że nasze systemy zachowują się z natury chaotycznie.

Naszym zadaniem jest identyfikacja tych słabych punktów, zanim one spowodują nieprawidłowości w działaniu całego systemu. Przykładem takich słabych punktów systemu są: nieprawidłowe zachowanie w przypadku awarii zewnętrznej usługi, grad ponowień spowodowany nieprawidłowym ustawieniem czasów oczekiwania na odpowiedź, awarie spowodowane niedostępnością zależnej usługi, która jest przeciążona, kaskadowe awarie spowodowane niedostępnością krytycznej i jedynej zależności itp. Wszystkie słabe punkty, muszą zostać zidentyfikowane oraz proaktywnie naprawione, zanim wpłyną na klientów końcowych i działanie systemów produkcyjnych. Potrzebujemy mechanizmów, które pozwolą ujarzmić istniejący w nich naturalny chaos, tak aby uzyskać większą elastyczność i szybkość wdrożeń, oraz upewnić się, że systemy, które zbudowaliśmy, będą zachowywały się stabilnie, pomimo ich stopnia złożoności.

Jedynie empiryczne podejście, skupione na analizie systemowej, pozwala okiełznać problem istniejącego chaosu w rozproszonych systemach dużej skali i zyskać pewność, że ich architektura pozwala na przetrwanie w rzeczywistych warunkach. Sprawdzamy to za pomocą obserwacji zachowania analizowanego systemu podczas kontrolowanego eksperymentu. A taką praktykę nazywamy Inżynierią Chaosu.

## INŻYNIERIA CHAOSU W PRAKTYCE

Inżynieria Chaosu wprowadza reguły, w jaki sposób przeprowadzać kontrolowane eksperymenty, aby wykrywać słabości systemu. Oto cztery kroki, według których eksperymenty te powinny przebiegać:

1. Rozpocznij od zdefiniowania ‘stanu bazowego’, udokumentowanego za pomocą pomiarów i wyników działania wskazującego na normalne zachowanie badanego systemu.
2. Postaw hipotezę, że stan bazowy zostanie utrzymany na czas eksperymentu dla grupy badanej oraz grupy kontrolnej.
3. Wprowadź zmienne, które odzwierciedlają rzeczywiste zdarzenia np. awaria serwera, uszkodzenia dysków twardych, spowolnione lub zerwane połączenia sieciowe itp.
4. Spróbuj obalić hipotezę, porównując różnice pomiędzy stanem bazowym grupy badanej oraz grupy kontrolnej.

Im trudniej jest zakłócić stan bazowy, tym większa pewność, że system będzie zachowywał się poprawnie w przypadku problemów. Jeśli za pomocą eksperymentu, udało się odkryć słabość, mamy w tym momencie scenariusz pozwalający na odtworzenie niepożądanego zachowania, w celu jego usunięcia, zanim doprowadzi on do awarii.

## ZAAWANSOWANE ZASADY

Zasady przedstawione poniżej pomogą Ci zaaplikować Inżynierię Chaosu do procesu opisanego w powyższych krokach. To, jaki nacisk położysz na podążanie za zasadami, bezpośrednio przekłada się na pewność, z jaką będziesz rozwijać i utrzymywać swój system.

### Stawiaj hipotezy dotyczące stanu bazowego

Skupiaj się bardziej na tym, co widać na wyjściu analizowanego systemu niż na jego wewnętrznych lub zaprojektowanych cechach. Pomiary metryk wyjściowych w krótkich odstępach czasu będą stanowić odzwierciedlenie stanu bazowego. Przykładami takich metryk mogą być: przepustowość systemu, liczba błędów, histogramy czasu opóźnień itp. Dzięki temu podczas eksperymentów możemy skupić się na analizie systemowych słabości w czasie rzeczywistym oraz weryfikujemy działanie systemu, zamiast analizować, jak teoretycznie nasz system powinien działać.

### Przygotuj rzeczywiste scenariusze awarii

Niepożądane działanie naszych systemów spowodowane jest wydarzeniami ze świata rzeczywistego. Podczas eksperymentów, należy skupić się w pierwszej kolejności na tych zdarzeniach, które mają największy wpływ na działanie systemu lub występują najczęściej. Bierz pod uwagę zdarzenia, które odzwierciedlają awarie sprzętowe (np. awaria serwera), awarie oprogramowania (np. nieprawidłowe lub nieoczekiwane odpowiedzi) oraz akceptowalne wydarzenia związane z ruchem (np. nieoczekiwany skok w liczbie zapytań) lub skalowaniem infrastruktury. Każde zdarzenie, które może zakłócić stabilność stanu bazowego, jest potencjalną zmienną podczas eksperymentów Inżynierii Chaosu.

### Wykonuj eksperymenty na systemach produkcyjnych

Systemy zachowują się inaczej w zależności od środowiska oraz wzorców ruchu. Skoro zachowanie związane z jego eksploatacją może zmienić się w każdym momencie, próbkowanie rzeczywistego ruchu jest jedynym sposobem, aby odtworzyć produkcyjne zachowanie systemu dla analizowanej ścieżki. W celu zagwarantowania autentyczności zachowania systemu oraz prawidłowego punktu odniesienia do rzeczywistego zachowania, zasady Inżynierii Chaosu sugerują, aby eksperymenty wykonywać bezpośrednio na systemie produkcyjnym.

### Zautomatyzuj wykonywanie eksperymentów

Przeprowadzanie eksperymentów metodami manualnymi jest czasochłonne oraz nieefektywne. Podłącz zautomatyzowane uruchamianie eksperymentów do swojego procesu ciągłej integracji/ciągłych wdrożeń (CI/CD). Dzięki temu praktyki Inżynierii Chaosu pomogą w dążeniu do tego, aby budować prawidłową automatyzację naszego systemu, która pomaga w orkiestracji wydarzeń oraz analizie i obserwacji.

### Minimalizuj strefę wpływu eksperymentu

Eksperymenty na systemie produkcyjnym mogą generować niepotrzebne problemy dla użytkowników końcowych. Oczywiście, przeprowadzenie takich eksperymentów musi być poprzedzone zgodą na pewne negatywne skutki uboczne, ale zadaniem i obowiązkiem Inżynierów Chaosu jest upewnienie się, że potencjalne konsekwencje kontrolowanej awarii będą jak najmniejsze.

Inżynieria Chaosu to zestaw potężnych praktyk, które zmieniły sposób, w jakim projektuje oraz implementuje się oprogramowanie w wielu firmach na całym świecie, także tych największych. Tam, gdzie inne praktyki skupiają się wyłącznie na szybkości wytwarzania i elastyczności, omawiane reguły skupiają się przede wszystkim na usuwaniu niepewności pojawiających się w systemach rozproszonych. Jako skutek uboczny ich stosowania, oprócz zaufania, uzyskujemy przewidywalność, i możliwość szybszego rozwoju. Dzięki temu jesteśmy w stanie dostarczyć klientom końcowym produkt i doświadczenia wysokiej jakości, na które zasługują.

Dołącz do oficjalnej grupy dyskusyjnej Chaos Community, aby porozmawiać o zasadach inżynierii chaosu [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
