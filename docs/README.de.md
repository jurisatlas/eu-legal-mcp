[← All JurisAtlas Jurisdictions](https://github.com/jurisatlas) · [Unified Multi-Country Installer](https://github.com/jurisatlas/cli) · [English README](../README.md)

**Languages:** [English](../README.md) | [Français](README.fr.md) | **Deutsch** | [Español](README.es.md) | [Italiano](README.it.md)

# Amtliche Rechts- und Rechtsprechungsrecherche für Ihre KI — die Europäische Union & den EGMR (`eu-legal-mcp`)

Dieser kostenlose, schreibgeschützte Model Context Protocol (MCP) Server verbindet Ihre KI-Anwendung (Claude Desktop & Claude Code CLI, Cursor, VS Code (GitHub Copilot / Cline / Roo Code), Windsurf, Google Antigravity & Gemini CLI, LM Studio, OpenAI Codex CLI, and Continue.dev) direkt mit den amtlichen Gesetzesportalen und den mehrstufigen Rechtsprechungsdatenbanken für **die Europäische Union & den EGMR** (1. Instanz, Berufungs- und Obergerichte sowie Höchst- und Verfassungsgerichte).

**Kostenlos & Open Source (MIT) · Nur-Lese-Zugriff auf amtliche Portale · Keine API-Schlüssel · Kein Zugriff auf persönliche Dateien · 1-Klick-Deinstallation**

---

## Einfache Einrichtung (Ohne Programmierung, ohne ZIP)

> [!TIP]
> **1-Datei-Installer (Kein ZIP-Entpacken nötig):** Laden Sie nur die einzelne Datei unten herunter und doppelklicken Sie darauf — sie lädt alle benötigten Dateien automatisch von GitHub im Hintergrund herunter und öffnet den grafischen Assistenten. Optional können Sie weiterhin das vollständige Archiv über **`<> Code` → `Download ZIP`** herunterladen.
> - **Windows:** [`Click_Here_To_Install_Windows.bat`](https://github.com/jurisatlas/eu-legal-mcp/raw/main/Click_Here_To_Install_Windows.bat)
> - **macOS:** [`Click_Here_To_Install_Mac.command`](https://github.com/jurisatlas/eu-legal-mcp/raw/main/Click_Here_To_Install_Mac.command)
> - Mehrere Länder gleichzeitig nutzen? Verwenden Sie das **[Einheitliche Multi-Länder-Installationsprogramm (jurisatlas/cli)](https://github.com/jurisatlas/cli)** oder den **[zentralen Server (jurisatlas-mcp)](https://github.com/jurisatlas/jurisatlas-mcp)**.

1. **1 Datei herunterladen:** Klicken Sie oben auf den Windows- (`.bat`) oder macOS-Link (`.command`) — oder optional auf **`<> Code` → `Download ZIP`**.
2. **Doppelklick zum Starten:** Der selbstständige Starter lädt automatisch alle aktuellen Dateien von GitHub im Hintergrund herunter und öffnet den Installationsassistenten.
3. **KI-Programme verbinden:** Prüfen Sie Ihre automatisch erkannten KI-Anwendungen (Claude Desktop & Claude Code CLI, Cursor, VS Code (GitHub Copilot / Cline / Roo Code), Windsurf, Google Antigravity & Gemini CLI, LM Studio, OpenAI Codex CLI, and Continue.dev), klicken Sie auf **Install to Selected AI Clients** und starten Sie Ihre KI-Anwendung neu. Der Server wird dauerhaft installiert — die heruntergeladene Datei können Sie danach löschen.

**Hinweis für ChatGPT Desktop / Web & Claude Web:** Diese Apps verwenden eine Live-HTTPS-MCP-URL (`--transport streamable-http`, siehe unten).

### Verbindung per MCP-Link oder JSON

- **1-Click Links & Claude `.mcpb`:** [jurisatlas.github.io](https://jurisatlas.github.io) (Cursor `cursor://`, VS Code `vscode:mcp/`, Claude Desktop `.mcpb`).
- **Local MCP JSON (`uvx`):** `eu-legal-mcp` via `https://github.com/jurisatlas/eu-legal-mcp/archive/refs/heads/main.zip` (see Developer Reference below; no Git required).
- **Remote HTTPS MCP (`https://.../mcp`):** `eu-legal-mcp --transport streamable-http --host 0.0.0.0 --port 8000` or 1-click deploy on FastMCP Cloud / Render via [`jurisatlas-mcp`](https://github.com/jurisatlas/jurisatlas-mcp).

<details>
<summary><b>Windows-SmartScreen- oder macOS-Gatekeeper-Hinweis gesehen? (Normal & Sicher)</b></summary>

- **Windows (SmartScreen):** Klicken Sie auf **Weitere Informationen** → **Trotzdem ausführen**.
- **macOS (Gatekeeper / Sequoia):** Öffnen Sie **Systemeinstellungen → Datenschutz & Sicherheit**, scrollen Sie nach unten und klicken Sie neben der blockierten Datei auf **Dennoch öffnen**.
- *Warum erscheint dieser Hinweis?* Open-Source-Skripte ohne kommerzielles Entwicklerzertifikat lösen standardmäßig eine Betriebssystemwarnung aus. Der gesamte Quellcode ist öffentlich einsehbar.

</details>

**Sicherheit & 1-Klick-Deinstallation:** Der Server arbeitet ausschließlich im Nur-Lese-Modus mit öffentlichen amtlichen Rechtsportalen und greift auf keine persönlichen Dokumente zu. Zur vollständigen Entfernung öffnen Sie den Assistenten erneut und klicken auf **Uninstall / Remove**.

---

## Sofort ausprobieren: 3 Beispiel-Prompts

1. > Prüfe das Zitat `ECLI:EU:C:2023:123 or CELEX:32016R0679 (GDPR)` in den amtlichen Registern für die Europäische Union & den EGMR, bestätige ob ein amtlicher Registertreffer vorliegt, und fasse die Kernaussage zusammen.
2. > Recherchiere aktuelle Gesetze und obergerichtliche bzw. höchstrichterliche Rechtsprechung in die Europäische Union & den EGMR zu einem konkreten Rechtsproblem und nenne alle amtlichen Links.
3. > Stelle den dreistufigen Instanzenzug in die Europäische Union & den EGMR für eine zivil- oder verwaltungsrechtliche Streitigkeit dar und suche aktuelle Entscheidungen der Rechtsmittelinstanz.

---

## Abgedeckte Gerichtsinstanzen & Amtliche Portale

| Instanz | Abgedeckte Gerichte |
|:---|:---|
| **1. Instanz (Eingangsgerichte)** | National First-Instance Referring Courts (Article 267 TFEU Preliminary References) & EU Specialized Chambers |
| **2. Instanz (Ober- und Berufungsgerichte)** | General Court of the European Union (EGC — ECLI:EU:T:*) |
| **3. Instanz (Höchst- und Verfassungsgerichte)** | Court of Justice of the European Union (CJEU — ECLI:EU:C:*) & European Court of Human Rights (ECHR) |

- **EUR-Lex CELLAR REST/SPARQL API (EU Regulations, Directives, Decisions):** [https://eur-lex.europa.eu](https://eur-lex.europa.eu) (`eur-lex.europa.eu`, `publications.europa.eu`)
- **EUR-Lex CELLAR SPARQL & InfoCuria / ECHR HUDOC:** [https://curia.europa.eu](https://curia.europa.eu) (`curia.europa.eu`, `hudoc.echr.coe.int`, `eur-lex.europa.eu`)

---

<details>
<summary><b>Entwickler- & Technikreferenz (6 MCP-Tools, 3 Prompts, uvx, manuelles JSON & Streamable HTTP)</b></summary>

### Standardized MCP Tools (6 Tools)

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, regulations, and official gazettes in European Union & ECHR. Returns `source_tier` (`official_registry_api` vs `web_search_fallback`) and structured `warnings`. |
| `search_case_law` | Searches national jurisprudence and judicial archives for European Union & ECHR, tagging official API vs web fallback hits. |
| `search_tiered_court_decisions` | Filters case law by judicial instance (`first_instance`, `appellate_regional` — EU General Court (EGC), `supreme_constitutional`) or a sub-portal key. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and official sub-portal keys for European Union & ECHR. |
| `get_legal_document_markdown` | Fetches full statutory or judgment text (HTML or `.pdf`) and converts it to clean paginated Markdown. |
| `verify_citation` | Verifies legal citations against live sources, returning `VERIFIED_OFFICIAL_RECORD` only for official registry API hits, `UNCONFIRMED_WEB_MATCH` for web fallback hits, or `NOT_FOUND`. |

### Built-in MCP Prompts (3 Native Prompts)

- `verify_citations_in_draft` — Extract and audit every European Union & ECHR citation in a legal brief, memo, or contract.
- `research_statute_and_precedent` — Research controlling statutes and multi-tier case law for a legal issue.
- `map_court_hierarchy` — Map the 3-tier court escalation path and locate appellate decisions.

### Run Directly with `uvx` (No Git Required)

```bash
uvx --from https://github.com/jurisatlas/eu-legal-mcp/archive/refs/heads/main.zip eu-legal-mcp
```

### Remote HTTPS / Streamable HTTP Mode (ChatGPT Desktop / Web & Claude Web)

```bash
uvx --from https://github.com/jurisatlas/eu-legal-mcp/archive/refs/heads/main.zip eu-legal-mcp --transport streamable-http --host 127.0.0.1 --port 8000
```

### Manual JSON Configuration

**Claude Desktop / Cursor / Windsurf / Antigravity / LM Studio (`mcpServers`):**

```json
{
  "mcpServers": {
    "eu-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/eu-legal-mcp/archive/refs/heads/main.zip",
        "eu-legal-mcp"
      ],
      "env": {
        "PYTHONIOENCODING": "utf-8"
      }
    }
  }
}
```

**VS Code (`Code/User/mcp.json` — uses `"servers"` + `"type": "stdio"`):**

```json
{
  "servers": {
    "eu-legal-mcp": {
      "type": "stdio",
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/eu-legal-mcp/archive/refs/heads/main.zip",
        "eu-legal-mcp"
      ],
      "env": {
        "PYTHONIOENCODING": "utf-8"
      }
    }
  }
}
```

</details>

---

> **Kein Rechtsrat:** JurisAtlas ist ein Recherche-Hilfsmittel. Prüfen Sie gesetzliche Bestimmungen und Gerichtsentscheidungen stets anhand der amtlichen Verkündungsblätter und Gerichtsregister. Nur Ergebnisse mit `VERIFIED_OFFICIAL_RECORD` stammen aus strukturierten amtlichen APIs; `UNCONFIRMED_WEB_MATCH` erfordert eine manuelle Überprüfung. ([MIT License](../LICENSE))
