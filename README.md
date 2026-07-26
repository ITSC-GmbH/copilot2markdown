---
title: Browser-Erweiterung Copilot2Markdown
subtitle: MS Copilot → Markdown
---

Exportiert Copilot-Chats als Markdown.

# Überblick

Erstellt aus einem Copilot-Chat eine Markdown-Datei im GFM-Stil.

Der Export wird entweder durch Klick auf das Erweiterungssymbol oder über den Eintrag `Copilot → Markdown ...` im Kontextmenü angestoßen.

Die Erweiterung ist im jeweiligen "Erweiterungs-Shop" für folgende Browser verfügbar:

- Chromium / Google Chrome
- Firefox
- Die Chromium-Erweiterung funktioniert zwar auch mit MS Edge, ist aber im MS-Shop derzeit nicht vorhanden.

Die Erweiterung unterstützt derzeit folgende Copilot-Varianten:

  - [m365 Copilot: https://m365.cloud.microsoft](https://m365.cloud.microsoft)
  - [MS Copilot: https://copilot.microsoft.com](https://copilot.microsoft.com)

# Funktionsumfang

Der erstellte Markdown-Code übernimmt mit kleinen Ausnahmen (s. u.) sämtliche Inhalte und Formatierungen des Chat:

  - Überschriften
  - Listen und Aufzählungen, mit Struktur
  - Zitate
  - Tabellen
  - Inline-Code und Code-Blöcke
  - Links
  - Bilder. Auch eingebettete Bilder; für jedes Bild erfolgt hier nach dem Download der Markdown-Datei nochmals automatisch ein Download der Bild-Datei. **Achtung, Namen der Bild-Dateien nicht ändern, sonst findet sie der Markdown-Code nicht!**

# Einschränkungen 

Was nicht exportiert wird:

  - Quellenverweise im "neuen" (Juli 2026) Layout von m365-Copilot bestehen aus einem `button`, der per Javascript in der Seitenleiste die URLs anzeigt. Dies kann die Erweiterung nicht analysieren, die Quellenverweise gehen verloren.
  - Trennlinien (`hr`) vor Überschriften werden absichtlich entfernt, da sie typografisch falsch sind und das Layout zerstören.

# Bitte beachten

  1. Die Copilot Web-Oberfläche lädt bei umfangreicheren Chats manchmal nur einen Teil des Chats in den Browser; beim Blättern oder Scrollen werden die nun sichtbaren Teile nachgeladen, die nicht mehr sichtbaren jedoch aus dem Speicher des Browsers (DOM) entfernt. **Diese Erweiterung kann nur die Teile exportieren, die momentan geladen sind. Sie müssen für einen ganzen Chat deshalb eventuell mehrere Exports durchführen.**
    2. Microsoft ändert ständig den Aufbau der Copilot-Seite. Obwohl ich mich bemüht habe, den Export möglichst unabhängig von der Struktur, den verwendeten CSS-Klassen usw. zu halten, kann es sein, dass die Erweiterung nach einer Änderung durch Microsoft manche Inhalte nicht mehr korrekt formatiert oder gar nicht findet.
       **Bitte erstellen Sie in einem solchen Fall wie [unten beschrieben](#probleme-und-änderungswünsche) ein Ticket, ich werde mich bemühen, die Erweiterung so schnell es geht anzupassen.**

# Probleme und Änderungswünsche

- Bei Problemen oder Änderungswünschen erstellen Sie ein Ticket im Github-Projekt `copilot2markdown`:
  [https://github.com/ITSC-GmbH/copilot2markdown](https://github.com/ITSC-GmbH/copilot2markdown)
- Prüfen Sie zuvor, ob bereits ein anderes Ticket zum selben Thema existiert.
- Geben Sie unbedingt an, ob m365 oder MS Copilot betroffen sind; diese beiden basieren auf einer völlig unterschiedlichen Seitenstruktur.
- Bei Fehlern beschreiben Sie, wie das Problem nachvollzogen werden kann; Screenshots und der fehlerhafte Markdown-Export sind hilfreich.
