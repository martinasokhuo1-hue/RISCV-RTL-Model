# RTL-basierte CPU-Entwicklung (VHDL)

Dieses Repository enthält das Design und die Implementierung eines Prozessors auf Register-Transfer-Ebene (RTL). Das Projekt wurde mit der **Vivado Design Suite v2019.1** erstellt und zielt auf einen **Xilinx Artix-7 FPGA** (`xc7a100tcsg324-1`).

## 🚀 System-Architektur
Das Design folgt einer modularen Architektur, die eine vollständige Befehlsabwicklung ermöglicht. [cite_start]Der Fokus liegt auf einem sauberen Datenfluss und der Trennung von Steuer- und Rechenlogik.

### Kern-Komponenten:
* **ALU (Arithmetic Logic Unit):** Realisiert in `ALU.vhd`, unterstützt Operationen wie Addition (`Add.vhd`), logische Verknüpfungen (`Logic.vhd`, `AND.vhd`, `OR.vhd`, `XOR.vhd`), Schiebeoperationen (`Shift.vhd`) und Vergleiche (`Cmp.vhd`).
* **Control Unit:** Die Datei `Control.vhd` übernimmt die zentrale Steuerung des Prozessors.
* **Register File (RF):** Implementiert in `RF.vhd` zur effizienten Verwaltung der internen Operanden.
* **DataPath:** In `DataPath.vhd` werden alle Komponenten (einschließlich MUX-Strukturen und Befehlsdekoder) zu einem funktionalen Prozessor zusammengeführt.
* **Program Counter Control:** Die Komponente `PcCtrl.vhd` steuert den Programmablauf und die Adressierung.

## 🛠 Technische Details & Tools
* **Sprache:** VHDL unter Verwendung spezialisierter Packages (`DefsPkg.vhd`, `CompsPkg.vhd`, `AuxFuncPkg.vhd`).
* **Entwicklungs-Software:** Xilinx Vivado v2019.1.
* **Target Hardware:** Xilinx Artix-7 FPGA.
* **Top-Level-Module:** Das Hauptmodul der Synthese ist als `CPU` definiert.

## 📁 Repository-Struktur
Basierend auf der vorliegenden Projektkonfiguration:
* `/sources_1`: Enthält die RTL-Design-Files (CPU, ALU, Control, etc.).
* `/sim_1`: Enthält die Simulationsumgebung inklusive der Testbench `TBE.vhd`, einem Clock-Generator `ClkGen.vhd` und Speicher-Modellen `MEM.vhd`.
* `/constrs_1`: Ordner für XDC-Dateien zur physikalischen Pin-Belegung.

## 📊 Verifizierung & Simulation
Die Funktionalität wurde intensiv im **Vivado Simulator (XSim)** geprüft.
* **Testbench:** Die Datei `TBE.vhd` dient als Top-Level für alle Simulationen.
* **Waveform-Konfiguration:** Mit der Datei `TBE_behav.wcfg` können die Signalverläufe direkt analysiert werden.
* **Simulations-Intensität:** Das Projekt weist eine aktive Simulationshistorie mit über 445 Starts auf.

## 📈 Visualisierung & Ergebnisse

### RTL-Struktur (Schematic)
Hier ist die aus Vivado generierte Hardware-Struktur der CPU zu sehen. Man erkennt deutlich die Trennung zwischen dem Datenpfad und der Control-Unit.
![RTL Schematic](imag structure/rtl_schematic.png)

### Simulations-Ergebnisse
Die Testbench `TBE.vhd` verifiziert die korrekte Ausführung der Befehlssätze.
![Simulation Waveform](imag_waveform/simulation_waveform.png)

---
**Kontakt:** [Martin Asokhuo] – [martinasokhuo1@gmail.com]

