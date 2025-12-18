# RTL-basierte CPU-Entwicklung (VHDL)

Dieses Repository enthält das Design und die Implementierung eines Prozessors auf Register-Transfer-Ebene (RTL). [cite_start]Das Projekt wurde mit der **Vivado Design Suite v2019.1** erstellt [cite: 1, 2] [cite_start]und zielt auf einen **Xilinx Artix-7 FPGA** (`xc7a100tcsg324-1`) ab[cite: 2, 21].

## 🚀 System-Architektur
Das Design folgt einer modularen Architektur, die eine vollständige Befehlsabwicklung ermöglicht. [cite_start]Der Fokus liegt auf einem sauberen Datenfluss und der Trennung von Steuer- und Rechenlogik[cite: 14, 15].

### Kern-Komponenten:
* [cite_start]**ALU (Arithmetic Logic Unit):** Realisiert in `ALU.vhd`, unterstützt Operationen wie Addition (`Add.vhd`), logische Verknüpfungen (`Logic.vhd`, `AND.vhd`, `OR.vhd`, `XOR.vhd`), Schiebeoperationen (`Shift.vhd`) und Vergleiche (`Cmp.vhd`)[cite: 7, 8, 9, 10, 13, 14].
* [cite_start]**Control Unit:** Die Datei `Control.vhd` übernimmt die zentrale Steuerung des Prozessors[cite: 10, 11].
* [cite_start]**Register File (RF):** Implementiert in `RF.vhd` zur effizienten Verwaltung der internen Operanden[cite: 12].
* [cite_start]**DataPath:** In `DataPath.vhd` werden alle Komponenten (einschließlich MUX-Strukturen und Befehlsdekoder) zu einem funktionalen Prozessor zusammengeführt[cite: 6, 11, 14].
* [cite_start]**Program Counter Control:** Die Komponente `PcCtrl.vhd` steuert den Programmablauf und die Adressierung[cite: 12, 13].

## 🛠 Technische Details & Tools
* [cite_start]**Sprache:** VHDL unter Verwendung spezialisierter Packages (`DefsPkg.vhd`, `CompsPkg.vhd`, `AuxFuncPkg.vhd`)[cite: 5, 6, 8].
* [cite_start]**Entwicklungs-Software:** Xilinx Vivado v2019.1[cite: 1].
* [cite_start]**Target Hardware:** Xilinx Artix-7 FPGA[cite: 2].
* [cite_start]**Top-Level-Module:** Das Hauptmodul der Synthese ist als `CPU` definiert[cite: 15].

## 📁 Repository-Struktur
[cite_start]Basierend auf der vorliegenden Projektkonfiguration[cite: 15, 19]:
* [cite_start]`/sources_1`: Enthält die RTL-Design-Files (CPU, ALU, Control, etc.) [cite: 5-14].
* [cite_start]`/sim_1`: Enthält die Simulationsumgebung inklusive der Testbench `TBE.vhd`, einem Clock-Generator `ClkGen.vhd` und Speicher-Modellen `MEM.vhd`[cite: 16, 17, 18].
* [cite_start]`/constrs_1`: Ordner für XDC-Dateien zur physikalischen Pin-Belegung[cite: 15].

## 📊 Verifizierung & Simulation
[cite_start]Die Funktionalität wurde intensiv im **Vivado Simulator (XSim)** geprüft[cite: 20].
* [cite_start]**Testbench:** Die Datei `TBE.vhd` dient als Top-Level für alle Simulationen[cite: 18, 19].
* [cite_start]**Waveform-Konfiguration:** Mit der Datei `TBE_behav.wcfg` können die Signalverläufe direkt analysiert werden[cite: 18, 19].
* [cite_start]**Simulations-Intensität:** Das Projekt weist eine aktive Simulationshistorie mit über 445 Starts auf[cite: 3].

---
**Kontakt:** [artin Asokhuo] – [martinasokhuo1@gmail.com]

