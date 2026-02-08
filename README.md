# Impact Calculator                                                        
                                                                             
  A browser-based EBIT impact calculator built with React, Tailwind CSS, and
  Chart.js. Designed for evaluating the financial impact of innovation
  initiatives across retail stores — now with multi-scenario comparison,
  charts, and dark mode.

  ## Live Versions

  | File | Version | Description |
  |------|---------|-------------|
  | `index.html` | **v3 (current)** | Multi-scenario calculator with charts,
  AUD currency, dark mode |
  | `index_v2.html` | v2 | Single scenario with cost tracking and ROI metrics
   |
  | `index_v1.html` | v1 | Original single-scenario calculator |

  ## What's New in v3

  ### Multi-Scenario Support
  - Compare up to **3 independent scenarios** side by side
  - Tabbed interface — click to switch, double-click to rename
  - Each scenario has its own inputs, results, and confidence levels

  ### Charts & Visualization
  - **Bar chart** comparing total EBIT across all scenarios
  - **Waterfall chart** breaking down EBIT components (Gross Profit, Labour
  Savings, Other EBIT)
  - Charts update live as you change inputs

  ### Dark Mode
  - Toggle between light and dark themes
  - Preference saved to browser storage
  - Print mode forces light theme for readability

  ### AUD Currency
  - All monetary values displayed in Australian Dollars (A$)
  - Formatted with `Intl.NumberFormat('en-AU')`

  ### Print Support
  - Clean print layout — hides tabs, buttons, and UI controls
  - Forces light background for readability

  ### Backward Compatibility
  - Automatically migrates saved v2 data into v3's first scenario
  - Import supports both v2 (flat JSON) and v3 (multi-scenario) formats

  ## Calculations

  Each scenario computes:

  | Metric | Formula |
  |--------|---------|
  | Incremental Sales | Stores x Weeks x Base Sales x Uplift % |
  | Gross Profit | Incremental Sales x Gross Margin % |
  | Labour Savings | Stores x Weeks x Hours Saved x Labour Rate |
  | Total EBIT Impact | Gross Profit + Labour Savings + Other EBIT |
  | Annualised EBIT | (Total EBIT / Weeks) x 52 |
  | ROI | (Total EBIT / Implementation Cost) x 100 |
  | Payback Period | Implementation Cost / Weekly EBIT |

  Confidence levels (10%–120%) scale the Total EBIT for sensitivity analysis.

  ## Input Parameters

  **Scope** — Stores, Weeks, Gross Margin %

  **Sales Uplift** — Base Sales per Store/Week, Uplift %

  **Labour & Other** — Hours Saved per Store/Week, Labour Rate, Other EBIT
  (+/-)

  **Investment** — Implementation Cost

  ## Tech Stack

  - **React 18.2** — component-based UI with hooks
  - **Tailwind CSS 2.2** — utility-first styling
  - **Chart.js 4.4** — bar and waterfall charts
  - **Babel Standalone** — in-browser JSX transpilation
  - **localStorage** — persistent state across sessions (no backend required)

  ## Data Management

  - **Export** — download scenario data as JSON
  - **Import** — load from JSON file (supports v2 and v3 formats)
  - **Copy** — copy confidence level table to clipboard (TSV, paste into
  Excel/Sheets)

  ## Usage

  No build step required. Open `index.html` in any modern browser.

  ```bash
  # or serve locally
  npx serve .

  Version History
  Version: v3
  Key Changes: Multi-scenario (up to 3), AUD currency, Chart.js
    visualizations, dark mode, print support, v2 data migration
  ────────────────────────────────────────
  Version: v2
  Key Changes: Added Innovation Initiative Costs section (recurring +
    one-off), ROI, Payback Period, Annualised EBIT
  ────────────────────────────────────────
  Version: v1
  Key Changes: Original calculator — single scenario, USD, confidence levels,

    export/import
  ---