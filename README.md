# FlightReservationApp

Flight Reservation API to aplikacja backendowa napisana w Spring Boot, umożliwiająca zarządzanie lotami, pasażerami oraz rezerwacjami. Używa bazy danych H2 (w pamięci) i udostępnia REST API.

## Wymagania

- Java 17 lub wyższa
- Maven 3.6+
- Postman (rekomendowane do testowania)

## Jak uruchomić

1. Sklonuj projekt lub otwórz w IntelliJ
2. W terminalu uruchom aplikację:
   
   mvn spring-boot:run
   
3. Backend dostępny będzie pod adresem:
   
   http://localhost:8080
   

## Konfiguracja bazy danych (H2)

Dostęp do konsoli bazy danych H2 możliwy pod adresem:


http://localhost:8080/h2-console


Dane logowania:

- JDBC URL: `jdbc:h2:mem:flightsdb`
- Użytkownik: `sa`
- Hasło: *(puste)*

## Endpointy REST API

### Flights

- GET `/flights` - lista lotów
- GET `/flights/{id}` - lot dostepny po id
- POST `/flights` - dodaj nowy lot
- PUT `/flights/{id}` - edytuj lot
- DELETE `/flights/{id}` - usuń lot

### Passengers

- GET `/passengers` - lista pasażerów
- GET `/passengers/{id}` - pasażer dostepny po id
- POST `/passengers` - dodaj pasażera
- PUT `/passengers/{id}` - edytuj pasażera
- DELETE `/passengers/{id}` - usuń pasażera

### Reservations

- GET `/reservations` - lista rezerwacji
- GET `/reservations/{id}` - rezerwacja dostepna po id
- POST `/reservations` - utwórz rezerwację
- PUT `/reservations/{id}` - edytuj rezerwację
- DELETE `/reservations/{id}` - usuń rezerwację

## Przykład użycia (Postman)

### Tworzenie nowej rezerwacji

POST `http://localhost:8080/reservations`

Body (raw JSON):

json
{
  "flightId": 1,
  "passengerId": 2,
  "seatNumber": "A1"
}


## Walidacja

- Sprawdzenie dostępności miejsc na locie
- Sprawdzenie, czy miejsce nie jest już zajęte
- Walidacja danych wejściowych (np. email, wymagane pola)
