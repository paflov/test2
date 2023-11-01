# Beispieldaten Testcenter-output

Alle Daten kommen von einer kürzlichen Präpilotierung Französisch VERA8. Ich habe von martin die Erlaubnis,
die euch weiterzugeben. Wenn ihr dazugehörigen Units und Testhefte angucken wollt, müssten wir uns 
zusätzlich von Maike Wäckerle als verantwortliche Koordinatorin das OK holen.

# Antwortdaten

Antwortdaten können vom Testcenter über den Admin-Bereich heruntergeladen werden, oder von einer anderen
Anwendung wie der ITC-Toolbox (oder dereinst eatprep2) über die Api-Schnittstelle vom Testcenter geladen
werden ([Doku API](https://pages.cms.hu-berlin.de/iqb/testcenter/dist/api/index.html#tag/admin-download/paths/~1workspace~1{ws_id}~1report~1response/get)).  

## Datei: frzverapp2022_output-responses.csv

- Direkte Datenausgabe der **Antwort**daten aus dem Testcenter als CSV-Tabelle
- Alle Testgruppen

Zeilen:
* Eine Zeile ist eine bearbeitete Unit in einem gelaufenen Testheft eines Teilnehmers 

Erklärung der Spalten:
* Gruppenname - Testgruppen-Id
* loginname - Loginname
* code - bei verschiedenen Login-Modi kann ein login für mehrere Teilnehmer verwendet werden, dann werden 
diese durch den Wert in "code" unterschieden.
* bookletname - ID des booklets
* unitname - ID der unit
* reponses - Die eigentlichen Antwortdaten (siehe unten, Antwortdatenformat)
* laststate - JSON-Objekt-letzter Zustand des Tests

## Datei: frzverapp2022_output-responses-2_Testgruppen.json

- Direkte Datenausgabe aus dem Testcenter als CSV-Tabelle
- Nur zwei Testgruppen als Beispiel ausgewählt

Das ist dasselbe, nur als JSON-Objekt. Dieses dürfte in jedem Kontext - außer händisch mit Excel - 
besser zu verarbeiten sein.

## Datei: frzverapp2022_toolbox-output

Die ITC-Toolbox ruft selbsttätig diese Daten ab und verschneidet sie. 
Das Ergebnis ist in dieser Datei zu finden.
* Dokumentation Ausgabe ITC-Toolbox: https://github.com/iqb-berlin/itc-toolbox/blob/master/docs/manual-output.md
* ITC-Toolbox Herunterladen https://www.iqb.hu-berlin.de/institut/ab/it/itc-ToolBox

# Logdaten

Funktioniert analog zu den Antwortdaten ([Doku API](https://pages.cms.hu-berlin.de/iqb/testcenter/dist/api/index.html#tag/admin-download/paths/~1workspace~1{ws_id}~1report~1log/get
)).

## Datei: frzverapp2022_output-logs-2_Testgruppen

- Direkte Datenausgabe der **Log**daten aus dem Testcenter als CSV-Tabelle
- Nur zwei Testgruppen als Beispiel ausgewählt

Die meisten Logeinträge kommen durch Änderungen des Test-Status zu stande und dürften selbsterklären sein.

# Anwortdatenformat

Aus Sicht des Testcenters sind können die Antwortdaten ein beliebiges Format haben. Der Gedanken dahinter ist, 
dass andere eventuell Player mit ganz anderen Formaten entwickeln wollen. Unsere Player liefern allerdings
(fast) alle das gleiche, das IQB-Standard-Format: 
- Dokumentation IQB-Standard 1.0: https://github.com/iqb-berlin/verona-data-specifications/blob/main/responses/manual_iqb-standard.md
- Geplante Erweiterung 1.1: https://github.com/iqb-berlin/verona-player-abi/wiki/IQB-Standardformat-f%C3%BCr-Antworten 


