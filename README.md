# HistAI Pathology Datahub

A skills repository providing clean and secure integration between AI coding agents (Claude Code, OpenAI Codex, Gemini CLI) and the HistAI Whole Slide Image Data Hub.

## Overview

This repository provides:
- 🔍 **Search pathology cases** by diagnosis, organ, age, stains, and clinical criteria
- 📊 **Build research cohorts** for machine learning and clinical studies  
- 💾 **Export whole slide images (WSI)** with comprehensive metadata
- 💰 **Manage costs** with volume-based pricing and selective slide downloads

## Security & Access Requirements

To use these skills, you must:
1. Have an active subscription on our [CellDX platform](https://celldx.hist.ai)
2. Have **2FA authentication** enabled on your CellDX account
3. Generate an API Key from **Profile Settings → API Keys**

## Integration

This repository is compatible with **Claude Code**, **OpenAI Codex**, and **Gemini CLI**. Choose your preferred agent below:

### Claude Code

#### Quick Install (Recommended)

1. **Register this repository as a plugin marketplace:**
   ```
   /plugin marketplace add histai/datahub
   ```

2. **Install the Cohort Builder skill:**
   ```
   /plugin install cohort-builder@histai/datahub
   ```

3. **Configure your API key:**
   - Generate an API key from [CellDX Platform → Profile Settings → API Keys](https://celldx.hist.ai)
   - Set it as an environment variable:
     ```bash
     export HISTAI_API_KEY="your-api-key"
     ```

4. **Start using:**
   - Example: *"Search for breast cancer cases with HER2 IHC staining"*

#### Manual Installation (Alternative)

If you prefer local installation:

1. **Clone this repository:**
   ```bash
   git clone https://github.com/histai/datahub.git
   cd datahub
   ```

2. **Register as a local skill:**
   ```
   /plugin add-local
   ```
   Point to the `skills/cohort_builder/SKILL.md` file.

### OpenAI Codex

Codex automatically detects skills via the `agents/AGENTS.md` file.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/histai/datahub.git
   cd datahub
   ```

2. **Verify skills are loaded:**
   ```bash
   codex --ask-for-approval never "Summarize the current instructions."
   ```

3. **Configure API key:**
   ```bash
   export HISTAI_API_KEY="your-api-key"
   ```

For more details, see the [Codex AGENTS guide](https://developers.openai.com/codex/guides/agents-md).

### Gemini CLI

This repository includes `gemini-extension.json` for Gemini CLI integration.

1. **Install from GitHub:**
   ```bash
   gemini extensions install https://github.com/histai/datahub.git --consent
   ```

   Or install locally:
   ```bash
   git clone https://github.com/histai/datahub.git
   cd datahub
   gemini extensions install . --consent
   ```

2. **Configure API key:**
   ```bash
   export HISTAI_API_KEY="your-api-key"
   ```

3. **Start using:**
   - The Gemini CLI will automatically load the cohort_builder skill
   - Interact with the HistAI Datahub through natural language

See [Gemini CLI extensions docs](https://geminicli.com/docs/extensions/#installing-an-extension) for more help.

## Available Skills

### 🔬 Cohort Builder

Search pathology cases by diagnosis, organ, age, and stains. Filter datasets (benign/malignant, cancer types), build research cohorts, and export whole slide images with clinical and technical metadata.

**Full documentation:** [`skills/cohort_builder/SKILL.md`](skills/cohort_builder/SKILL.md)

## Repository Structure

```
datahub/
├── .claude-plugin/
│   └── marketplace.json          # Claude Code marketplace configuration
├── agents/
│   └── AGENTS.md                 # OpenAI Codex skill definitions
├── skills/
│   └── cohort_builder/
│       └── SKILL.md              # Main skill documentation
├── gemini-extension.json         # Gemini CLI extension configuration
└── README.md                     # This file
```

## API Access

- **Base URL:** `https://prod.celldx.net`
- **Authentication:** API Key via `X-API-KEY` header
- **Documentation:** See individual skill files for detailed API reference

## Support

For issues, custom data requests, or enterprise inquiries:
- 📧 **Sales:** sales@hist.ai
- 📚 **Documentation:** [skills/cohort_builder/SKILL.md](skills/cohort_builder/SKILL.md)
- 🌐 **Platform:** [https://celldx.hist.ai](https://celldx.hist.ai)

## Data Licensing

All Whole Slide Images (WSI) accessed through this API are distributed under the **HistAI Commercial License**.

- 📄 **License:** [HistAI Commercial License (DLA)](https://hist.ai/policies/dla/)
- 🔒 **Terms:** Review the Data Licensing Agreement before purchasing cohorts
- ⚖️ **Usage Rights:** Commercial and research use as specified in the DLA

## License

This repository and its code are provided under the [LICENSE](LICENSE) file. Note that the WSI data accessed through the API has separate licensing terms (see Data Licensing above).