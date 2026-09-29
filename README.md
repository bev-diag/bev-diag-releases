# BEV Diag: wersje testowe / test builds

[Polski](#polski) · [English](#english)

---

## Polski

Testowe wersje aplikacji **BEV Diag** na Androida: diagnostyka baterii
trakcyjnej samochodów elektrycznych przez adapter OBD (ELM327/STN), w
duchu LeafSpy Pro. Na razie obsługiwany jest **Nissan Leaf** (testowany
na AZE0).

To repozytorium zawiera tylko wydania (pliki APK). Kod aplikacji jest
prywatny.

### Instalacja

1. Otwórz [najnowsze wydanie](https://github.com/bev-diag/bev-diag-releases/releases/latest)
   na telefonie i pobierz plik `.apk`.
2. Otwórz pobrany plik. Android zapyta o zgodę na instalację z tego
   źródła (przeglądarki lub menedżera plików); zezwól.
3. Przy **pierwszym uruchomieniu** telefon musi mieć internet: aplikacja
   sprawdza, czy ta wersja jest aktualna. Potem działa także bez
   internetu, np. podłączona do WiFi adaptera.

### Adaptery

- Bluetooth LE (np. Konnwei KW905, Vgate, OBDLink CX)
- Bluetooth klasyczny (najpierw sparuj adapter w ustawieniach telefonu)
- WiFi (domyślnie 192.168.0.10:35000)

### Ważne: to wersja testowa

- Aplikacja może pokazywać błędne wartości. Nie podejmuj na ich podstawie
  decyzji o zakupie lub naprawie auta.
- Każda wersja testowa działa **90 dni** od zbudowania. 14 dni przed
  końcem aplikacja o tym przypomni; wtedy pobierz nowszą.
- Wersję z poważnym błędem możemy zdalnie wyłączyć. Aplikacja powie
  wtedy, żeby pobrać nową; nagrane sesje nadal da się wyeksportować.

### Zgłaszanie błędów

[Załóż zgłoszenie](https://github.com/bev-diag/bev-diag-releases/issues/new/choose)
(potrzebne konto GitHub). Bardzo pomaga log ruchu adaptera:
Ustawienia → Logi ruchu adaptera → Udostępnij ostatni log.

### Dla opiekunów

Plik `latest.json` na gałęzi `main` czyta każda wersja testowa:

| Pole | Działanie |
|---|---|
| `latest` | nowsza niż zainstalowana wersja: baner z linkiem do pobrania |
| `min_version` | zainstalowana wersja starsza niż ta: aplikacja jest zablokowana |
| `sunset` | `true`: baner „Testy zakończone”; ustaw `url` na sklep |
| `message` | opcjonalna wiadomość w danym języku, np. `{"pl": "…", "en": "…"}` |
| `url` | link do pobrania; domyślnie najnowsze wydanie |

Uszkodzony `latest.json` sprawia, że żadna świeżo zainstalowana wersja
się nie uruchomi. Przed wypchnięciem sprawdź go:
`python3 -m json.tool latest.json`.

---

## English

Test builds of the **BEV Diag** app for Android: traction battery
diagnostics for electric cars over an OBD adapter (ELM327/STN), in the
spirit of LeafSpy Pro. For now the **Nissan Leaf** is supported (tested
on the AZE0).

This repository holds releases (APK files) only. The app's source code is
private.

### Installing

1. Open the [latest release](https://github.com/bev-diag/bev-diag-releases/releases/latest)
   on your phone and download the `.apk` file.
2. Open the downloaded file. Android asks whether to allow installing from
   that source (the browser or file manager); allow it.
3. On the **first start** the phone needs the internet: the app checks
   that this version is current. After that it also works offline, e.g.
   connected to the adapter's WiFi.

### Adapters

- Bluetooth LE (e.g. Konnwei KW905, Vgate, OBDLink CX)
- Bluetooth Classic (pair the adapter in the phone's settings first)
- WiFi (default 192.168.0.10:35000)

### Important: this is a test build

- The app may show wrong values. Do not base decisions about buying or
  repairing a car on them.
- Each test build works for **90 days** after it was built. The app
  reminds you 14 days before the end; get a newer one then.
- A build with a serious bug can be switched off remotely. The app then
  tells you to get a new one; recorded sessions can still be exported.

### Reporting problems

[Open an issue](https://github.com/bev-diag/bev-diag-releases/issues/new/choose)
(needs a GitHub account). The adapter traffic log helps a lot:
Settings → Adapter traffic logs → Share latest log.

### For maintainers

Every test build reads `latest.json` on the `main` branch:

| Field | Effect |
|---|---|
| `latest` | newer than the installed build: banner with a download link |
| `min_version` | installed build older than this: the app is blocked |
| `sunset` | `true`: banner "Testing has ended"; point `url` at the store |
| `message` | optional note by language, e.g. `{"pl": "…", "en": "…"}` |
| `url` | download link; defaults to the latest release |

A broken `latest.json` stops every newly installed build from starting.
Check it before pushing: `python3 -m json.tool latest.json`.
