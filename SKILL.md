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

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:EU:C:2023:123 or CELEX:32016R0679 (GDPR)`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** National First-Instance Referring Courts (Article 267 TFEU Preliminary References) & EU Specialized Chambers
   - **Second Instance (Cantonal / Regional / Appellate):** General Court of the European Union (EGC — ECLI:EU:T:*)
   - **Supreme & Constitutional Instance:** Court of Justice of the European Union (CJEU — ECLI:EU:C:*) & European Court of Human Rights (ECHR)
   - **Primary Tiered Database:** EUR-Lex CELLAR SPARQL & InfoCuria / ECHR HUDOC (`https://curia.europa.eu`)
