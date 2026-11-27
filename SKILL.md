---
name: eu-legal-mcp-skill
description: Official European Union & ECHR (EU) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# European Union & ECHR Legal Research & Multi-Tier Case Law Skill (`eu-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **European Union & ECHR (EU)**.

## Verification & Research Rules

1. **Honest Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:EU:C:2023:123 or CELEX:32016R0679 (GDPR)`). Clearly distinguish `VERIFIED_OFFICIAL_RECORD` (`official_registry_api`) from `UNCONFIRMED_WEB_MATCH` (`web_search_fallback`) and surface any `warnings`.
2. **Multi-Tier Judicial Coverage:**
   - **Tier 1 — First Instance:** National First-Instance Referring Courts (Article 267 TFEU Preliminary References) & EU Specialized Chambers
   - **Tier 2 — EU General Court (EGC):** General Court of the European Union (EGC — ECLI:EU:T:*)
   - **Tier 3 — Supreme & Constitutional:** Court of Justice of the European Union (CJEU — ECLI:EU:C:*) & European Court of Human Rights (ECHR)
   - **Primary Tiered Database:** EUR-Lex CELLAR SPARQL & InfoCuria / ECHR HUDOC (`https://curia.europa.eu`)
3. **Built-in MCP Prompts:** Leverage `verify_citations_in_draft`, `research_statute_and_precedent`, and `map_court_hierarchy`.
