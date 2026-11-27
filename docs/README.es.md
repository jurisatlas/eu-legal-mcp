[← All JurisAtlas Jurisdictions](https://github.com/jurisatlas) · [Unified Multi-Country Installer](https://github.com/jurisatlas/cli) · [English README](../README.md)

**Languages:** [English](../README.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | **Español** | [Italiano](README.it.md)

# Investigación jurídica oficial para tu asistente de IA — la Unión Europea y el TEDH (`eu-legal-mcp`)

Este servidor Model Context Protocol (MCP) gratuito y de solo lectura conecta tu asistente de IA (Claude Desktop & Claude Code CLI, Cursor, VS Code (GitHub Copilot / Cline / Roo Code), Windsurf, Google Antigravity & Gemini CLI, LM Studio, OpenAI Codex CLI, and Continue.dev) directamente con los portales legislativos oficiales y las bases de datos judiciales para **la Unión Europea y el TEDH** (primera instancia, tribunales de apelación / superiores y tribunales supremos o constitucionales).

**Gratuito y Código Abierto (MIT) · Solo lectura en portales oficiales · Sin claves API · No toca archivos personales · Desinstalación en 1 clic**

---

## Instalación sencilla (Sin programación, sin ZIP)

> [!TIP]
> **Instalador de 1 solo archivo (Sin descomprimir ZIP):** Descarga únicamente el archivo de abajo y haz doble clic: descarga automáticamente todos los archivos necesarios desde GitHub en segundo plano y abre el asistente visual. El ZIP completo (`<> Code` → `Download ZIP`) sigue disponible opcionalmente.
> - **Windows:** [`Click_Here_To_Install_Windows.bat`](https://github.com/jurisatlas/eu-legal-mcp/raw/main/Click_Here_To_Install_Windows.bat)
> - **macOS:** [`Click_Here_To_Install_Mac.command`](https://github.com/jurisatlas/eu-legal-mcp/raw/main/Click_Here_To_Install_Mac.command)
> - ¿Necesitas varios países? Usa el **[Instalador unificado multipaís (jurisatlas/cli)](https://github.com/jurisatlas/cli)** o el **[servidor unificado (jurisatlas-mcp)](https://github.com/jurisatlas/jurisatlas-mcp)**.

1. **Descargar 1 archivo:** Haz clic en el enlace de Windows (`.bat`) o macOS (`.command`) arriba (o descarga opcionalmente el ZIP completo).
2. **Doble clic para iniciar:** El lanzador autónomo descarga automáticamente los archivos actualizados desde GitHub en segundo plano y abre el asistente gráfico.
3. **Conectar tus aplicaciones de IA:** Revisa tus apps detectadas automáticamente (Claude Desktop & Claude Code CLI, Cursor, VS Code (GitHub Copilot / Cline / Roo Code), Windsurf, Google Antigravity & Gemini CLI, LM Studio, OpenAI Codex CLI, and Continue.dev), pulsa **Install to Selected AI Clients** y reinicia tu app de IA.

**Nota para ChatGPT Desktop / Web y Claude Web:** Estas aplicaciones usan una URL HTTPS MCP remota (`--transport streamable-http`, consulta abajo).

### Cómo conectar mediante enlace MCP o JSON

- **1-Click Links & Claude `.mcpb`:** [jurisatlas.github.io](https://jurisatlas.github.io) (Cursor `cursor://`, VS Code `vscode:mcp/`, Claude Desktop `.mcpb`).
- **Local MCP JSON (`uvx`):** `eu-legal-mcp` via `https://github.com/jurisatlas/eu-legal-mcp/archive/refs/heads/main.zip` (see Developer Reference below; no Git required).
- **Remote HTTPS MCP (`https://.../mcp`):** `eu-legal-mcp --transport streamable-http --host 0.0.0.0 --port 8000` or 1-click deploy on FastMCP Cloud / Render via [`jurisatlas-mcp`](https://github.com/jurisatlas/jurisatlas-mcp).

<details>
<summary><b>¿Aparece una alerta de Windows SmartScreen o macOS Gatekeeper? (Normal y seguro)</b></summary>

- **Windows (SmartScreen):** Haz clic en **Más información** → **Ejecutar de todas formas**.
- **macOS (Gatekeeper / Sequoia):** Ve a **Ajustes del Sistema → Privacidad y seguridad**, baja y haz clic en **Abrir de todos modos**.
- *¿Por qué ocurre esto?* Los scripts de código abierto sin firma comercial muestran esta alerta estándar del sistema operativo. Todo el código es público.

</details>

**Seguridad y desinstalación en 1 clic:** Funciona solo en modo lectura contra portales oficiales públicos y nunca accede a tus archivos personales. Para eliminarlo por completo, vuelve a abrir el instalador y pulsa **Uninstall / Remove**.

---

## Pruébalo ahora: 3 prompts listos para copiar

1. > Verifica la cita `ECLI:EU:C:2023:123 or CELEX:32016R0679 (GDPR)` en los registros oficiales de la Unión Europea y el TEDH, indica si se confirmó en una fuente oficial y resume la norma o resolución.
2. > Investiga la legislación aplicable y la jurisprudencia relevante en la Unión Europea y el TEDH sobre una cuestión jurídica concreta e incluye enlaces oficiales.
3. > Traza la jerarquía judicial de 3 niveles en la Unión Europea y el TEDH para un litigio civil o administrativo y busca resoluciones recientes de apelación.

---

## Jerarquía judicial y fuentes oficiales

| Instancia judicial | Órganos jurisdiccionales cubiertos |
|:---|:---|
| **Primera instancia** | National First-Instance Referring Courts (Article 267 TFEU Preliminary References) & EU Specialized Chambers |
| **Segunda instancia (Apelación y Tribunales Superiores)** | General Court of the European Union (EGC — ECLI:EU:T:*) |
| **Tribunales Supremos y Constitucionales** | Court of Justice of the European Union (CJEU — ECLI:EU:C:*) & European Court of Human Rights (ECHR) |

- **EUR-Lex CELLAR REST/SPARQL API (EU Regulations, Directives, Decisions):** [https://eur-lex.europa.eu](https://eur-lex.europa.eu) (`eur-lex.europa.eu`, `publications.europa.eu`)
- **EUR-Lex CELLAR SPARQL & InfoCuria / ECHR HUDOC:** [https://curia.europa.eu](https://curia.europa.eu) (`curia.europa.eu`, `hudoc.echr.coe.int`, `eur-lex.europa.eu`)

---

<details>
<summary><b>Referencia técnica para desarrolladores (6 herramientas MCP, 3 prompts, uvx, JSON manual y Streamable HTTP)</b></summary>

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

> **No constituye asesoramiento legal:** JurisAtlas es una herramienta de apoyo a la investigación. Comprueba siempre las fuentes en boletines oficiales. Solo `VERIFIED_OFFICIAL_RECORD` proviene de una API oficial; `UNCONFIRMED_WEB_MATCH` requiere verificación manual. ([MIT License](../LICENSE))
