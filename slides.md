---
theme: seriph
# background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: prism
lineNumbers: false
info: |
  ## Schulung Home Assistant
drawings:
  persist: false
transition: slide-left
title: Schulung Home Assistant
mdc: true

---

# Schulung Home Assistant

## Heimautomatisierung mit Home Assistant (Einstieg)

---

# Agenda

#TODO: Agenda füllen

---

# Vor dem Kurs - 1

- Vorbereitung: Download und Installation von Homeassistant OS

---

# Vor dem Kurs - 2: Downloads

* [Virtualbox](https://www.virtualbox.org) (Herunterladen und installieren)
* [Homeassistant OS für Virtualbox](https://www.home-assistant.io/installation/windows)
  * Image für Virtualbox herunterladen
  * Anleitung auf der Seite folgen (Achtung: Virtualbox spezifische Anleitung befolgen!)

Altnerativ:
* Wer Homeassistant (OS) schon installiert hat, kann dieses nutzen

---

# Vor dem Kurs - 3: Installation für diese Schulung

* Virtualbox installieren
* Homeassistant OS für Virtualbox herunterladen
* Homeassistant OS in Virtualbox importieren
* Homeassistant OS starten

---

# Home Assitant - Was ist das?

* Open Source Software
* Heimautomatisierung

---

# Alternativen

* [ioBroker](https://www.iobroker.net)
* [FHEM](https://fhem.de)
* [openHAB](https://www.openhab.org)
* [Domoticz](https://www.domoticz.com)
* [Homey](https://homey.app)
* [HomeKit](https://www.apple.com/de/ios/home)
* [Homebridge](https://homebridge.io)
* Philips Hue

Keine 100% Deckung der jeweiligen Alternativen (z.B. Philips Hue steuert nur Lampen etc.)

---

# Motivation

* Warum Home Assistant?
  * Privatsphäre/Datenschutz
  * Offenheit
  * Flexibilität
  * Viele Geräte
  * Viele Protokolle
  * Viele Möglichkeiten
  * Open Source
  * Community


---

# Systemanforderungen - 1

* Raspberry Pi 3 oder 4 (Ab da "Macht es Spaß")
  * Es gibt fertige Hardware von Home Assistant (z.B. [Blue](https://www.home-assistant.io/blue), [Yellow](https://www.home-assistant.io/yellow/) und [Green](https://www.home-assistant.io/green/))
* Beim Installieren von aufwendigen Erweiterungen: x86 "Server" und >= 4GB RAM
* Für die Verwendung von Protokollen wie Zigbee, Z-Wave, EnOcean, 433MHz, 868MHz, 2,4GHz, 5GHz, Bluetooth, Infrarot, etc. werden zusätzliche Hardware benötigt

---

# Einschub: Zigbee - 1

* Zigbee ist ein Funkprotokoll
* Zigbee ist aber nicht WLAN - Funkt aber auf 2,4GHz
* Zigbee braucht ein Gateway
* Zigbee wird für viele Smart-Home Geräte verwendet
* Es gibt extrem viele (teilweise günstige) Geräte
  * Lampen (z.B. IKEA, Ledvance, Philips, etc.)
  * Schalter (z.B. Philips, IKEA)
  * Sensoren (z.B. Xiaomi, Aqara)
* Zigbee ist ein Mesh-Netzwerk
  * Jedes Gerät kann als Repeater dienen
  * Reichweite kann so erhöht werden
  * Geräte können so auch weiter entfernt vom Gateway sein

---

# Einschub: Zigbee - 2

* Stolpersteine bei Zigbee
  * Funkfrequenzen können überlaufen sein durch WLAN, Bluetooth, etc.
  * Funkfrequenzen müssen manchmal durchprobiert werden - welche gehen bei mir?
  * Manche Geräte sind nicht kompatibel mit allen Gateways
  * Viele Gateways sind nicht kompatibel mit allen Geräten
    * Alternative: Statt Gateway einen USB Stick verwenden, aber:
      * Selbst für Homeassitant gibt es veschiedene Integrationen
      * Integration mit Homeassistant aufwand (Meinung: Es lohnt sich aber)
      * Ohne Homeassistant schaltet dann nix mehr

---

# Systemanforderungen - 2

* Persönliche Empfehlung für "Zigbee":
  * Zigbee:
    * Home Assistant SkyConnect:
      * Einfachste Integration
      * Kann auch Matter
      * Integration mit *ZHA*
    * SONOFF Zigbee 3.0 USB Dongle Plus
      * Gute Antenne, guter Empfang (auch durch Wände)
      * Preiswert
      * Integration mit *Zigbee2MQTT*

---

# Installation in der Praxis

* Bei Raspberry Pi
  * [Raspberry Pi Imager](https://www.raspberrypi.org/software/)
  * Mit Image für Raspbery Pi flashen
* Für x86 Server:
  * [Homeassistant OS](https://www.home-assistant.io/installation/) folgen
  * Mit USB Stick installieren
* Für Promox Server
  * Installations Skript von [https://tteck.github.io/Proxmox/](https://tteck.github.io/Proxmox/)

---

# Installation - 1

* Schulung:
  * VirtualBox Image importieren
* Praxis:
  * Balana Etcher benutzen um Image zu flashen
    * Raspberry Pi: SD Karte
    * Andere Rechner: USB Stick

---

# Installation - 2

* Nach einiger Zeit erscheint ein Textfeld mit der URL (IP Adresse und Port)
* Diese URL in den Browser kopieren
* Falls die URL nicht funktioniert, kann auch die IP Adresse verwendet werden (Port nicht vergessen!)
* Alle weiteren Schritte dieser Schulung finden im Browser statt

---
layout: image
image: installed_cli.png
backgroundSize: contain

---

<v-click>
  <Arrow x1="800" y1="290" x2="460" y2="290" color="red" />
</v-click>

---

# Installation 3

* Wir klicken uns nun im Browser durch den Installationsprozess
* Der Ort ist dabei wichtig, da er für die Wettervorhersage benötigt wird
* Auch für Ortung von Geräten (z.B. Smartphones) ggf. wichtig
* Ob wir Statistiken teilen ist uns überlassen
* Ggf. werden bei der Installation schon Geräte gefunden
* Am Ende sehen wir eine Übersicht mit Wetter



---
layout: image
image: installation_01.png
backgroundSize: contain

---
---
layout: image
image: installation_02.png
backgroundSize: contain

---
---
layout: image
image: installation_03.png
backgroundSize: contain

---
---
layout: image
image: installation_04.png
backgroundSize: contain

---
---
layout: image
image: installation_05.png
backgroundSize: contain

---
---
layout: image
image: installation_06.png
backgroundSize: contain

---
---

# Installation 4

* Falls noch nicht geschehen: (USB) Geräte an den Rechner anschließen
* Bei Nutzung von Virtualbox können wir Geräte durchreichen (z.B. Zigbee USB Stick)

---

# Updates

* Home Assistant wird regelmäßig aktualisiert
* Updates können über die Weboberfläche eingespielt werden
* Updates werden sowohl für Home Assistant selbst als auch für die installierten Erweiterungen angezeigt
* Updates sollten regelmäßig eingespielt werden

---
layout: image
image: updates_01.png
backgroundSize: contain

---
<v-click>
  <Arrow x1="800" y1="290" x2="220" y2="400" color="red" />
</v-click>
---
layout: image
image: updates_02.png
backgroundSize: contain

---
<v-click>
  <Arrow x1="800" y1="290" x2="550" y2="380" color="red" />
</v-click>
---
layout: image
image: updates_03.png
backgroundSize: contain

---
---

# Devices / Geräte

* Geräte können über die Weboberfläche hinzugefügt und konfiguriert werden
* Geräte sind physikalische Geräte, wie z.B. eine Lampe, ein Router, ein Drucker, etc.
* Geräte können auch virtuell sein, wie z.B. ein Wetterbericht, ein Kalender, etc.
* Etliche Geräte werden von Home Assistant automatisch erkannt / gefunden
* Beispiel:

---

# Geräte hinzufügen

* Geräte können über die Weboberfläche hinzugefügt werden


---

# Addons

* Home Assistant kann durch Addons erweitert werden
* Addons sind Erweiterungen, die in Home Assistant laufen
* Addons können über die Weboberfläche installiert werden
* Addons können über die Weboberfläche konfiguriert werden, gestartet und gestoppt
* Beispiel: Editor "Visual Studio Code" als Addon


---
layout: image
image: addons_01.png
backgroundSize: contain
---
<v-click>
  <Arrow x1="800" y1="290" x2="220" y2="400" color="red" />
</v-click>
---
layout: image
image: addons_02.png
backgroundSize: contain
---
<v-click>
  <Arrow x1="800" y1="290" x2="800" y2="500" color="red" />
</v-click>
---
layout: image
image: addons_03.png
backgroundSize: contain
---
<v-click>
  <Arrow x1="800" y1="290" x2="500" y2="300" color="red" />
</v-click>
---
layout: image
image: addons_04.png
backgroundSize: contain
---
<v-click>
  <Arrow x1="800" y1="290" x2="400" y2="320" color="red" />
</v-click>
---
layout: image
image: addons_05.png
backgroundSize: contain
---
<v-click>
  <Arrow x1="800" y1="290" x2="400" y2="450" color="red" />
</v-click>
---
layout: image
image: addons_06.png
backgroundSize: contain
---
<v-click>
  <Arrow x1="800" y1="290" x2="850" y2="300" color="red" />
  <Arrow x1="800" y1="290" x2="850" y2="350" color="red" />
  <Arrow x1="800" y1="290" x2="850" y2="400" color="red" />
</v-click>
---
layout: image
image: addons_07.png
backgroundSize: contain
---
<v-click>
  <Arrow x1="800" y1="290" x2="750" y2="500" color="red" />
</v-click>
---
layout: image
image: addons_08.png
backgroundSize: contain
---
---

# Demo modus

* Damit wir einige Geräte zur verfügung haben, können wir den Demo Modus aktivieren
* Der Demo Modus ist nur für Testzwecke gedacht
* Der Demo modues muss über die datei `configuration.yaml` aktiviert werden
* Die Datei `configuration.yaml` ist die zentrale Konfigurationsdatei von Home Assistant
* Diese öffnen wir mit dem Visual Studio Code Addon
* Wir tragen folgendes in die Datei ZUSÄTZLICH ein:

```yaml
demo:
```

---

# Konfiguration - 1

* Manche Dinge können nur über die Konfigurationsdatei konfiguriert werden
* Viele Dinge können via grafischer Oberfläche konfiguriert werden, aber auch via Konfigurationsdatei
* Die Konfigurationsdatei ist eine YAML Datei
  * YAML ist ein Datenformat
  * YAML ist ein Textformat
  * YAML ist ein Format, das für Menschen gut lesbar ist
  * YAML muss immer korrekt eingerückt sein. Einrückungen sind wichtig!
  * Auch grafische Oberflächen schreiben YAML Dateien, diese sind aber oft nicht so gut lesbar
* Wir schauen durch alle Konfigurations-Optionen von Home Assistant

---
layout: image
image: settings.png
backgroundSize: contain
---
---

# Devices & Services - 1


* Integrations
  * Hier werden alle Integrationen angezeigt & konfiguriert
  * Es können weitere installiert werden, z.B. Wetterdienste, Hardware-Integrationen (Zigbee, Z-Wave, etc.)
* Devices
  * Hier werden alle einzelnen Geräte angezeigt
  * Beispiele: Lampen, Schalter, Sensoren, etc.

---

# Devices & Services - 2


* Entities:
  * Entities sind die einzelnen Funktionen eines Gerätes
  * Beispiele: Eine Lampe hat eine Entity für das Ein- und Ausschalten, eine Entity für die Helligkeit, etc.
* Helpers:
  * Helpers sind Hilfsfunktionen/Hilfsvariablen
  * Beispiele:
    * Zeitplan für das Ein- und Ausschalten einer Lampe
    * Virtuelle Schalter
    * Variablen: z.B. Letzte Uhrzeit, zu der ein Gerät eingeschaltet wurde
    * Hier gibt es viel Spielraum für eigene Ideen

---

# Automations & Scenes - 1

* Automations
  * Hier können Automatisierungen erstellt werden
  * Automatisierungen sind Regeln, die bestimmte Aktionen ausführen, wenn bestimmte Bedingungen erfüllt sind
  * Beispiel: Wenn es dunkel wird, dann schalte die Lampe ein
  * Automations können hochkomplex sein
* Scenes
  * Hier können Szenen erstellt werden
  * Szenen sind gespeicherte Zustände, z.B. Lichtstimmungen für Lampen im Wohnzimmer

---


# Automations & Scenes - 2

* Scripts:
  * Hier können Skripte erstellt werden
  * Eine oder mehrere nacheinander ausgeführte Serviceaufrufe
  * Skripte können auch über Automatisierungen ausgeführt werden
* Blueprints:
  * Hier können Blueprints erstellt werden
  * Blueprints sind Vorlagen für Automatisierungen
  * Blueprints können auch aus der Community installiert werden


---

# Areas & Zones - 1

* Areas
  * Hier können Areas erstellt und verwaltet werden
  * Eine *Area* enspricht i.d.R. einem Raum
  * Hier können alle Geräte eines Raumes zusammengefasst werden
  * Tipp: Schöne Bilder für die Areas verwenden
  * Nutzen: Geräte können so einfacher gefunden werden
* Zones:
  * Hier können Zonen erstellt und verwaltet werden
  * Eine Zone ist eine geografische Zone z.B. "Zuhause" oder "50 Meter um das Haus herum"
  * Hiermit können Automatisierungen erstellt werden, die auf die Zonen reagieren
    * Beispiel: Wenn ich nach Hause komme, dann schalte das Licht ein

---

# Dashboards

* Hier können Dashboards erstellt werden
  * Dashboards sind individuelle Ansichten
  * Dashboards können z.B. für Tablets oder Smartphones optimiert werden
  * Beispiele:
    * Ein Dashboard für das Wohnzimmer mit allen Geräten und Funktionen
    * Ein Mini-Dashboard, welches nur die wichtigsten Funktionen enthält
  * Tipp: Hier Zeit investieren, es lohnt sich!

---

# Automatisierung - 1

* Eine Automatisierung besteht aus
  * Trigger:
    * Der Auslöser für die Automatisierung
    * Beispiel: Ein Schalter wird betätigt, ein Gerät wird eingeschaltet, es wird dunkel, etc.
  * Condition (Optional):
    * Die Bedingung für die Automatisierung
    * Beispiel: Es ist nach 18 Uhr, es ist dunkel, es ist jemand zu Hause, etc.
  * Action:
    * Die Aktion, die ausgeführt wird, wenn der Trigger ausgelöst wurde und die Bedingung erfüllt ist
    * Beispiel: Eine Lampe wird eingeschaltet, eine Nachricht wird gesendet, etc.

---

# Automatisierung - 2

* Einfaches Beispiel:
  * Beschreibung: Um 18 Uhr soll die Küchen Lampe eingeschaltet werden
  * Trigger:
    * Zeit: 18 Uhr
  * Condition:
    * Nur, wenn die Sonne schon untergegangen ist
  * Action:
    * Schalte die Küchenlampe ein

---
layout: image
image: automation_01.png
backgroundSize: contain
---
---

# Automatisierung - 3

* Vorteil grafisches "Zusammenklicken":
  * Einfach zu verstehen
  * Sehr übersichtlich
  * Schnell erstellt
  * Fehler sind schnell gefunden
* Nachteil
  * Extrem schlecht zu teilen (Screenshot nachbauen?)
  * Komplexe Automatisierungen sind schwer zu erstellen und SEHR schwer zu editieren
* Lösung: Automatisierung in YAML anzeigen lassen

---

# Automatisierung - 4

* Automatisierung in YAML anzeigen lassen:
  * Im 3-Punkte Menü: "Edit in YAML"
  * Es kann nach dem Editieren wieder zurück gewechselt werden

Anzeige:

```yaml
alias: 18 Uhr -> Küchenlicht an
description: ""
trigger:
  - platform: time_pattern
    hours: "18"
    minutes: "0"
    seconds: "0"
condition:
  - condition: sun
    after: sunset
action:
  - type: turn_on
    device_id: 5814380796f1aa1b95c0b0583909eb9b
    entity_id: 70b4116985d4fca01651799789ce7200
    domain: light
mode: single

```
---

# Template Sensoren - 1

* Template Sensoren sind Sensoren, die aus anderen Sensoren errechnet werden
* Beispiele:
  * Ein Sensor, der die differenz zwischen zwei anderen Sensoren anzeigt (z.B. Soll- und Ist-Temperatur)
  * Ein Sensor, der die Temperatur von vor 1 Stunde, 1 Tag, 1 Woche, etc. anzeigt
* Template Sensoren werden in der `configuration.yaml` erstellt und konfiguriert

#TODO: EINFACHERES BEISPIEL
```yaml
# Template that shows, when the switch 'switch.ac' was turned on last time
- sensor:
  - unique_id: "ac_last_on"
    name: AC last on
    device_class: timestamp
    state: >
      {{ states('sensor.time') }}
    icon: mdi:clock


```


---

# Komplexe Automatisierung - 1

* Situation: Wie wollen ...
  * eine Benachrichtigung, wenn unsere Waschmaschine fertig ist
  * eine Abschätzung, wann die Waschmaschine fertig ist
* Probleme:
  * Unsere Waschmaschine gibt kein Signal ab / ist nicht "smart"
  * Wie wissen nicht wie lange ein Waschvorgang dauert
* Lösung:
  * Wir messen den Stromverbrauch der Waschmaschine und erkennen so ...
    * ... wenn die Waschmaschine gestartet wurde
    * ... wann die Waschmaschine fertig ist

---

# Komplexe Automatisierung - 2

* Voraussetzungen:
  * eine "Zwischensteckdose", die den Verbrauch grob misst (z.B. Shelly Plug S, NOUS A1Z, etc.)
  * Etliche Hilfsvariablen und Automatisierungen
  * Eine Template-Sensor, der den Endzeitpunkt eines Waschvorgangs errechnet
* Notwendige Beobachtungen:
  * Beobachtung: Wie viel Strom braucht die Waschmaschine im Betrieb?
  * Beobachtung: Wie viel Strom braucht die Waschmaschine im ausgeschalteten Zustand?
  * Wir betrachten nach einem Waschvorgang den Stromverbrauch über den Verbrauch hinweg

---

# Komplexe Automatisierung - 3

![Stromverbrauch](washing_machine.png)
* Anfangs sehr hoher Stromverbrauch
* Stromverbrauch sinkt nach einiger Zeit und bleibt bis auf Schleudervorgang niedrig

---

# Komplexe Automatisierung - 4

* Folgerungen:
  * Wenn der Stromverbrauch über einen längeren Zeitraum niedrig  ist, ist die Waschmaschine fertig
    * Hier: Ist der Verbrauch unter 1 Watt für 10 Minuten -> Waschmaschine ist AUS
  * Wenn der Stromverbrauch über einen längeren Zeitraum hoch ist, ist die Waschmaschine gestartet
    * Hier: Ist der Verbrauch über 10 Watt für 1 Minute -> Waschmaschine ist AN
  * Bedingungen, zum "Glätten":
    * Angehen:
      * Nur wenn der Strommesser 5 Minuten an war, kann die Waschmaschine angehen
      * Nur wenn die Waschmaschine aus war, kann sie angehen
    * Ausgehen:
      * Nur wenn die Waschmaschine an ist, kann sie ausgehen
      * Nur wenn die Waschmaschine 5 Minuten an war, kann sie ausgehen

---

# Komplexe Automatisierung - 5

* Was passiert beim Angehen:
  * Wir schreiben die aktuelle Uhrzeit/Datum in einen Helfer (Startzeit) `washing_machine_started`
  * Wir schicken eine Benachrichtigung, dass die Waschmaschine gestartet wurde
* Was passiert beim Ausgehen:
  * Wir schreiben die aktuelle Uhrzeit/Datum in einen Helfer (Endzeit)
  * Wir schicken eine Benachrichtigung, dass die Waschmaschine fertig ist
  * Wir berechnen die Dauer des Waschvorgangs (Endzeit - Startzeit) und schreiben diese in eine Helfer (Geschätzte Laufzeit) `washing_machine_estimated_runtime`

---

# Komplexe Automatisierung - 6

* Wie wissen wir aber, dass die Waschmaschien gerade läuft?
* Lösung:
  * Wir schreiben, eine Template-Variable, die dies uns errechnet
  * Diese ist wahr, wenn die Startzeit größer ist als die Endzeit (d.h. sie ist gestartet, aber nicht beendet)
  * Zudem zeigen wir zwei verschiedene Icons an, je nach Zustand
* In `config.yaml`:
```yaml
- binary_sensor:
  - unique_id: "washing_machine_is_running"
    name: Washing Machine is running
    state: >
      {{ state_attr('input_datetime.washing_machine_started','timestamp') >= state_attr('input_datetime.washing_machine_stopped','timestamp') }}
    icon: >
      {% if is_state("binary_sensor.washing_machine_is_running", "on") %}
        mdi:washing-machine
      {% else %}
        mdi:washing-machine-off
      {% endif %}
```

---

# Komplexe Automatisierung - 7

* Noch haben wir aber keine Info/Anzeige, wie lange ein laufender Waschvorgang geht
* Lösung: Template-Variable, die die aktuelle Startzeit + die geschätzte Laufzeit addiert
* In `config.yaml`:
```yaml
- sensor:
  - unique_id: "washing_machine_estimated_endtime"
    name: Washing machine estimated endtime
    device_class: timestamp
    state: >
      {% set starttime = states.input_datetime.washing_machine_started.state | as_timestamp %}
      {% set timediff = states.input_number.washing_machine_estimated_runtime.state | float %}
      {{ (starttime + timediff) | timestamp_local }}
```
---

# Komplexe Automatisierung - 8

* Achtung: Noch zeigt uns die Variable nur die geschätzte Endzeit an, diese kann auch in der Vergangenheit liegen.
* Lösung: Wir zeigen sie nur an, wenn die Waschmaschine gerade läuft (Template binary sensor, s.o.)

---

# TODO:

* Grafische und Textuelle Konfiguration
 * Unterschied zwischen grafischer und textueller Konfiguration
 * Einführung in die Home Assistant Lovelace UI
 * Grundlagen der textuellen Konfiguration mittels YAML
* Einbinden von Zigbee (als Beispiel)
 * Was ist Zigbee und warum ist es wichtig für die Heimautomatisierung?
 * Integration von Zigbee-Geräten in Home Assistant
 * Best Practices und Troubleshooting
* Automatisierungen: Das “smart” in Smart-Home
 * Grundlagen der Automatisierung
 * Erstellen von einfachen bis komplexen Automatisierungsregeln
 * Szenarien, Auslöser, Bedingungen und Aktionen
* Weitere Datenquellen und Dienste
 * Am Rande: Einbindung externer Datenquellen wie Wetterdienste, Kalender und mehr
 * Verknüpfen und Darstellen dieser Daten in Home Assistant
* Updates und Backups
 * Wichtige Aspekte von Systemupdates
 * Erstellen und Wiederherstellen von Backups
* Fragen, Fragen, Fragen
 * Offene Diskussion und Fragerunde
 *
# Abschluss

[Diese Schulung](https://github.com/derphilipp/schulung_homeassistnat) · [Schulung ansehen](https://derphilipp.github.io/schulung_homeassistant) · [Kontakt](https://philipp-weissmann.de)
