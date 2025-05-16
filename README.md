 # Instrukcja instalacji strony internetowej i bazy danych

## Krok 1: Wgranie plików na serwer

1. Skopiuj wszystkie pliki z folderu `website` znajdującego się na nośniku do katalogu na serwerze, w którym ma działać strona (np. `/var/www/html`, `public_html`, itp.).
2. Upewnij się, że wszystkie pliki zostały poprawnie przesłane i mają odpowiednie uprawnienia do odczytu przez serwer [WWW](http://WWW).

## Krok 2: Utworzenie bazy danych

1. Zaloguj się do panelu zarządzania bazą danych (np. phpMyAdmin) lub użyj klienta MySQL.
2. Utwórz nową bazę danych z kodowaniem **utf8-polish-ci**:

   ```sql
   CREATE DATABASE nazwa_bazy_danych CHARACTER SET utf8 COLLATE utf8_polish_ci;
   ```
3. Zaimportuj strukturę i dane:

   * Przejdź do folderu `database` na nośniku.
   * Znajduje się tam plik `.sql` zawierający strukturę i dane bazy.
   * Użyj go do importu.

## Krok 3: Konfiguracja połączenia z bazą danych

1. Otwórz plik `config.php` znajdujący się w folderze strony.
2. Zmień wartości zmiennych na odpowiednie dane:

   ```php
   $host = 'IP_serwera_bazy_danych';
   $db_user = 'nazwa_uzytkownika';
   $db_password = 'haslo_uzytkownika';
   $db_name = 'nazwa_bazy_danych';
   ```
3. Zapisz zmiany w pliku i upewnij się, że plik `config.php` jest zabezpieczony przed dostępem z zewnątrz.

## Krok 4: Gotowe

Po wykonaniu powyższych kroków strona powinna być gotowa do działania. Otwórz ją w przeglądarce, aby upewnić się, że wszystko działa poprawnie.
