# Python lernen

Sie haben den [barrierefreien eLearning-Python-Kurs](https://www.bfwonline.de/indexmobile/showCourse/CourseId/20257) für blinde und sehbehinderte Nutzerinnen und Nutzer des [BFW Würzburg](https://www.bfw-wuerzburg.de) absolviert und erfolgreich die Grundlagen der Programmiersprache Python erlernt.

Nachfolgend finden Sie einige ergänzende Informationen, die Ihnen beim weiteren Arbeiten mit Python hilfreich sein könnten:

## Pfad zur aktuellen `.py`-Datei ermitteln

Die folgende Python-Funktion gibt den Pfad zur aktuell ausgeführten `.py`-Datei zurück:

```python
import os

def aktueller_dateipfad():
	"""
	Gibt den absoluten Pfad der aktuell ausgeführten Python-Datei zurück.
	Returns:
		str: Absoluter Pfad der Datei.
	"""
	return os.path.dirname(os.path.abspath(__file__))

# Beispielaufruf
print(aktueller_dateipfad())
```

### Erläuterung:
1. **import os** – Importiert das `os`-Modul, das Funktionen zur Interaktion mit dem Betriebssystem bereitstellt.
2. **def aktueller_dateipfad():** – Definiert die Funktion zur Ermittlung des Dateipfads.
3. **Dokstrings (`""" ... """`)** – Beschreiben die Funktion und deren Rückgabewert.
4. **`__file__`** – Eine spezielle Variable, die den relativen Pfad der ausgeführten Datei enthält. `os.path.abspath(__file__)` wandelt diesen in einen absoluten Pfad um.
5. **Beispielaufruf** – Gibt den Pfad aus, wenn die Datei ausgeführt wird.

## Konsolenbildschirm unter Windows löschen

Der folgende Python-Code löscht den Bildschirm eines Konsolenfensters unter Windows:

```python
import os

def clear_screen():
	""" Löscht den Bildschirm des Konsolenfensters unter Windows. """
	os.system("cls")

# Beispielaufruf
clear_screen()
```

> Hinweis: Der Befehl `cls` funktioniert ausschließlich in der Windows-Eingabeaufforderung und ist nicht mit anderen Betriebssystemen kompatibel.

## `.py`-Datei in eine `.exe`-Datei umwandeln

Im Folgenden finden Sie eine Schritt-für-Schritt-Anleitung, wie Sie mit PyInstaller Ihre Python-Datei in eine ausführbare `.exe`-Datei konvertieren:

### Schritt 1: PyInstaller installieren

Falls PyInstaller noch nicht installiert ist, führen Sie folgenden Befehl aus:

```bash
pip install pyinstaller
```

### Schritt 2: In das Verzeichnis der `.py`-Datei wechseln

Navigieren Sie über die Eingabeaufforderung (`cmd`) in das Verzeichnis Ihrer Python-Datei:

```bash
cd Pfad/zur/Datei
```

### Schritt 3: `.exe`-Datei erstellen

Führen Sie folgenden Befehl aus, um Ihre Datei in eine `.exe` umzuwandeln:

```bash
pyinstaller --onefile ihr_script.py
```

> **--onefile** erstellt eine einzelne `.exe`-Datei anstelle mehrerer Dateien und Ordner.

Falls Sie eine `.exe` mit grafischer Oberfläche (ohne Konsolenfenster) benötigen, verwenden Sie stattdessen:

```bash
pyinstaller --onefile --windowed ihr_script.py
```

### Schritt 4: `.exe`-Datei finden

Die erstellte Datei befindet sich im Ordner **dist/** innerhalb Ihres Projektverzeichnisses.

### Schritt 5: `.exe`-Datei testen

Wechseln Sie in den **dist/**-Ordner und führen Sie die `.exe`-Datei aus, um sie zu testen.