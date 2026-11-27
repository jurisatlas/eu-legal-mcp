[← All JurisAtlas Jurisdictions](https://github.com/jurisatlas) · [Unified Multi-Country Installer](https://github.com/jurisatlas/cli) · [English README](../README.md)

**Languages:** [English](../README.md) | **Français** | [Deutsch](README.de.md) | [Español](README.es.md) | [Italiano](README.it.md)

# Recherche juridique officielle pour votre assistant IA — l'Union européenne et la CEDH (`eu-legal-mcp`)

Ce serveur Model Context Protocol (MCP) gratuit et en lecture seule connecte directement votre application d'IA (Claude Desktop & Claude Code CLI, Cursor, VS Code (GitHub Copilot / Cline / Roo Code), Windsurf, Google Antigravity & Gemini CLI, LM Studio, OpenAI Codex CLI, and Continue.dev) aux portails législatifs officiels et aux bases de jurisprudence pour **l'Union européenne et la CEDH** (première instance, cours d'appel / juridictions régionales et juridictions suprêmes ou constitutionnelles).

**Gratuit & Open Source (MIT) · Lecture seule sur portails officiels · Aucune clé API · Aucun accès aux fichiers personnels · Désinstallation en 1 clic**

---

## Installation facile (Sans programmation, sans ZIP)

> [!TIP]
> **Installateur 1 fichier (Sans extraction ZIP) :** Téléchargez simplement le fichier unique ci-dessous et double-cliquez dessus — il télécharge automatiquement tous les fichiers nécessaires depuis GitHub en arrière-plan et ouvre l'assistant visuel. Le ZIP complet (`<> Code` → `Download ZIP`) reste disponible en option.
> - **Windows:** [`Click_Here_To_Install_Windows.bat`](https://github.com/jurisatlas/eu-legal-mcp/raw/main/Click_Here_To_Install_Windows.bat)
> - **macOS:** [`Click_Here_To_Install_Mac.command`](https://github.com/jurisatlas/eu-legal-mcp/raw/main/Click_Here_To_Install_Mac.command)
> - Vous travaillez sur plusieurs pays ? Utilisez l'**[Installateur multi-pays unifié (jurisatlas/cli)](https://github.com/jurisatlas/cli)** ou le **[serveur unifié (jurisatlas-mcp)](https://github.com/jurisatlas/jurisatlas-mcp)**.

1. **Télécharger 1 fichier :** Cliquez sur le lien Windows (`.bat`) ou macOS (`.command`) ci-dessus (ou sur le ZIP complet en option).
2. **Double-cliquer pour lancer :** Le lanceur autonome récupère automatiquement les fichiers à jour depuis GitHub en arrière-plan et ouvre l'assistant graphique.
3. **Connecter vos applications IA :** Vérifiez vos applications détectées automatiquement (Claude Desktop & Claude Code CLI, Cursor, VS Code (GitHub Copilot / Cline / Roo Code), Windsurf, Google Antigravity & Gemini CLI, LM Studio, OpenAI Codex CLI, and Continue.dev), cliquez sur **Install to Selected AI Clients**, puis redémarrez votre application IA.

**Note pour ChatGPT Desktop / Web et Claude Web :** Ces applications utilisent une URL MCP HTTPS distante (`--transport streamable-http`, voir ci-dessous).

### Connexion par lien MCP ou JSON

- **1-Click Links & Claude `.mcpb`:** [jurisatlas.github.io](https://jurisatlas.github.io) (Cursor `cursor://`, VS Code `vscode:mcp/`, Claude Desktop `.mcpb`).
- **Local MCP JSON (`uvx`):** `eu-legal-mcp` via `https://github.com/jurisatlas/eu-legal-mcp/archive/refs/heads/main.zip` (see Developer Reference below; no Git required).
- **Remote HTTPS MCP (`https://.../mcp`):** `eu-legal-mcp --transport streamable-http --host 0.0.0.0 --port 8000` or 1-click deploy on FastMCP Cloud / Render via [`jurisatlas-mcp`](https://github.com/jurisatlas/jurisatlas-mcp).

<details>
<summary><b>Alerte de sécurité Windows SmartScreen ou macOS Gatekeeper ? (Normal & Sûr)</b></summary>

- **Windows (SmartScreen) :** Cliquez sur **Informations complémentaires** → **Exécuter quand même**.
- **macOS (Gatekeeper / Sequoia) :** Ouvrez **Réglages Système → Confidentialité et sécurité**, descendez puis cliquez sur **Ouvrir quand même**.
- *Pourquoi cette alerte apparaît-elle ?* Les scripts open source non signés déclenchent par défaut l'avertissement du système. L'intégralité du code est publique et vérifiable.

</details>

**Sécurité & Désinstallation en 1 clic :** Cet outil fonctionne strictement en lecture seule sur les portails publics officiels et ne touche jamais vos documents personnels. Pour le supprimer proprement, relancez l'assistant et cliquez sur **Uninstall / Remove**.

---

## À essayer immédiatement : 3 exemples de requêtes

1. > Vérifie la référence `ECLI:EU:C:2023:123 or CELEX:32016R0679 (GDPR)` dans les registres officiels pour l'Union européenne et la CEDH, indique si elle correspond à un registre officiel vérifié, et résume la règle ou la décision.
2. > Recherche la législation applicable et la jurisprudence récente pour l'Union européenne et la CEDH sur une question juridique précise, avec les liens vers les portails officiels.
3. > Présente la hiérarchie judiciaire à 3 niveaux pour l'Union européenne et la CEDH pour un litige civil ou administratif et recherche des décisions récentes en appel.

---

## Hiérarchie juridictionnelle & Sources officielles

| Degré de juridiction | Juridictions couvertes |
|:---|:---|
| **1er degré (Première instance)** | National First-Instance Referring Courts (Article 267 TFEU Preliminary References) & EU Specialized Chambers |
| **2nd degré (Cours d'appel et juridictions régionales)** | General Court of the European Union (EGC — ECLI:EU:T:*) |
| **Juridictions suprêmes et constitutionnelles** | Court of Justice of the European Union (CJEU — ECLI:EU:C:*) & European Court of Human Rights (ECHR) |

- **EUR-Lex CELLAR REST/SPARQL API (EU Regulations, Directives, Decisions):** [https://eur-lex.europa.eu](https://eur-lex.europa.eu) (`eur-lex.europa.eu`, `publications.europa.eu`)
- **EUR-Lex CELLAR SPARQL & InfoCuria / ECHR HUDOC:** [https://curia.europa.eu](https://curia.europa.eu) (`curia.europa.eu`, `hudoc.echr.coe.int`, `eur-lex.europa.eu`)

---

<details>
<summary><b>Référence technique pour développeurs (6 outils MCP, 3 prompts, uvx, JSON manuel & Streamable HTTP)</b></summary>

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

> **Ceci n'est pas un avis juridique :** JurisAtlas est un outil d'aide à la recherche. Vérifiez toujours les textes et décisions sur les journaux officiels. Seul le statut `VERIFIED_OFFICIAL_RECORD` provient d'une API officielle structurée ; `UNCONFIRMED_WEB_MATCH` exige une vérification manuelle. ([MIT License](../LICENSE))
