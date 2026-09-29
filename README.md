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

### Adaptery

Potwierdzone (sprawdzone z aplikacją):

- Konnwei KW905
- Qerk KW905

Inne adaptery ELM327/STN mogą działać, ale nie są jeszcze potwierdzone.
Aplikacja łączy się przez:

- Bluetooth LE
- Bluetooth klasyczny (najpierw sparuj adapter w ustawieniach telefonu)
- WiFi (domyślnie 192.168.0.10:35000)

Działa Ci inny adapter? Koniecznie
[daj znać](https://github.com/bev-diag/bev-diag-releases/issues/new?template=adapter.yml),
dopiszemy go do listy.

### Ważne: to wersja testowa

- Aplikacja może pokazywać błędne wartości. Nie podejmuj na ich podstawie
  decyzji o zakupie lub naprawie auta.
- Wersje testowe mają ograniczony czas działania; aplikacja powie, kiedy
  pobrać nowszą.

### Zgłaszanie błędów

[Załóż zgłoszenie](https://github.com/bev-diag/bev-diag-releases/issues/new/choose)
(potrzebne konto GitHub). Bardzo pomaga log ruchu adaptera:
Ustawienia → Logi ruchu adaptera → Udostępnij ostatni log.

### Kontakt

Pytania, uwagi albo zgłoszenie bez konta GitHub:
[bevdiag@gmail.com](mailto:bevdiag@gmail.com)

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

### Adapters

Confirmed (tested with the app):

- Konnwei KW905
- Qerk KW905

Other ELM327/STN adapters may work but are not confirmed yet. The app
connects over:

- Bluetooth LE
- Bluetooth Classic (pair the adapter in the phone's settings first)
- WiFi (default 192.168.0.10:35000)

Another adapter works for you? Be sure to
[let us know](https://github.com/bev-diag/bev-diag-releases/issues/new?template=adapter.yml),
and we will add it to the list.

### Important: this is a test build

- The app may show wrong values. Do not base decisions about buying or
  repairing a car on them.
- Test builds work for a limited time; the app tells you when to get a
  newer one.

### Reporting problems

[Open an issue](https://github.com/bev-diag/bev-diag-releases/issues/new/choose)
(needs a GitHub account). The adapter traffic log helps a lot:
Settings → Adapter traffic logs → Share latest log.

### Contact

Questions, feedback, or a report without a GitHub account:
[bevdiag@gmail.com](mailto:bevdiag@gmail.com)
