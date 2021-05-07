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

## Aufgabe 3: Zeilen filtern und exportieren
Nutze das Schlüsselwort `where` um die Liste nach Laptops zu filtern.
```
$laptops = ($columns | where { $_.Kategorie -EQ "Laptop" } )
echo "Gefundene Laptops: " $laptops.count
```
Sortiere die so erstellte Liste nach der Spalte Modell. Lies Dir ggf. die Doku für das CmdLet `Sort-Object` durch.
```
$sorted = ($laptops | Sort-Object -Property ...)
```
Mit dem CmdLet `Export-Csv` kannst Du dann die erzeugte Liste wieder exportieren. Erstelle bitte jeweils eine sortierte Tabellle für Laptops und Smartphones.

## Aufgabe 4: Shell-Skript im main-Branch bereitstellen
Wirf nochmal einen Blick in das [Git Cheat Sheet](https://training.github.com/downloads/de/github-git-cheat-sheet/) und pushe zunächst Deine Änderungen in Deinen eigenen Branch und dann merge Deine Änderungen mit dem Remote main Branch.
