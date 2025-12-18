# RTL-basierte CPU Entwicklung (VHDL)

Dieses Repository enthält das Design und die Implementierung eines Prozessors auf Register-Transfer-Level (RTL). [cite_start]Das Projekt wurde mit der **Vivado Design Suite v2019.1** erstellt und zielt auf einen **Xilinx Artix-7 FPGA** (`xc7a100tcsg324-1`).

## 🚀 System-Architektur
Das Design folgt einer modularen Architektur, die eine vollständige Befehlsabwicklung ermöglicht. Der Fokus liegt auf einem sauberen Datenfluss und der Trennung von Steuer- und Rechenlogik.

### Kern-Komponenten:
**ALU (Arithmetic Logic Unit):** Realisiert in `ALU.vhd`, unterstützt Operationen wie Addition (`Add.vhd`), logische Verknüpfungen (`Logic.vhd`), Schiebeoperationen (`Shift.vhd`) und Vergleiche (`Cmp.vhd`)[cite: 7, 8, 9, 10].
**Control Unit:** Die Datei `Control.vhd` übernimmt die zentrale Steuerung des Prozessors[cite: 10].
**Register File (RF):** Implementiert in `RF.vhd` zur effizienten Verwaltung der internen Operanden[cite: 12].
**DataPath:** In `DataPath.vhd` werden alle Komponenten (einschließlich MUX-Strukturen und Befehlsdekoder) zu einem funktionalen Prozessor zusammengeführt[cite: 6, 12, 14].
**Program Counter Control:** Die Komponente `PcCtrl.vhd` steuert den Programmablauf und die Adressierung[cite: 12].

## 🛠 Technische Details & Tools
**Sprache:** VHDL (unter Verwendung von Packages wie `DefsPkg.vhd` und `CompsPkg.vhd` für globale Definitionen).
**Entwicklungs-Software:** Xilinx Vivado v2019.1.
**Target Hardware:** Xilinx Artix-7 FPGA.
**Top-Level-Module:** Das Hauptmodul ist als `CPU` definiert.

## 📁 Repository-Struktur
Basierend auf der vorliegenden Projektkonfiguration:
 `/sources_1`: Enthält die RTL-Design-Files (CPU, ALU, Control, etc.).
 `/sim_1`: Enthält die Simulationsumgebung inklusive der Testbench `TBE.vhd`, einem Clock-Generator `ClkGen.vhd` und Speicher-Modellen `MEM.vhd`.
 `/constraints`: (XDC-Dateien) Für die physikalische Pin-Belegung auf dem FPGA-Board.

## 📊 Verifizierung & Simulation
Die Funktionalität wurde intensiv im **Vivado Simulator (XSim)** geprüft.
**Testbench:** Die Datei `TBE.vhd` dient als Top-Level für alle Simulationen.
**Waveform-Konfiguration:** Mit der Datei `TBE_behav.wcfg` können die Signalverläufe direkt analysiert werden.
**Simulations-Historie:** Das Projekt weist über 445 durchgeführte Simulationsläufe auf, was eine hohe Testabdeckung belegt.

---
**Kontakt:** [Martin Asokhuo] – [martinasokhuo1@gmail.com]
