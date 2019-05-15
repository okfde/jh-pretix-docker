# JS-pretix-docker

Versionskontrolle für das Pretix-setup von Jugend Hackt.

Work in progress.

## env.sample
Passe die Datei **env.sample** entsprechend Deiner Datenbank an und kopiere diese nach **.env**.

## About .po

Eine angepasste Sprachdatei basieren auf [`de_Informal`](https://github.com/pretix/pretix/tree/master/src/pretix/locale/de_Informal), in csv umgewandelt mit [csv2po](http://docs.translatehouse.org/projects/translate-toolkit/en/latest/commands/csv2po.html),
übersetzt, und zurück gewandelt.

Fehler der Konvertierung manuell ausgebessert, mit [poedit](https://poedit.net).

Inhaltlich wird hauptsächlich "Bestellung" in "Anmeldung" umgedeutet.

## About Docker

Was gerade funktioniert:

- Baue und starte den pretix-container
- kopiere die .po Dateien in den Container

``` bash
$ docker cp pretix/po/django.po your-container-id:/pretix/src/pretix/locale/de_Informal/LC_MESSAGES && \
  docker cp pretix/po/djangojs.po your-container-id:/pretix/src/pretix/locale/de_Informal/LC_MESSAGES
```

- so können auch die .mo dateien kopiert werden, _oder_ im Container nochmal bauen

``` bash
$ docker exec -it your-container-id bash
```
im Container dann

``` bash
$ cd pretix/src && make production
```

Das ist keine permanente Lösung, wir arbeiten dran
