---
subject : "Browser-Erweiterungen"
title : "Browser-Erweiterung Copilot2Markdown"
subtitle : "MS Copilot → Markdown"
author : "ITSC IT Systems Consulting GmbH"
abstract: "Exportiert Copilot-Chats in Markdown-Dokumente."
keywords: ["Copilot", "Markdown"]
lang: "de"
---

Exportiert Copilot-Chats als Markdown.

# Überblick

Erstellt aus einem Copilot-Chat eine Markdown-Datei im GFM-Stil.

Der Export wird entweder durch Klick auf das Erweiterungssymbol oder über den Eintrag `Copilot → Markdown ...` im Kontextmenü angestoßen.

Die Erweiterung ist im jeweiligen "Erweiterungs-Shop" für folgende Browser verfügbar:

- Chromium / Google Chrome (im [Chrome Web Store](https://chromewebstore.google.com/))
- Firefox ([Mozilla Add-On Store](https://addons.mozilla.org))
- MS Edge[^1]. Die Erweiterung muss allerdings aus dem [Chrome Web Store](https://chromewebstore.google.com/) installiert werden.

Folgende Copilot-Varianten werden derzeit unterstützt:

  - [m365 Copilot: https://m365.cloud.microsoft](https://m365.cloud.microsoft)
  - [MS Copilot: https://copilot.microsoft.com](https://copilot.microsoft.com)

*Ungleich ähnlichen Erweiterungen werden keine externen Dienste verwendet, die Konvertierung erfolgt ausschließlich lokal auf dem Rechner - Ihre Daten bleiben zu 100% bei Ihnen.*

[^1]: siehe ["Probleme mit Microsoft Edge Version 150"](#probleme-mit-microsoft-edge-version-150)

> [!caution]
>
> ### *Probleme mit Microsoft Edge Version 150*
>
> *Microsoft hat in Edge Version 150 willkürlich und ohne dies zu dokumentieren Sperren für alle `*.cloud.microsoft`, `copilot.microsoft.com`, `www.microsoft365.com` und andere eingebaut, die **<u>jegliche</u>** Erweiterung auf diesen Seiten blockiert!*
> *Siehe Diskussion hier: [Bug - Edge Addons: All extensions are blocked on \*.cloud.microsoft starting in Edge ≥150 with no override #644](https://github.com/microsoft/MicrosoftEdge-Extensions/issues/644)*
>
> *Angeblich soll dies in Edge Version 152 wieder geändert werden, aber ein offizielles Statement von MS hierzu konnte ich nirgends finden.*
>
> *Bis dahin ist die einzige Lösung, auf Version 149 zurückzugehen, um wieder Erweiterungen auf Microsoft-Seiten nutzen zu können - oder einfach auf Chromium oder Firefox umzusteigen.*

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
3. Sind Sie selbst Programmierer, können Sie den Quellcode selbst anpassen (siehe Abschnitt ["Verfügbarkeit des Quellcodes"](#verfügbarkeit-des-quellcodes)); in der Regel beschränkt sich dies auf die Anpassung von CSS Selektoren im `CONFIG`-Abschnitt. Ich wäre Ihnen dankbar, wenn Sie mir die Anpassungen in einem Ticket zukommen lassen (z. B. als `diff`); ich kann dies dann in die Erweiterungspakete in den Shops übernehmen.

# Probleme und Änderungswünsche

- Bei Problemen oder Änderungswünschen erstellen Sie ein Ticket im Github-Projekt `copilot2markdown`:
  [https://github.com/ITSC-GmbH/copilot2markdown](https://github.com/ITSC-GmbH/copilot2markdown)
- Prüfen Sie zuvor, ob bereits ein anderes Ticket zum selben Thema existiert.
- Geben Sie unbedingt an, ob m365 oder MS Copilot betroffen sind; diese beiden basieren auf einer völlig unterschiedlichen Seitenstruktur.
- Bei Fehlern beschreiben Sie, wie das Problem nachvollzogen werden kann; Screenshots und der fehlerhafte Markdown-Export sind hilfreich.

# Verfügbarkeit des Quellcodes

Der Quellcode jedes Releases steht frei zur Verfügung; Sie können ihn auf der GitHub-Projektseite im Abschnitt ["Releases"](https://github.com/ITSC-GmbH/copilot2markdown/releases) herunterladen.

Der Code steht unter der MIT-Lizenz - das heißt, Sie können damit machen, was Sie wollen, sofern Sie meine Copyright-Hinweise und die Lizenzbeschreibung selbst nicht entfernen.
