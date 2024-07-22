# CI_CD_TEST

# 1. Wdrażanie lokalne Wymagania:

## dotyczące konfiguracji środowiska dla testów Cypress w projekcie. Oto kilka kroków, które powinieneś wykonać:

1. Zainstaluj `Node.js`: Upewnij się, że masz zainstalowany `Node.js` na swoim systemie. Jeśli nie, pobierz go ze strony` Node.js` i zainstaluj.

2. Sprawdź wersję `Node.js`: Upewnij się, że korzystasz z wersji `Node.js` 18 lub 20, ponieważ projekt został przetestowany na tych wersjach.

3. Zainstaluj `Git`: Jeśli jeszcze tego nie zrobiłeś, zainstaluj `Git` na swoim komputerze. Możesz pobrać go ze strony `Git`.

4. Otwórz katalog projektu: Przejdź do katalogu głównego swojego projektu za pomocą wiersza poleceń lub terminala.

5. Sklonuj repozytorium: Sklonuj repozytorium projektu za pomocą komendy` git clone <adres-repozytorium>`.

6. Zainstaluj moduły lokalnie: W katalogu projektu uruchom komendę `npm init -y`, aby zainstalować moduły zdefiniowane w pliku `package.json`.

7. Dodajemy do projektu Cypress lokalnie `npm install cypress --save-dev`.

8. Uruchom testy: Aby uruchomić testy, użyj komendy `npx cypress open` - pierwsze uruchomienie.

9. W oknie startowym Cypress wybierz `E2E Testing`.

10. Zostaną zaproponowane 4 pliki z testami, które automatycznie zostaną pobrane po kliknięciu `continue`.

11. Wybierz domyślną przeglądarkę, sugestia `Google Chrome` i `Start E2E Testing in Chrome`.

12. Po otwarciu interfejsu webowego Cypress wybierz `Create new spec`.

13. ## Ponowne uruchomienia Cypress na komendę w VScode/terminal `npx cypress open`.

14. Aby opisać `workflows` tworzymy folder `.github`, w nim podkatalog `workflows` a w nim plik `main.yml` (zawartość do podejrzenia w repozytorium).

15. Modyfikujemy `package.json`

```
"scripts": {
    "test": "cypress run"
  },

```

# 2. CI/CD Actions

- ## Tworzenie repozytorium projektu na GitHubie:

- Rozpoczynamy od utworzenia nowego repozytorium na` GitHubie`.

- Nadajemy mu nazwę i dodajemy pliki z naszą pracą.

- ## Klonowanie repozytorium lokalnie:

  - Klonujemy repozytorium na nasz lokalny komputer, używając komendy` git clone`.

  - W ten sposób pobieramy zawartość repozytorium na dysk twardy.

- ## Wysyłanie zawartości na GitHub:

  - Po dokonaniu zmian w plikach, używamy komendy `git push`, aby przesłać naszą pracę na `GitHuba`.

- ## Konfiguracja workflow w GitHub Actions:

  - Przechodzimy do repozytorium na GitHubie.

  - Wybieramy zakładkę “Actions”.

  - Klikamy przycisk “Set up a workflow yourself” (konfiguracja własnego workflow).

  - Tworzymy plik `YAML`, np. `main.yml`, w folderze `.github/workflows`.

- ## Sprawdzanie poprawności pliku YAML:

  - Otwieramy plik `main.yml` i upewniamy się, że zawiera poprawne definicje zadań (jobs) i kroków (steps).

  - Możemy korzystać z gotowych szablonów lub dostosować konfigurację do naszych potrzeb.

- ## Testowanie workflow:

  - Po zapisaniu pliku `YAML`, wrzucamy go na `GitHuba`.

  - Workflow zostanie automatycznie uruchomiony przy kolejnym `pushu` do gałęzi main.

- ## Sprawdzanie wyników w zakładce Actions:

  - Wchodzimy do zakładki “Actions” i wybieramy nasz workflow.

  - Sprawdzamy, czy wszystko działa poprawnie.

  - Jeśli coś wymaga poprawek, dostosowujemy plik `YAML` lub kod.

## Plik z testami:

`login_tests.cy.js`

# Zestawienie tych samych testów z zastosowaniem Page object pattern i bez.

Dwa sposoby pisania testów, na tym samym zestawie testów.

Wyjściowy zestaw testów `cypress-js-tests1/cypress/e2e/nonPOP.cy.js`

i do niego stworzony odpowiednik z zastosowaniem POP `cypress-js-tests1/cypress/e2e/POP.cy.js`
oraz z logiką `cypress-js-tests1/cypress/pages/OLDLogin.js`.

# Zastosowanie Page object pattern w testach.

1. Poprzednie testy z wykorzystaniem wzorca `Page object pattern` - `login.cy.js`.

2. Każda strona ma swój własny plik w folderze `pages`:

a. Dla strony logowania istnieje plik `Login.js`.

b. Dla strony głównej istnieje plik `HomePage.js`.
