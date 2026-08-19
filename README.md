---
subject : "Browser Extensions"
title : "Browser extension Copilot2Markdown"
subtitle : "MS Copilot → Markdown"
author : "ITSC IT Systems Consulting GmbH"
abstract: "Exports Copilot chats into Markdown documents."
keywords: ["Copilot", "Markdown"]
lang: "en"
---

Language / Sprache:

- 🇬🇧 English

- 🇩🇪 [Deutsch](./README.de.md)

Exports Copilot chats as Markdown.

# Overview

Unfortunately, the Copilot interface offers extremely limited options for archiving or further editing chats. Only the current conversation thread can be exported to Word or Pages - and the result isn't particularly attractive.

This is where "MS Copilot → Pretty Exporter" steps in; it processes Copilot chats and exports them to PDF, HTML, and Markdown. It also features a WYSIWYG document preview directly within the extension, allowing you to edit documents, add notes, or remove unwanted sections beforehand.

*Unlike similar extensions, no external services are used; conversion takes place entirely locally on your computer - your data remains 100% with you.*

## Quick Start

Install the extension and navigate to the Copilot site of your choice - either m365 Copilot or MS Copilot:

- [M365 Copilot: https://m365.cloud.microsoft](https://m365.cloud.microsoft)
- [MS Copilot: https://copilot.microsoft.com](https://copilot.microsoft.com)

Then, try a task like this:

> "Generate an output that demonstrates the capabilities of the Copilot interface. That means an output featuring a heading hierarchy, bullet points, numbered lists, check lists, quotes, tables, and code blocks. Create an attractive logo suited to this task and display it as the title of the output."

Open the context menu, select "MS Copilot → Pretty Exporter" / "Preview & Edit ...", and explore the functions of the toolbar buttons. Also, try the "Settings" button - all settings are thoroughly documented in the online help, giving you insight into the available features.

## How It Works

The extension analyzes, processes, and cleans up the Copilot webpage, converting it into Markdown format. Markdown is simple enough to be edited with any text editor, yet powerful enough to be used for professional books and presentations.

The extension then generates preview, PDF, and HTML files from the Markdown document.

# Features

With minor exceptions (see below), the generated Markdown code preserves all content and formatting from the chat:

- Headings
- Lists and bullet points (including structure)
- Quotes
- Tables
- Inline code and code blocks
- Links
- Images (including embedded images; the image file is automatically downloaded again after the Markdown file is downloaded). **Note: Do not change the image filenames after export; otherwise, the Markdown or HTML document will not be able to locate them.**

The extension is available in the respective extension stores for the following browsers:

- Chromium / Google Chrome (via the [Chrome Web Store](https://chromewebstore.google.com/))
- Firefox (via the [Mozilla Add-On Store](https://addons.mozilla.org))
- MS Edge[^1]. However, the extension must be installed from the [Chrome Web Store](https://chromewebstore.google.com/).

[^1]: MS Edge version 150 is buggy and does not allow any extensions for Microsoft sites like Copilot. Please ensure you use a newer or older version, or a different browser.

# Limitations

Items that currently cannot be exported:

- Source references in the "new" (July 2026) layout of M365 Copilot consist of a `button` that displays URLs in the sidebar via JavaScript. The extension cannot parse this, so the source references are lost.

# Please note

1. With extensive chats, the Copilot web interface sometimes loads only a portion of the conversation into the browser; as you scroll, newly visible parts are loaded, while parts that are no longer visible are removed from the browser's memory (DOM). **This extension can only export the parts that are currently loaded. Therefore, you may need to perform multiple exports to capture an entire chat.**
2. Microsoft frequently changes the layout of the Copilot page. Although I have endeavored to make the export process as independent as possible from the page structure, CSS classes used, etc., changes made by Microsoft might cause the extension to fail to locate certain content or format it incorrectly.
**In such a case, please create a ticket as described [below](#issues-and-feature-requests); I will do my best to update the extension as quickly as possible.**
3. If you are a programmer, you can modify the source code yourself (see the ["Source code availability"](#source-code-availability) section); typically, this involves adjusting CSS selectors in the `CONFIGS` section of `export-config.js`. I would appreciate it if you could share your modifications with me via a ticket (e.g., as a `diff`); I can then incorporate them into the extension packages available in the shops.

# Issues and Feature Requests

- If you encounter issues or have feature requests, please create a ticket in the `copilot2markdown` GitHub project:
[https://github.com/ITSC-GmbH/copilot2markdown](https://github.com/ITSC-GmbH/copilot2markdown)
- Before doing so, please check if a ticket regarding the same topic already exists.
- Be sure to specify whether M365 or MS Copilot is affected; the two rely on completely different page structures.
- In the event of errors, please describe how to reproduce the issue; screenshots and the problematic Markdown export are helpful.

# Source Code Availability

The source code for each release is freely available; you can download it from the "Releases" section of the GitHub project page: ["Releases"](https://github.com/ITSC-GmbH/copilot2markdown/releases).

# License

The code is licensed under the MIT License - meaning you are free to use it however you wish, provided you do not remove my copyright notices or the license description itself.

However, this license does not extend to the included third-party components. Detailed information can be found in the `licenses` subdirectory.






















