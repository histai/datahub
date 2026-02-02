# HistAI Pathology Datahub Skills

This file provides skill definitions for OpenAI Codex and other agents that support the AGENTS.md format.

---

## Cohort Builder

**Skill ID:** `cohort_builder`  
**Path:** `skills/cohort_builder/SKILL.md`

### Description

Search pathology cases by diagnosis, organ, age, and stains. Filter datasets (benign/malignant, cancer types), build research cohorts, and export whole slide images with clinical and technical metadata.

### Prerequisites

- Active subscription on [CellDX platform](https://celldx.hist.ai)
- 2FA authentication enabled
- API Key generated from Profile Settings → API Keys

### Environment Setup

```bash
export HISTAI_API_KEY="your-api-key"
```

### When to Use This Skill

Use this skill when you need to:
- Search for pathology cases by clinical criteria (diagnosis, organ, cancer type)
- Filter datasets by technical parameters (stains, magnification, scanner)
- Build training cohorts for machine learning models
- Export whole slide images (WSI) and metadata for research
- Calculate dataset distributions and statistics
- Manage billing and cohort costs

### ⚠️ Financial Safety & Confirmation

**Purchasing a cohort involves real financial charges and is non-refundable.**

AI agents **MUST** receive explicit confirmation from the user (a clear "YES" or "PROCEED") before executing any payment (`/pay`) command. Agents should always present the total estimated cost and cohort contents to the user before asking for confirmation.

### Key Capabilities

1. **Case Search & Discovery**
   - Search by diagnosis, organ, age, gender, ICD-10
   - Filter by stain types (H&E, IHC markers like HER2, ER, Ki-67)
   - Search within pathology protocols (macro, micro, conclusion)
   - Get available filter values and counts

2. **Cohort Management**
   - Create named cohorts from search results
   - Add or remove cases and slides
   - Optimize costs by selecting specific slides
   - Track cohort status and payment

3. **Data Export**
   - Download whole slide images
   - Export clinical and technical metadata
   - Manage download windows and refresh expired links

4. **Billing & Pricing**
   - Check account balance
   - View transaction history
   - Volume discounts based on cohort size

### API Base URL

```
https://prod.celldx.net
```

### Authentication

All requests require the `X-API-KEY` header:

```bash
X-API-KEY: $HISTAI_API_KEY
```

---

For detailed API documentation, examples, and best practices, refer to `skills/cohort_builder/Skill.md`.
