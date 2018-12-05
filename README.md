# Zadanie rekrutacyjne Ruby on Rails

## Opis zadania i zasoby

* TL;DR: Zaprojektuj system kategorii jak na Allegro.
* [Wizualizacja pomocnicza jest tutaj](https://lchojnowski-personal.s3-eu-central-1.amazonaws.com/Ruby-on-Rails-Zadanie-rekrutacyjne-MKOIq6s40L.pdf) - możesz też zobaczyć ją w tym repozytorium jako pdf lub xml (otwiera się za pomocą [draw.io](https://www.draw.io/))

## Wymagania biznesowe

- W aplikacji mamy system kateogrii (Category)
- Oraz należacych do nich produktów (Product)
- Kategorie mają strukturę drzewa, dowolnie rozbudowanego, z jedną kategorią głowną (Root)
- Produkt może należeć tylko do jednej kateogrii, tej leżącej najgłębiej w drzewie (na przykład Root -> Samochody -> Osobowe -> Opel - czyli tylko do Opel)
- Produkt ma nazwę (string)
- Każda kategoria może posiadać nieskończoną liczbę dodatkowych atrybutów ją definiujących, na przykład:
	- Dla kategorii Opel będą to na przykład:
		- Rocznik (integer)
		- Przebieg (integer)
		- Używany (boolean)
		- Cena (decimal)
		- Benzyna/Diesel (rodzaj, wg słownika, może być ich wiele)
	- Ale możemy mieć te ż inną kategorię w serwisie, na przykład:
		- Root -> Telefony -> Apple -> iPhone
			- Cena (decimal)
			- Wersja (integer)
			- System operacyjny (string)
			- Używany (boolean)
	- I kategorie mogą też dziedziczyć słownik atrybutów z innej kategorii (na przykład Root -> Samochody -> Osobowe -> Mercedes dziedziczy z Opel - zobacz na graf) z tego samego poziomu w drzewie
- Kategoria może posiadać atrybuty wspólne z innymi kategoriami (na przykład cena, używany powyżej) oraz unikalne dla tej kategorii (na przykład wersja / przebieg powyżej)
- Nie projektuj tutaj systemu użytkowników lub logowania - nie jest istotny
- Chcemy mieć w backendzie CRUDa gdzie możemy definiować kategorie wraz z ich atrybutami, lub dziedziczenia ich (atrybutów) z innej kategorii
- Oraz CRUDA gdzie możemy tworzyć nowe produkty, i definiować im poprawnie wartości atrybutów w zależności od tego w jakim miejscu drzewa kategorii się znajdują / im wybrano
- W aplikacji powinno być miejsce, w którym będziemy mogli chodzić po drzewie kategorii, a tym samym wyświetlać listę produktów
	- Wchodząc w kategorię nadrzędną, powinienem widzieć produkty z podrzędnych kategorii
	- Będąc w kategorii podrzędnej, nie widzię produktów z kategorii bliźniaczej lub nadrzędnych (czyli będąc w Root -> Samochody -> Opel widzę tylko Ople, ale bedąc w Samochody widzę Ople, Mercedesy, etc - a bedąc w Root widzę wszystkie możliwe produkty na listingu)
- Przeglądając poszczególne kategorie zmienia nam się wygląd filtrów (tak jak na allegro - z lewej) oraz ich ilość. Czyli będąc w kategorii Root możemy filtrować produkty po cenie (bo wszystkie kategorie to mają), natomiast będą w kateogrii opel możemy to filtrować w - więcej info na grafie załączonym

## Wymagania techniczne

- Rozwiązanie powinno zostać dostarczone jako kompletny projekt repozytorium git możliwego do sklonowania (odeślij mi adres repo na githubie)
- Frontend jest bez znaczenia, może być jQuery, Vue.js, co chcesz
