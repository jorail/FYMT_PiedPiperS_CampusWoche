**PiedPiperS code auf ESP32 C3 zero**

**Verwendete Softwareumgebung:**

• MS Visual Studio Code 1.134.0

• C/C++ Extension Pack (einschließlich C/C++-Erweiterung, CMake-Tools)

• PlatformIO-IDE-Erweiterung

• eine Reihe von Bibliotheken, die in der Datei „platformio.ini“ und im Code „PiedPiperS.cpp“ als #include enthalten sind und beim Kompilieren automatisch geladen werden

• eine manuelle Änderung in der Bibliothek „SPIFFSIniFile.h“:
  
  Pfad im VSCode Explorer \PiedPiperS\.pio\libdeps\ESP32C3_SuperMini\SPIFFSIniFile\src\SPIFFSIniFile.h
  
  Füge in der Datei „SPIFFSIniFile.h“ anfänglich folgende Zeile ein:
  
  #include "SPIFFS.h" //manuell hinzugefügt, um den Fehler "SPIFFS" wurde in diesem Geltungsbereich nicht deklariert zu vermeiden

**Installation der PiedPiperS-Software im FlashSpeicher des ESP32-C3-Zero-Mikroprozessors durch Nutzung der PlatformIO-Erweiterung:**

1. Erstelle das Dateisystem-Image des Inhalts im Ordner \data mithilfe der PlatformIO-Erweiterung:
    PlatformIO > Projekt-Aufgaben > ESP32C3_SuperMini > Plattform > Dateisystem-Image erstellen

2. Lade das Dateisystem-Image über den COM-Port der angeschlossenen USB-Verbindung zum ESP32-C3-Zero hoch:
    PlatformIO > Projekt-Aufgaben > ESP32C3_SuperMini > Plattform > Dateisystem-Image hochladen

3. Erstelle/kompiliere den Code „PiedPiperS.cpp“:
    PlatformIO > Projekt-Aufgaben > ESP32C3_SuperMini > Allgemein > Erstellen

4. Kompilierten PiedPiperS.cpp-Code hochladen:
    PlatformIO > Projekt-Aufgaben > ESP32C3_SuperMini > Allgemein > Hochladen.
    Dabei wird der Code vor dem Hochladen automatisch erneut kompiliert.

**Weitere Projektdetails, Erläuterungen und einige Fotos im Ordner \docs.**

