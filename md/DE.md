# Handlebars-Vorlagen-Projekt

Dieses Projekt bietet ein einfaches Setup-Beispiel, das Handlebars-Dateien mit dem File Tracker unter Verwendung von Handlebars-Vorlagen in HTML konvertiert und öffentliche Assets in ein Ausgabeverzeichnis kopiert. Das Projekt bietet auch die Möglichkeit, das Ausgabeverzeichnis regelmäßig zu bereinigen und neu zu erstellen.

## Merkmale

- Konvertiert Handlebars-Vorlagen in HTML.
- Kopiert generische Assets (CSS, JS, Bilder, etc.) in das Ausgabeverzeichnis.
- Überwacht Änderungen im Quellverzeichnis und aktualisiert das Ausgabeverzeichnis entsprechend.
- Säubert das Ausgabeverzeichnis regelmäßig und baut es neu auf.

## Installation

1. Klonen Sie das Repository:

   ```bash
   git clone https://github.com/Eren-Seyfi/vanilla-Handlebars-generate.git
   cd Handlebars-template-project
   ```

2) installieren Sie die Abhängigkeiten:

   ```bash
   npm install
   ```

3) starten Sie das Projekt:

   ```bash
   npm start
   ```

## Struktur

- **src**: Ressourcenverzeichnis mit Handlebars-Vorlagen und öffentlichen Assets.
  - **templates**: Enthält `layouts`, `partials`, `components` und `pages`.
  - **public**: Enthält öffentliche Assets wie CSS- und JS-Dateien.
- **www**: Ausgabeverzeichnis, in dem konvertiertes HTML und kopierte Assets gespeichert werden.
- **bootstrap.js**: Hauptskript zum Einrichten des Projekts, Verfolgen von Änderungen und Konvertieren von Vorlagen.
- **structure.json**: Konfigurationsdatei, die die Struktur und die Einstellungen definiert.

## Wie Layouts funktionieren:

In diesem Projekt sind die Handlebars-Vorlagen in Layouts unterteilt, um eine modulare Struktur zu schaffen. Die Layout-Dateien befinden sich im Verzeichnis templates/layouts. Jede Handlebars-Datei einer Seite gibt an, zu welcher Layout-Datei sie gehört, indem sie den Layout-Namen im Dateinamen angibt, z. B. index.main.Handlebars bedeutet, dass das Layout main.Handlebars verwendet wird.

Wenn Vorlagen gerendert werden, wird die Layout-Datei verwendet, um den Seiteninhalt zu umhüllen. Dadurch wird sichergestellt, dass die Kopf- und Fußzeilen sowie die Navigationsabschnitte auf den verschiedenen Seiten konsistent sind. Zum Beispiel wird eine index.main.Handlebars-Datei mit dem main.Handlebars-Layout umhüllt, und die gleiche Kopf- und Fußzeile wird für alle Seiten verwendet, die dieses Layout verwenden.

## Konfiguration

### structure.json

```json
{
  "inputDir": "src",
  "outputDir": "www",
  "interval": 5000,
  "mainTemplate": "templates/layouts/main.hbs",
  "pagesDir": "templates/pages",
  "templates": {
    "layouts": ["main.hbs", "example.hbs"],
    "partials": ["header.hbs", "footer.hbs", "nav.hbs"],
    "pages": [
      "index.main.hbs",
      "about.main.hbs",
      "index.example.hbs",
      "about.example.hbs"
    ],
    "components": []
  },
  "public": {
    "css": ["style.css"],
    "js": ["app.js"]
  }
}
```

- **inputDir**: Quellverzeichnis.
- **AusgabeVerzeichnis**: Ausgabeverzeichnis.
- **Intervall**: Intervall in Millisekunden, um das Ausgabeverzeichnis zu löschen und neu zu erstellen.
- **mainTemplate**: Pfad zur Handlebars-Hauptvorlage.
- **pagesDir**: Das Verzeichnis, das die Handlebars-Seitenvorlagen enthält.
- **templates**: Die Struktur der Vorlagen.
- **public**: Die Struktur der öffentlichen Entitäten.

## Skripte

- **start**: Führt das Hauptskript aus (`bootstrap.js`).

Übersetzt mit DeepL.com (kostenlose Version)
