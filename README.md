# FYMT_PiedPiperS_CampusWoche

Sofware environment used: 

MS Visual Studio Code 1.134.0
+ C/C++ Extension Pack (including C/C++ extension, CMake Tools)
+ PlatformIO IDE extension
+ a number of libraries included in the platformio.ini and the PiedPiperS.cpp code, which will be loaded automatically when compiling
+ one manual amendment in the SPIFFSIniFile.h library: add in file SPIFFSIniFile.h following line: #include "SPIFFS.h" //manually added in order to prevent error: 'SPIFFS' was not declared in this scope
  
  Path in VSCode Explorer > PiedPiperS > .pio > libdeps > ESP32C3_SuperMini > SPIFFSIniFile > src > SPIFFSIniFile.h


See further Project detail, explainations and some photos in the \docs folder.

In the \data folder, you can adjust the lok.png photo. It should have an extension of 300 pixels width 100 pixels height and about and not much more than 60 KB. Reduce the resolution of the photo accordingly or increase the compressen, e.g. using IrfanView app.

In the \data folder, you can edit the lok.ini text file and set the basic variables for the start of the PiedPiperS code: 
  Loco name, 
  wifi-name/SSID, 
  password, 
  Motor supply volatage
  
See further detail in the \docs\ReadMe_lok_ini.md. Assure, that all lines in the lok.ini file stay within a maximum of 40 characters line length, so that the software can process it. 

The installation of the PiedPiperS software at the ESP32-C3-zero microprocessor flash memory requires using the PlatformIO extension as follows: 
1. Build Filesystem Image of the content in the \data folder using the PlatformIO extension 
   PlatformIO>Projekt Tasks>ESP32C3_SuperMini>Platform>Build Filesystem Image
2. Upload Filesystem Image via COM port at the USB connected to the ESP32-C3-zero
   PlatformIO>Projekt Tasks>ESP32C3_SuperMini>Platform>Upload Filesystem Image
3. Builde/compile PiedPiperS.cpp code
   PlatformIO>Projekt Tasks>ESP32C3_SuperMini>General>Build
4. Uploade compiled PiedPiperS.cpp code
   PlatformIO>Projekt Tasks>ESP32C3_SuperMini>General>Upload 
   This is automatically building the code again before the upload.
