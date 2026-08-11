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

# Overview

Creates a GFM-style Markdown file from a Copilot chat.

The export is triggered either by clicking the extension icon or via the `Copilot → Markdown ...` entry in the context menu.

The extension is available in the respective “extension store” for the following browsers:

- Chromium / Google Chrome (im [Chrome Web Store](https://chromewebstore.google.com/))
- Firefox ([Mozilla Add-On Store](https://addons.mozilla.org))
- MS Edge[^1]. However, the extension must be installed from the [Chrome Web Store](https://chromewebstore.google.com/).

The extension currently supports the following Copilot versions:

  - [m365 Copilot: https://m365.cloud.microsoft](https://m365.cloud.microsoft)
  - [MS Copilot: https://copilot.microsoft.com](https://copilot.microsoft.com)

*Unlike similar extensions, no external services are used; conversion takes place entirely locally on your computer - your data remains 100% with you.*

[^1]: see ["Problems with Microsoft Edge version 150" ](#problems-with-microsoft-edge-version-150)

> [!CAUTION]
>
> ### *Problems with Microsoft Edge version 150*
>
> *Problems with Microsoft Edge version 150*
>
> *In Edge version 150, Microsoft arbitrarily - and without any documentation - implemented restrictions for `*.cloud.microsoft`, `copilot.microsoft.com`, `www.microsoft365.com`, and other domains that block <u>all</u> extensions on these pages!*
> *See discussion here: [Bug - Edge Addons: All extensions are blocked on \*.cloud.microsoft starting in Edge ≥150 with no override #644](https://github.com/microsoft/MicrosoftEdge-Extensions/issues/644)*
>
> *This is reportedly set to be changed back in Edge version 152, but I have been unable to find an official statement from Microsoft regarding this.*

# Features

With a few exceptions (see below), the generated Markdown code preserves all content and formatting from the chat:

  - Headings
  - Lists and bulleted lists, with structure
  - Quotes
  - Tables
  - Inline code and code blocks
  - Links
  - Images. This includes embedded images; for each image, the image file is automatically downloaded before the Markdown file is downloaded. **Warning: Do not change the names of the image files, otherwise the Markdown code will not be able to find them!**

# Limitations

What is not exported:

  - Source references in the “new” (July 2026) layout of m365-Copilot consist of a `button` that displays the URLs in the sidebar via JavaScript. The extension cannot parse this, so the source references are lost.
  - Horizontal rules (`hr`) before headings are intentionally removed because they are typographically incorrect and disrupt the layout.

# Please note

1. For longer chats, the Copilot web interface sometimes loads only a portion of the chat into the browser; when you scroll, the now-visible parts are reloaded, but the parts that are no longer visible are removed from the browser’s memory (DOM). **This extension can only export the parts that are currently loaded. You may therefore need to perform multiple exports for a single chat.**
2. Microsoft is constantly changing the structure of the Copilot page. Although I’ve tried to make the export as independent as possible from the structure, the CSS classes used, etc., it’s possible that after a change by Microsoft, the extension may no longer format some content correctly or may not find it at all.
  **In such cases, please create a ticket as [described below](#problems-and-feature-requests); I will do my best to update the extension as soon as possible.**
3. If you are a programmer yourself, you can customize the source code on your own (see the section ["Source Code Availability"](#source-code-availability)); this is usually limited to adjusting CSS selectors in the `CONFIGS` section of `content-config.js`. I would appreciate it if you could send me the changes in a ticket (e.g., as a `diff`); I can then incorporate them into the extension packages available in the shops.

# Issues and Feature Requests

- If you encounter any issues or have feature requests, please open a ticket in the GitHub project `copilot2markdown`:
  [https://github.com/ITSC-GmbH/copilot2markdown](https://github.com/ITSC-GmbH/copilot2markdown)
- Please check first to see if another ticket on the same topic already exists.
- Be sure to specify whether m365 or MS Copilot is affected; these two are based on completely different page structures.
- For bugs, describe how the issue can be reproduced; screenshots and the faulty Markdown export are helpful.

# Source Code Availability

The source code for each release is freely available; you can download it from the GitHub project page in the [“Releases”](https://github.com/ITSC-GmbH/copilot2markdown/releases) section.

The code is licensed under the MIT License - which means you can do whatever you want with it, as long as you do not remove my copyright notices or the license text itself.