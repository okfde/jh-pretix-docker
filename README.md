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

In `pretix/Dockerfile` holen wir uns das Pretix Image und kopieren unsere .po dateien hinein.

Im Setup der `docker-compose.yml` benutzen wir dann 'unser eigenes' Pretix.
