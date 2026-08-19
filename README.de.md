---
subject : "Browser-Erweiterungen"
title : "Browser-Erweiterung Copilot2Markdown"
subtitle : "MS Copilot → Markdown"
author : "ITSC IT Systems Consulting GmbH"
abstract: "Exportiert Copilot-Chats in Markdown-Dokumente."
keywords: ["Copilot", "Markdown"]
lang: "de"
---

Exportiert Copilot Chats schön aufbereitet nach PDF, HTML und Markdown.

# Überblick

Leider sind die Möglichkeiten der Copilot-Oberfläche extrem limitiert, wenn es darum geht, Chats zu archivieren oder weiterzubearbeiten. Lediglich die aktuelle Dialogrund kann nach Word oder Pages exportiert werden - und das nicht einmal besonders hübsch.

Hier springt "MS Copilot → Pretty Exporter" in die Bresche, bereitet die Copilot Chats auf und exportiert sie nach PDF, HTML und Markdown. Auch eine WYSIWYG-Vorschau der Dokumente direkt in der Erweiterung ist vorhanden, in der Sie die Dokumente sogar vorab bearbeiten, Notizen hinzufügen oder ungewünschte Passagen entfernen können.

*Ungleich ähnlichen Erweiterungen werden keine externen Dienste verwendet, die Konvertierung erfolgt ausschließlich lokal auf dem Rechner - Ihre Daten bleiben zu 100% bei Ihnen.*

## Schnellstart

