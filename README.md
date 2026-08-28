# Universal Scrolling Screenshot

> **Capture complete webpages, dashboards, data grids, and nested scrollable areas — vertically and horizontally — without losing detail.**

Universal Scrolling Screenshot is a Chrome extension designed for webpages that conventional screenshot tools often struggle with: wide tables, long dashboards, virtualized grids, nested scroll containers, and interfaces that scroll in both directions.

It can also extract supported tables directly to **CSV** or **Excel (.xlsx)**, using the fastest available extraction method before falling back to controlled scrolling when required.

---

## Chrome Web Store

**Version:** 1.0

> **Chrome Web Store:** [Install Universal Scrolling Screenshot](https://chromewebstore.google.com/detail/universal-scrolling-scree/nfjelpifbaainmjejfpacgeaefjialdi)

_The Chrome Web Store URL is live._

---

## Key Features

### Full-page and scroll-area screenshots

- Capture normal webpages vertically.
- Capture pages that scroll horizontally and vertically.
- Capture nested scrollable containers.
- Capture dashboards and independently scrolling panels.
- Manually select the exact scroll area to capture.
- Automatically detect likely scroll targets.
- Preserve native screenshot resolution whenever possible.
- Use lossless tile-based output for exceptionally large captures instead of intentionally downscaling them.

### Stop & Save

Long-running operations do not need to finish before you can keep the result.

During screenshot capture you can use **Stop & Save** to:

- stop after the current capture step;
- preserve everything captured so far;
- save a valid partial image;
- restore the original page or grid scroll position.

The same concept is available for table extraction, allowing collected CSV/XLSX data to be saved even when you stop an extraction early.

### CSV and Excel table export

The extension can create:

- **CSV** for lightweight, interoperable raw-data export;
- **Excel (.xlsx)** for convenient viewing, filtering, editing, and structured table use.

The addon does **not** depend on a website exposing its own CSV or Excel download button.

Instead, it checks for the most efficient extraction method available for the selected table.

The preferred order is:

1. **Direct framework/data API** — fastest; no scrolling when the complete dataset is accessible.
2. **Complete HTML table** — direct DOM extraction when all rows and columns are already present.
3. **Virtual-grid reconstruction** — controlled horizontal and vertical scanning when only part of a large grid is rendered.
4. **Screenshot capture** — when structured extraction is not feasible.

### Virtualized and complex grids

Universal Scrolling Screenshot includes handling for common grid and table architectures, including:

- DataTables
- Handsontable
- SlickGrid
- AG Grid
- Elastic / Kibana-style grids
- EUI DataGrid
- MUI DataGrid
- React Data Grid
- Tabulator
- React Virtualized
- standard HTML tables
- ARIA-based grids
- other DOM-based virtualized tables where row and column data can be reconstructed

Framework support can vary depending on how a specific website exposes its grid instance and data model.

### Estimated completion time

For long operations, the extension provides progress and estimated completion information.

Examples include:

- screenshot tile progress;
- expected finish time;
- estimated remaining duration;
- virtual-grid scan progress;
- CSV/XLSX extraction progress;
- file-generation progress.

Estimates are continuously refined using actual operation timings.

---

## Diagnostic Logging

Universal Scrolling Screenshot includes structured diagnostic logging to help troubleshoot complex websites without requiring captured table contents to be included in the log.

Available logging levels:

| Level | Purpose |
|---|---|
| **Off** | Disable diagnostic logging |
| **Error** | Failures and reasons only |
| **Warn** | Errors plus fallbacks, cancellations, and risky conditions |
| **Info** | Recommended for normal troubleshooting |
| **Debug** | Detailed capture and extraction milestones |
| **Trace** | Maximum technical detail for difficult rendering/stitching issues |

Diagnostic events may include:

- operation ID;
- timestamps;
- success/failure outcome;
- reason codes;
- capture-target geometry;
- tile coordinates;
- scroll or transform positions;
- crop and stitch coordinates;
- canvas growth decisions;
- framework detection;
- timings and performance information.

### Diagnostic privacy

Diagnostic logs are designed to avoid storing:

- screenshot image payloads;
- table-cell contents;
- extracted CSV/XLSX data.

Users can download diagnostic logs for troubleshooting and clear them from the extension interface.

---

## Privacy First

Universal Scrolling Screenshot is designed around **local browser processing**.

Screenshot capture, table extraction, CSV/XLSX generation, and diagnostic processing are performed locally in the browser.

The extension does not intentionally transmit captured webpage content, screenshots, or extracted table data to the developer or third parties.

For full details, read the:

**[Privacy Policy](https://cyberarchon.github.io/universal-scrolling-screenshot/privacy.html)**

---

## Chrome Permissions

The extension uses a limited set of Chrome permissions required for its core functionality:

| Permission | Why it is used |
|---|---|
| `activeTab` | Access the webpage only after the user invokes the extension |
| `scripting` | Inspect and control the selected page/scroll container during capture or extraction |
| `downloads` | Save screenshots, CSV files, Excel files, and diagnostic logs |
| `storage` | Store extension preferences and temporary diagnostic state |

The extension does not require blanket permanent access to every website through `<all_urls>`.

---

## Typical Use Cases

Universal Scrolling Screenshot is useful for:

- large web tables;
- security dashboards;
- SIEM dashboards;
- analytics dashboards;
- Splunk-style interfaces;
- Elastic/Kibana-style interfaces;
- reporting portals;
- administrative consoles;
- data grids with frozen headers or columns;
- horizontally scrolling tables;
- long vertically scrolling tables;
- virtualized datasets;
- webpages with nested scroll containers;
- pages where conventional full-page screenshot tools miss content.

---

## How It Works

```text
Webpage / Dashboard / Data Grid
              │
              ▼
     Detect or select target
              │
      ┌───────┴────────┐
      │                │
      ▼                ▼
 Screenshot         Table Data
      │                │
      ▼                ▼
 Vertical +        Best available
 Horizontal        extraction path
 Tile Capture           │
      │          ┌──────┴─────────┐
      ▼          │                │
 PNG / SVG     CSV             Excel
```

For screenshots, the extension moves through the capture target in controlled tiles and stitches the results while preserving already-captured regions.

For tables, the extension first checks whether the complete dataset can be retrieved directly before using a slower virtual-grid scan.

---

## Website

**Product homepage**  
https://cyberarchon.github.io/universal-scrolling-screenshot/

**Privacy Policy**  
https://cyberarchon.github.io/universal-scrolling-screenshot/privacy.html

**Support**  
https://cyberarchon.github.io/universal-scrolling-screenshot/support.html

**FAQ**  
https://cyberarchon.github.io/universal-scrolling-screenshot/faq.html

**Release Notes**  
https://cyberarchon.github.io/universal-scrolling-screenshot/changelog.html

---

## Support

If you encounter a website that does not capture or export correctly, please provide as much of the following as you can safely share:

- Chrome version;
- Universal Scrolling Screenshot version;
- affected website URL, if it is public;
- screenshot demonstrating the problem;
- diagnostic log generated with **Debug** or **Trace** logging enabled.

Please **do not send confidential, proprietary, personal, or sensitive webpage content** when reporting an issue.

**Support email:**  
[CyberArchon@outlook.com](mailto:CyberArchon@outlook.com)

---

## Support Development

If Universal Scrolling Screenshot saves you time and you would like to support continued development, testing, and maintenance:

**[Support via PayPal](https://www.paypal.me/rameshbabu71)**

PayPal: **@rameshbabu71**

Donations are optional and do not unlock additional extension functionality.

---

## Version 1.0

Version 1.0 includes:

- full-page vertical screenshot capture;
- horizontal + vertical scrolling capture;
- nested scroll-container support;
- smart target detection;
- manual scroll-area selection;
- high-resolution stitching;
- Stop & Save for screenshot capture;
- CSV export;
- Excel (.xlsx) export;
- direct framework/API table extraction where available;
- HTML-table extraction;
- virtualized-grid reconstruction;
- Stop & Save for table extraction;
- live progress and ETA;
- structured diagnostic logging;
- multiple logging levels;
- support for complex grid structures and synchronized headers.

See the full **[Release Notes](https://cyberarchon.github.io/universal-scrolling-screenshot/changelog.html)**.

---

## Known Limitations

Some browser/application architectures cannot be handled generically by a Chrome extension.

Examples can include:

- cross-origin iframe content that the extension cannot access;
- closed Shadow DOM;
- canvas/WebGL applications that do not expose usable DOM data;
- custom interfaces that simulate scrolling without exposing normal scrolling state;
- genuinely infinite datasets with no finite end;
- proprietary grid implementations that do not expose stable data or cell coordinates.

Where direct table extraction is unavailable, the extension attempts an appropriate fallback method.

---

## Security and Responsible Reporting

If you believe you have found a security or privacy issue, please do not disclose sensitive details publicly.

Contact:

**CyberArchon@outlook.com**

Include **Security Report — Universal Scrolling Screenshot** in the subject line.

---

## Developer

**Ramesh Babu**

Developer and maintainer of Universal Scrolling Screenshot.

Support: [CyberArchon@outlook.com](mailto:CyberArchon@outlook.com)

---

## Project Status

**Current public release:** 1.0

This repository hosts the public website, documentation, privacy information, support resources, and release information for Universal Scrolling Screenshot.

The Chrome Web Store installation link will be added after the extension is published.

---

## Copyright

Copyright © 2026 Ramesh Babu.

All rights reserved unless otherwise stated.
