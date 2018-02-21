# Ruby on Rails Developer Recruitment Task

Napisać prostą aplikację do sprawdzania prognozy pogody z wykorzystaniem jakiejś darmowej usługi np. http://apidev.accuweather.com/developers/ lub http://openweathermap.org/api (do wyboru programisty)

## Założenia biznesowe

- Na pierwszym widoku będzie można podać miasto dla którego chce się wyszukać prognozę pogody lub wybrać jedno z miast już wcześniej wyszukiwanych. Wskazane jest zrobienie zapamiętywania wyszukiwanych miast pomiędzy sesjami aplikacji. Nazwa miejscowości ma być walidowana wg wyrażenia regularnego a-zA-Z
- Po pobraniu prognozy pogody dla podanego miasta ma nastąpić nawigacja do nowego widoku ze szczegółami prognozy. Podczas nawigacji, mają zostać przekazane wcześniej pobrane dane pogodowe do nowego widoku
- Ilość szczegółów prognozy pogody na ekranie szczegółowym jest dowolna. Może być np. temperatura aktualna, stan zachmurzenia, możliwość opadów, tabelka z temperaturami na najbliższe godziny itd w zależności co uda się pobrać z usługi. Po przejściu na ekran szczegółów mogą być dociągane jakieś dodatkowe dane, np. prognoza na kolejne dni
- Kolor czcionki temperatury ma różnić się w zależności od stopni -> poniżej 10 stopni kolor niebieski, między 10 a 20 stopni kolor czarny, powyżej 20 kolor czerwony
- UI aplikacji pozostawiamy w gestii programisty - ma być taki, jaki programista chciałby sam używać w swojej aplikacji

## Założenia techniczne

- Rozwiązanie powinno zostać dostarczone jako kompletny projekt repozytorium git możliwego do sklonowania
- Aplikacja powinna być napisana w najnowszej wersji frameworka ruby on rails
