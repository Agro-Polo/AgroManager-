# AgroManager – automatyczne aktualizacje

Ta wersja jest przygotowana do automatycznego publikowania na Firebase Hosting po każdym pushu do gałęzi `main` w GitHub.

## Jednorazowa konfiguracja GitHub

1. W Firebase/Google Cloud utwórz klucz JSON konta serwisowego z uprawnieniami do Firebase Hosting dla projektu `agromanager-2d113`.
2. W repozytorium GitHub wejdź w Settings → Secrets and variables → Actions.
3. Utwórz sekret o nazwie `FIREBASE_SERVICE_ACCOUNT_AGROMANAGER_2D113` i wklej pełną zawartość pliku JSON.
4. Wgraj zawartość tego pakietu do gałęzi `main`.
5. GitHub Actions automatycznie opublikuje aplikację na Firebase Hosting.

Po publikacji zainstalowana PWA sprawdza aktualizację przy uruchomieniu, po powrocie do aplikacji oraz co godzinę podczas działania. Gdy nowy Service Worker przejmie kontrolę, aplikacja przeładuje się do nowej wersji.

Dane gospodarstwa przechowywane w Firebase/Firestore są niezależne od plików aplikacji. Aktualizacja frontendu nie powinna usuwać danych użytkownika.
