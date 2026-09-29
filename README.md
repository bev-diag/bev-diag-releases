# BEV Diag: wersje testowe

Testowe wersje aplikacji **BEV Diag** na Androida: diagnostyka baterii
trakcyjnej samochodów elektrycznych przez adapter OBD (ELM327/STN), w
duchu LeafSpy Pro. Na razie obsługiwany jest **Nissan Leaf** (testowany
na AZE0).

To repozytorium zawiera tylko wydania (pliki APK). Kod aplikacji jest
prywatny.

## Instalacja

1. Otwórz [najnowsze wydanie](https://github.com/bev-diag/bev-diag-releases/releases/latest)
   na telefonie i pobierz plik `.apk`.
2. Otwórz pobrany plik. Android zapyta o zgodę na instalację z tego
   źródła (przeglądarki lub menedżera plików); zezwól.
3. Przy **pierwszym uruchomieniu** telefon musi mieć internet: aplikacja
   sprawdza, czy ta wersja jest aktualna. Potem działa także bez
   internetu, np. podłączona do WiFi adaptera.

## Adaptery

- Bluetooth LE (np. Konnwei KW905, Vgate, OBDLink CX)
- Bluetooth klasyczny (najpierw sparuj adapter w ustawieniach telefonu)
- WiFi (domyślnie 192.168.0.10:35000)

## Ważne: to wersja testowa

- Aplikacja może pokazywać błędne wartości. Nie podejmuj na ich podstawie
  decyzji o zakupie lub naprawie auta.
- Każda wersja testowa działa **90 dni** od zbudowania. 14 dni przed
  końcem aplikacja o tym przypomni; wtedy pobierz nowszą.
- Wersję z poważnym błędem możemy zdalnie wyłączyć. Aplikacja powie
  wtedy, żeby pobrać nową; nagrane sesje nadal da się wyeksportować.

## Zgłaszanie błędów

[Załóż zgłoszenie](https://github.com/bev-diag/bev-diag-releases/issues/new/choose)
(potrzebne konto GitHub). Bardzo pomaga log ruchu adaptera:
Ustawienia → Logi ruchu adaptera → Udostępnij ostatni log.

---

## English

Test builds of **BEV Diag** for Android: traction battery diagnostics for
EVs over an ELM327/STN OBD adapter. Currently supports the **Nissan Leaf**
(tested on AZE0). This repository holds releases only; the source is
private.

Download the `.apk` from the
[latest release](https://github.com/bev-diag/bev-diag-releases/releases/latest)
and allow installing from that source. The **first start needs the
internet** (the app checks that the version is current); after that it
works offline. Each test build works for **90 days** after it was built.
Report problems in [Issues](https://github.com/bev-diag/bev-diag-releases/issues/new/choose),
ideally with the adapter traffic log (Settings → Adapter traffic logs).

## For maintainers

`latest.json` on `main` is read by every test build:

| Field | Effect |
|---|---|
| `latest` | newer than the installed build: banner with a download link |
| `min_version` | installed build older than this: the app is blocked |
| `sunset` | `true`: banner "testing has ended"; point `url` at the store |
| `message` | optional note by language, e.g. `{"pl": "…", "en": "…"}` |
| `url` | download link; defaults to the latest release |

A broken `latest.json` stops every newly installed build from starting.
Check it with `python3 -m json.tool latest.json` before pushing.
