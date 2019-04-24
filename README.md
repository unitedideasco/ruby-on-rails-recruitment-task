# Zadanie rekrutacyjne Ruby on Rails

## Opis zadania i zasoby

* TL;DR: Zaprojektuj system kategorii jak na Allegro
* [Wizualizacja pomocnicza jest tutaj](dodatkowe_informacje.pdf) - możesz też zobaczyć ją w tym repozytorium jako pdf lub xml (otwiera się za pomocą [draw.io](https://www.draw.io/))

## Wymagania biznesowe

- W aplikacji mamy system kategorii (Category)
- A także należacych do nich produktów (Product)
- Kategorie mają strukturę drzewa, dowolnie rozbudowanego, z jedną kategorią głowną (Root)
- Produkt może należeć tylko do jednej kategorii, tej leżącej najgłębiej w drzewie (na przykład Root -> Motoryzacja -> Opel - czyli tylko do Opel)
- Produkt ma nazwę (string)
- Każda kategoria może posiadać nieskończoną liczbę dodatkowych atrybutów ją definiujących, na przykład:
	- Dla kategorii Opel:
		- Rocznik (integer)
		- Przebieg (integer)
		- Cena (decimal)
		- Benzyna/Diesel (paliwo, wg słownika, może być ich nieskończenie wiele)
	- Ale możemy mieć te ż inną kategorię:
		- Root -> Telefony -> Apple -> iPhone
			- Cena (decimal)
			- Wersja (integer)
			- System operacyjny (string)
	- I kategorie mogą też dziedziczyć słownik atrybutów z innej kategorii (na przykład Root -> Samochody -> Mercedes dziedziczy z Opel - [zobacz na graf](dodatkowe_informacje.pdf)) z tego samego poziomu w drzewie
- Kategoria może posiadać atrybuty wspólne z innymi kategoriami (na przykład cena, używany powyżej) oraz unikalne dla tej kategorii (na przykład wersja / przebieg powyżej)
- Nie projektuj tutaj systemu użytkowników lub logowania - nie jest istotny
- Chcemy mieć w backendzie CRUDa gdzie możemy definiować kategorie wraz z ich atrybutami, lub dziedziczenia ich (atrybutów) z innej kategorii
- W aplikacji powinniśmy mieć również CRUDA gdzie możemy zarządzać produktami, i definiować im poprawnie wartości atrybutów w zależności od tego w jakim miejscu drzewa kategorii się znajdują
- W aplikacji powinno być miejsce, w którym będziemy mogli chodzić po drzewie kategorii, a tym samym wyświetlać listę produktów
	- Wchodząc w kategorię nadrzędną, powinienem widzieć produkty z podrzędnych kategorii
	- Będąc w kategorii podrzędnej, nie widzię produktów z kategorii bliźniaczej (czyli będąc w Root -> Samochody -> Opel widzę tylko Ople, ale bedąc w Samochody widzę Ople, Mercedesy, etc - a bedąc w Root widzę wszystkie możliwe produkty na listingu)
- Przeglądając poszczególne kategorie zmienia nam się wygląd filtrów (tak jak na allegro - z lewej) oraz ich ilość. Czyli będąc w kategorii Root możemy filtrować produkty po cenie (bo wszystkie kategorie to mają), natomiast będą w kateogrii opel możemy to filtrować [zobacz na graf](dodatkowe_informacje.pdf)

## Wymagania techniczne

- Rozwiązanie powinno zostać dostarczone jako kompletny projekt repozytorium git możliwego do sklonowania (odeślij mi adres repo na githubie)
- Frontend jest bez znaczenia, może być jQuery, Vue.js, React lub czym tylko chcesz :-)

## FAQ / Protips

- **Protip: Zadanie jest łatwo rozwiązać jeśli zrobisz je najpierw na kartce - projektując schemat bazy danych który jest w stanie przejść wszystkie przypadki użycia**
- Ile to zadanie zajmie? *Większość osób robi je w 2/3 dni*
- Czy muszę / mogę używać gemów? *Sposób rozwiązania nie jest narzucony, więc można*