Installieren Sie die Erweiterung und gehen auf die Copilot-Seite Iher Wahl, entweder m365-Copilot oder MS-Copilot:

  - [m365 Copilot: https://m365.cloud.microsoft](https://m365.cloud.microsoft)
  - [MS Copilot: https://copilot.microsoft.com](https://copilot.microsoft.com)

Probieren Sie es dann mit einer Aufgabe wie dieser:

> "Erstelle eine Ausgabe, die die Möglichkeiten der Copilot-Oberfläche demonstriert. Das heißt, eine Ausgabe mit einer Überschriften-Hierarchie, mit Aufzählungen, Nummerierungen, Checklisten, Zitaten, Tabellen und Codeblöcken. Erzeuge ein hübsches, zu dieser Aufgabe passendes Logo und zeige es als Titel der Ausgabe an."

Rufen Sie aus dem Kontextmenü heraus "MS Copilot → Pretty Exporter" / "Vorschau & Bearbeitung ..." und schauen sich dort die Möglichkeiten der "Toolbar-Buttons" an. Versuchen Sie auch den Button "Einstellungen" - alle Einstellungen sind ausführlich in der Online-Hilfe dokumentiert und geben Ihnen einen Einblick in die Möglichkeiten.

## Funktionsprinzip

Die Copilot-Webseite wird von der Erweiterung analysiert, aufbereitet und bereinigt und in das Markdown-Format übersetzt. Markdown ist auf der einen Seite so simpel, dass es mit jedem beliebigen Texteditor bearbeitet werden kann, auf der anderen Seite so leistungsfähig, das  es auch für professionelle Bücher und Präsentationen genutzt wird.

Aus dem Markdown-Dokument erzeugt die Erweiterung anschließend Vorschau, PDF- und HTML-Dateien.

# Funktionsumfang

Der erstellte Markdown-Code übernimmt mit kleinen Ausnahmen (s. u.) sämtliche Inhalte und Formatierungen des Chat:

  - Überschriften
  - Listen und Aufzählungen, mit Struktur
  - Zitate
  - Tabellen
  - Inline-Code und Code-Blöcke
  - Links
  - Bilder. Auch eingebettete Bilder; für jedes Bild erfolgt hier nach dem Download der Markdown-Datei nochmals automatisch ein Download der Bild-Datei. **Achtung, Namen der Bild-Dateien nicht ändern, sonst findet sie der Markdown-Code nicht!**

Die Erweiterung ist im jeweiligen "Erweiterungs-Shop" für folgende Browser verfügbar:

- Chromium / Google Chrome (im [Chrome Web Store](https://chromewebstore.google.com/))
- Firefox ([Mozilla Add-On Store](https://addons.mozilla.org))
- MS Edge[^1]. Die Erweiterung muss allerdings aus dem [Chrome Web Store](https://chromewebstore.google.com/) installiert werden.

[^1]: MS Edge Version 150 ist fehlerhaft und erlaubt keinerlei Erweiterungen für Microsoft-seiten wie Copilot. Verwenden Sie unbedingt eine neuere oder ältere Version oder einen anderen Browser.

# Einschränkungen 

Was derzeit nicht exportiert werden kann:

  - Quellenverweise im "neuen" (Juli 2026) Layout von m365-Copilot bestehen aus einem `button`, der per Javascript in der Seitenleiste die URLs anzeigt. Dies kann die Erweiterung nicht analysieren, die Quellenverweise gehen verloren.

# Bitte beachten

1. Die Copilot Web-Oberfläche lädt bei umfangreicheren Chats manchmal nur einen Teil des Chats in den Browser; beim Blättern oder Scrollen werden die nun sichtbaren Teile nachgeladen, die nicht mehr sichtbaren jedoch aus dem Speicher des Browsers (DOM) entfernt. **Diese Erweiterung kann nur die Teile exportieren, die momentan geladen sind. Sie müssen für einen ganzen Chat deshalb eventuell mehrere Exports durchführen.**
2. Microsoft ändert ständig den Aufbau der Copilot-Seite. Obwohl ich mich bemüht habe, den Export möglichst unabhängig von der Struktur, den verwendeten CSS-Klassen usw. zu halten, kann es sein, dass die Erweiterung nach einer Änderung durch Microsoft manche Inhalte nicht mehr korrekt formatiert oder gar nicht findet.
**Bitte erstellen Sie in einem solchen Fall wie [unten beschrieben](#probleme-und-änderungswünsche) ein Ticket, ich werde mich bemühen, die Erweiterung so schnell es geht anzupassen.**
3. Sind Sie selbst Programmierer, können Sie den Quellcode selbst anpassen (siehe Abschnitt ["Verfügbarkeit des Quellcodes"](#verfügbarkeit-des-quellcodes)); in der Regel beschränkt sich dies auf die Anpassung von CSS Selektoren im `CONFIGS`-Abschnitt von `export-config.js`. Ich wäre Ihnen dankbar, wenn Sie mir die Anpassungen in einem Ticket zukommen lassen (z. B. als `diff`); ich kann dies dann in die Erweiterungspakete in den Shops übernehmen.

# Probleme und Änderungswünsche

- Bei Problemen oder Änderungswünschen erstellen Sie ein Ticket im Github-Projekt `copilot2markdown`:
  [https://github.com/ITSC-GmbH/copilot2markdown](https://github.com/ITSC-GmbH/copilot2markdown)
- Prüfen Sie zuvor, ob bereits ein anderes Ticket zum selben Thema existiert.
- Geben Sie unbedingt an, ob m365 oder MS Copilot betroffen sind; diese beiden basieren auf einer völlig unterschiedlichen Seitenstruktur.
- Bei Fehlern beschreiben Sie, wie das Problem nachvollzogen werden kann; Screenshots und der fehlerhafte Markdown-Export sind hilfreich.

# Verfügbarkeit des Quellcodes

Der Quellcode jedes Releases steht frei zur Verfügung; Sie können ihn auf der GitHub-Projektseite im Abschnitt ["Releases"](https://github.com/ITSC-GmbH/copilot2markdown/releases) herunterladen.

# Lizenz

Der Code steht unter der MIT-Lizenz - das heißt, Sie können damit machen, was Sie wollen, sofern Sie meine Copyright-Hinweise und die Lizenzbeschreibung selbst nicht entfernen.

Diese Lizenz erstreckt sich jedoch nicht auf die mitgelieferten Dritt-Partei-Komponenten. Genauere Informationen finden Sie im Unterverzeichnis `licenses`.
