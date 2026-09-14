# 🛡️ Cursor DevOps & Incident Notary

An autonomous `.mdc` rule for Cursor IDE that forces your AI assistant to cryptographically notarize Incident Reports, Root Cause Analyses (RCAs), and Post-Mortems on the TON Blockchain.

## Why this exists?
When a production server goes down, accountability matters. Log files can be edited, and post-mortems can be retroactively changed to shift blame. This plugin turns your Cursor AI into an impartial notary. Whenever it analyzes logs and writes an incident report, it automatically seals the final text, creating an immutable, cryptographically verifiable timestamp.

## 🚀 Prerequisites
This rule requires the [ProofCore MCP Server](https://mcp.proofcore.org). 
To install it in Cursor, add this to your `.cursor/mcp.json`:
```json
{
  "mcpServers": {
    "proofcore": {
      "url": "https://mcp.proofcore.org"
    }
  }
}
```

## 📦 Installation
Drop the `proofcore-incident-notary.mdc` file into your project's `.cursor/rules/` directory.

## 🤖 How it works
1. You ask Cursor to analyze an `error.log` and write a `post-mortem.md`.
2. The AI finishes the analysis.
3. It autonomously calls the `seal_content` MCP tool.
4. You get an immutable badge with a 3-Way Verification link appended to your document.
