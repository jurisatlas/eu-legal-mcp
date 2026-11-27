[← All JurisAtlas Jurisdictions](https://github.com/jurisatlas) · [Unified Multi-Country Installer](https://github.com/jurisatlas/cli) · [English README](../README.md)

**Languages:** [English](../README.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Español](README.es.md) | **Italiano**

# Ricerca giuridica ufficiale per il tuo assistente IA — l'Unione europea e la CEDU (`eu-legal-mcp`)

Questo server Model Context Protocol (MCP) gratuito in sola lettura collega la tua applicazione IA (Claude Desktop & Claude Code CLI, Cursor, VS Code (GitHub Copilot / Cline / Roo Code), Windsurf, Google Antigravity & Gemini CLI, LM Studio, OpenAI Codex CLI, and Continue.dev) direttamente ai portali legislativi ufficiali e alle banche dati giurisprudenziali per **l'Unione europea e la CEDU** (tribunali di primo grado, corti d'appello e corti supreme o costituzionali).

**Gratuito & Open Source (MIT) · Sola lettura su portali ufficiali · Nessuna chiave API · Nessun accesso ai file personali · Disinstallazione in 1 clic**

---

## Installazione semplice (Senza codice, senza ZIP)

> [!TIP]
> **Programma di installazione a 1 file (Nessun ZIP richiesto):** Scarica solo il singolo file qui sotto e fai doppio clic — scarica automaticamente tutti i file necessari da GitHub in background e apre la finestra guidata. L'archivio ZIP completo (`<> Code` → `Download ZIP`) rimane disponibile come opzione.
> - **Windows:** [`Click_Here_To_Install_Windows.bat`](https://github.com/jurisatlas/eu-legal-mcp/raw/main/Click_Here_To_Install_Windows.bat)
> - **macOS:** [`Click_Here_To_Install_Mac.command`](https://github.com/jurisatlas/eu-legal-mcp/raw/main/Click_Here_To_Install_Mac.command)
> - Ti servono più giurisdizioni? Usa l'**[Installatore unificato multi-paese (jurisatlas/cli)](https://github.com/jurisatlas/cli)** o il **[server unificato (jurisatlas-mcp)](https://github.com/jurisatlas/jurisatlas-mcp)**.

1. **Scarica 1 file:** Fai clic sul link Windows (`.bat`) o macOS (`.command`) sopra (oppure scarica lo ZIP completo opzionale).
2. **Fai doppio clic per avviare:** L'avviatore scarica automaticamente in background i file aggiornati da GitHub e apre la finestra grafica di configurazione.
3. **Collega le tue app IA:** Controlla le applicazioni rilevate automaticamente (Claude Desktop & Claude Code CLI, Cursor, VS Code (GitHub Copilot / Cline / Roo Code), Windsurf, Google Antigravity & Gemini CLI, LM Studio, OpenAI Codex CLI, and Continue.dev), fai clic su **Install to Selected AI Clients** e riavvia il client IA.

**Nota per ChatGPT Desktop / Web e Claude Web:** Queste app utilizzano un URL MCP HTTPS remoto (`--transport streamable-http`, vedi sotto).

### Connessione tramite link MCP o JSON

- **1-Click Links & Claude `.mcpb`:** [jurisatlas.github.io](https://jurisatlas.github.io) (Cursor `cursor://`, VS Code `vscode:mcp/`, Claude Desktop `.mcpb`).
- **Local MCP JSON (`uvx`):** `eu-legal-mcp` via `https://github.com/jurisatlas/eu-legal-mcp/archive/refs/heads/main.zip` (see Developer Reference below; no Git required).
- **Remote HTTPS MCP (`https://.../mcp`):** `eu-legal-mcp --transport streamable-http --host 0.0.0.0 --port 8000` or 1-click deploy on FastMCP Cloud / Render via [`jurisatlas-mcp`](https://github.com/jurisatlas/jurisatlas-mcp).

<details>
<summary><b>Avviso Windows SmartScreen o macOS Gatekeeper? (Normale e sicuro)</b></summary>

- **Windows (SmartScreen):** Fai clic su **Ulteriori informazioni** → **Esegui comunque**.
- **macOS (Gatekeeper / Sequoia):** Apri **Impostazioni di Sistema → Privacy e sicurezza**, scorri verso il basso e fai clic su **Apri comunque**.
- *Perché compare questo avviso?* Gli script open source privi di certificato commerciale attivano automaticamente il controllo del sistema. Tutto il codice è pubblico e verificabile.

</details>

**Sicurezza e disinstallazione in 1 clic:** Opera esclusivamente in sola lettura sui portali ufficiali pubblici e non tocca mai i tuoi documenti personali. Per rimuoverlo completamente, riapri l'assistente e fai clic su **Uninstall / Remove**.

---

## Prova subito: 3 prompt pronti all'uso

1. > Verifica la citazione `ECLI:EU:C:2023:123 or CELEX:32016R0679 (GDPR)` nei registri ufficiali per l'Unione europea e la CEDU, specifica se è un riscontro ufficiale verificato e riassumi il principio di diritto.
2. > Cerca la normativa vigente e la giurisprudenza rilevante per l'Unione europea e la CEDU su una questione giuridica specifica, riportando i collegamenti ufficiali.
3. > Mappa i tre gradi di giudizio per l'Unione europea e la CEDU per una controversia civile o amministrativa e trova recenti pronunce di secondo grado.

---

## Gradi di giudizio & Portali ufficiali

| Grado di giudizio | Organi giudiziari coperti |
|:---|:---|
| **Primo grado (Tribunali di prima istanza)** | National First-Instance Referring Courts (Article 267 TFEU Preliminary References) & EU Specialized Chambers |
| **Secondo grado (Corti d'Appello e organi regionali)** | General Court of the European Union (EGC — ECLI:EU:T:*) |
| **Corti Supreme e Costituzionali** | Court of Justice of the European Union (CJEU — ECLI:EU:C:*) & European Court of Human Rights (ECHR) |

- **EUR-Lex CELLAR REST/SPARQL API (EU Regulations, Directives, Decisions):** [https://eur-lex.europa.eu](https://eur-lex.europa.eu) (`eur-lex.europa.eu`, `publications.europa.eu`)
- **EUR-Lex CELLAR SPARQL & InfoCuria / ECHR HUDOC:** [https://curia.europa.eu](https://curia.europa.eu) (`curia.europa.eu`, `hudoc.echr.coe.int`, `eur-lex.europa.eu`)

---

<details>
<summary><b>Riferimento tecnico per sviluppatori (6 strumenti MCP, 3 prompt, uvx, JSON manuale & Streamable HTTP)</b></summary>

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

> **Non costituisce consulenza legale:** JurisAtlas è uno strumento di supporto alla ricerca. Verifica sempre norme e sentenze sulle gazzette ufficiali. Solo `VERIFIED_OFFICIAL_RECORD` proviene da un'API ufficiale; `UNCONFIRMED_WEB_MATCH` richiede verifica manuale. ([MIT License](../LICENSE))
