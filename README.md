# IKEA-Feinstaubsensor Vindrikning mit ESP32 per Bluetooth auf Smartphone anzeigen

IKEA bietet den Feistaubsensor VINDRIKTNING an
[IKEA vindriktning](https://www.ikea.com/de/de/p/vindriktning-luftqualitaetssensor-70498242/)

Der Sensor misst den Feinstaub in der Luft und zeigt die Konzentration mit einer dreifarbigen LED Leiste an.  

Eine Beschreibung des Ikea Sensors, sowie die Idee, die Messdaten vom Ikea-Sensor abzugreifen und auf einem Mobiltelefon darzustellen finden sich im Beitrag von [heise](https://www.heise.de/ratgeber/Ikea-Feinstaubsensor-Vindriktning-zum-IoT-Device-aufbohren-6164149.html)

---

## Konzept

Der IKEA Vindrikting Sensor wird geöffnet. Es werden drei Drähte angelötet für Versorgungsspannung, Ground und das serielle Signal aus dem Sensor. Das Serielle Signal aus dem Sensor (5 Volt) wird per Spannungsteiler an den ESP32 Eingang (verträgt nur 3.3 Volt) angepasst.

Der ESP32 empfängt die Daten des Sensors über seine serielle UART Schnittstelle. Der ESP32 interpretiert den Datenstrom und extrahiert daraus den Messwert.

Der ESP32 sendet den Messwert als Zahl per Bluetooth an das Handy.

Es gibt zwei Möglichkeiten, die Messwerte auf dem Handy darzustellen:  
**Serial Bluetooth Terminal** aus dem Play Store zeigt Zahlenwerte  
**IKEA Vindriktning Monitor** zeigt die Messwerte in einer einfachen Grafik

---

## Hardware

Der IKEA Sensor wird an die Serielle Schnittstelle des ESP32 angeschlossen.  
So geht's: link  

---

## ESP32 Software

Die Arduino basierte Software für den ESP32 findet sich unter [ESP32 Arduino](https://github.com/PeterDirnhofer/IKEA-vintrikning-ESP32-Bluetooth/blob/main/IKEA_ESP32.ino)

---

## Handy Software: Serial Bluetooth Terminal

Die App kann aus dem Google Play Store geladen werden. Suche nach "serial bluetooth terminal"

---

## Handy Software: IKEA Vindriktning Monitor auf das Handy laden

Die App herunterladen von [ESP32BluetoothApp.apk](https://github.com/PeterDirnhofer/IKEA-vintrikning-ESP32-Bluetooth/blob/main/ESP32BluetoothApp.apk) und auf dem Handy installieren.


## Handy Software: IKEA Vindriktning Monitor mit MIT APP Inventor bearbeiten

Es gibt aber auch die Möglichkeit, die App mit dem **MIT App Inventor** zu bearbeiten und an die eigenen Vorstellungen anzupassen.

Eine schöne Einführung in den **MIT App Inventor** gibt es unter [Youtube App Inventor Tutorial
](https://youtu.be/aM2ktMKAunw)  
Die App als mit dem **MIT App Inventor** bearbeitbare **aia** Datei liegt auf [ESP32BluetoothApp.
aia](https://github.com/PeterDirnhofer/IKEA-vintrikning-ESP32-Bluetooth/blob/main/ESP32BluetoothApp.aia)

