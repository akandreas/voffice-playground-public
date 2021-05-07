# voffice-playground-public

# Übung 1: Mit PowerShell CSV-Dateien filtern

## Aufgabe 1: Projekt auschecken und Branch erstellen
Hol Dir zunächst eine lokale Kopie dieses Git-Repositories und erzeuge einen eigenen Branch. Die dazu erforderlichen Git-Befehle (`checkout` und `branch`) findest Du im [Git Cheat Sheet](https://training.github.com/downloads/de/github-git-cheat-sheet/).
Das Repository ist öffentlich erreichbar unter:
* https://github.com/akandreas/voffice-playground-public.git

Öffne den Ordner und die darin enthaltene CSV-Datei in Deinem Editor, zum Beipsiel in [Visual Studio Code](https://code.visualstudio.com/Download).

## Aufgabe 2: CSV-Datei auslesen und auf relevante Spalten einschränken

Such in der [PowerShell 101](https://docs.microsoft.com/en-us/powershell/scripting/learn/ps101/00-introduction?view=powershell-7.1) Doku nach dem CmdLet `Import-Csv` oder lass Dir den eingebauten Hilfetext wie folgt ausgeben:
```
Get-Help Import-Csv
```
Reduziere den Inhalt der CSV-Datei auf die Spalten _Firma_, _Asset Tag_, _Modell_, _Modellnr._ und _Kategorie und lass Dir das Ergebnis ausgeben, zum Beispiel:
```
$data = Import-Csv ./custom-assets-report-public.csv
$columns = ($data | select Firma, ... )
echo $columns
```
