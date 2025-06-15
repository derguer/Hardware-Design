# 🌿 Intelligenter Pflanzenwächter – Hardware Design Projekt

Ein Microcontroller-basiertes System zur automatischen Überwachung und Bewässerung von Pflanzen. Entwickelt im Rahmen des Moduls **Hardware Design**.

---

## 📷 Projektübersicht

![Systemübersicht](images/system_overview.jpg)

Der Pflanzenwächter misst Bodenfeuchtigkeit, Temperatur und Lichtintensität. Über ein Relaismodul wird eine Wasserpumpe angesteuert, wenn die Bodenfeuchte unter einen Schwellenwert fällt.

---

## 🛠️ Hardware-Komponenten

| Bauteil                | Beschreibung                        |
|------------------------|-------------------------------------|
| Mikrocontroller        | ESP32                                |
| Bodenfeuchtesensor     | Kapazitiv                             |
| Temperatursensor       | DHT22                                |
| Pumpe + Relaismodul    | 5V Mini-Pumpe + 1-Kanal Relais       |
| Versorgung             | 5V via USB oder Akku                 |
| Platine                | Eigenes PCB, mit KiCad designt      |

---

## 🔧 Schaltung & PCB Design

### Schaltplan
![Schaltplan](images/schematic.png)

### PCB Layout
![PCB Layout](images/pcb_layout.png)

Die Platine wurde in **Autodesk Fusion** erstellt und über JLCPCB gefertigt. Alle Gerber-Files sind im Ordner `hardware/gerber/` verfügbar.

---

## 🧪 Funktionsweise

1. Sensor misst Feuchtigkeit
2. Wenn unter Schwelle → ESP32 aktiviert Pumpe
3. LED zeigt Systemstatus (rot/grün)
4. Daten werden per UART gesendet (optional für Debugging)

---

## 📂 Projektstruktur

```bash
📁 hardware/
 ├── schematic.kicad_sch
 ├── pcb.kicad_pcb
 ├── gerber/
📁 images/
 ├── schematic.png
 ├── pcb_layout.png
 ├── system_overview.jpg
📁 firmware/
 ├── main.ino
README.md
