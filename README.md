# SCMCP

An MCP server for scRNA-Seq analysis with natural language!

## 🪩 What can it do?

- **IO module**: Read and write scRNA-Seq data with natural language
- **Preprocessing module**: Filtering, quality control, normalization, scaling, highly-variable genes, PCA, Neighbors,...
- **Tool module**: Clustering, differential expression, etc.
- **Plotting module**: Violin plots, heatmaps, dotplots
- **Cell-cell communication analysis**
- **Pseudotime analysis**
- **Enrichment analysis**

## ❓ Who is this for?

- Anyone who wants to do scRNA-Seq analysis using natural language!
- Agent developers who want to call scanpy's functions for their applications

## 🌐 Where to use it?

You can use scmcp in most AI clients, plugins, or agent frameworks that support the MCP:

- AI clients, like Cherry Studio
- Plugins, like Cline
- Agent frameworks, like Agno 

## 📚 Documentation

scmcphub's complete documentation is available at https://docs.scmcphub.org

## 🎬 Demo

A demo showing scRNA-Seq cell cluster analysis in an AI client Cherry Studio using natural language based on scmcp:

https://github.com/user-attachments/assets/93a8fcd8-aa38-4875-a147-a5eeff22a559

## 🏎️ Quickstart

### Install

Install from PyPI:
```bash
pip install scmcp
```

You can test it by running:
```bash
scmcp run
```

## 🚀 Running Modes

SCMCP provides two distinct run modes to accommodate different user needs and preferences:

### 1. Tool Mode

In tool mode, SCMCP provides a curated set of predefined functions that the LLM can select and execute.

**Advantages:**
- **Stable**: Predefined functions ensure consistent and reliable execution
- **Predictable**: Known behavior and expected outputs
- **Safe**: Controlled environment with validated operations

**Disadvantages:**
- **Limited flexibility**: Restricted to available predefined functions; you need to define new tools when you need customization functions

#### Usage

Running in terminal:
```bash
scmcp run --run-mode tool
```

Configure MCP client:
```json
{
  "mcpServers": {
    "scmcp": {
      "command": "/home/test/bin/scmcp",
      "args": ["run", "--run-mode", "tool"]
    }
  }
}
```

**Examples:**
- https://youtu.be/VM7G-VMNhOs
- https://youtu.be/D669c0EyNzE
- https://youtu.be/b45_6fJXEIQ

### 2. Code Mode

In code mode, SCMCP provides a Jupyter backend that allows the LLM to generate and execute custom code. Additionally, it can generate complete Jupyter notebooks containing executable code, analysis results, and visualizations.

This mode is based on the project: https://github.com/huang-sh/abcoder

**Advantages:**
- **Highly flexible**: Can create custom workflows and combine operations freely
- **Extensible**: Supports any Python code and external libraries
- **Interactive**: Real-time code execution and debugging capabilities

**Disadvantages:**
- **Less stable**: Code generation may vary each time

#### Usage

Running in terminal:
```bash
scmcp run --run-mode code
```

Configure MCP client:
```json
{
  "mcpServers": {
    "scmcp": {
      "command": "/home/test/bin/scmcp",
      "args": ["run", "--run-mode", "code"]
    }
  }
}
```

**Example:**
https://youtu.be/3jtXIeapslI

## 📝 Mode Comparison

| Feature | Tool Mode | Code Mode |
|---------|-----------|-----------|
| **Execution Method** | Predefined functions | Custom code generation |
| **Stability** | High (consistent) | Lower (variable) |
| **Flexibility** | Limited to available tools | Highly flexible |
| **Safety** | Controlled environment | Full Python execution |
| **Use Case** | Standard workflows | Custom analysis |
| **Learning Curve** | Easy to use | Requires Python knowledge |

## 🌐 Remote Deployment

For both modes, you can also run SCMCP remotely:

### Remote Setup

Start the server:
```bash
# Tool mode
scmcp run --transport shttp --port 8000 --run-mode tool

# Code mode
scmcp run --transport shttp --port 8000 --run-mode code
```

Configure your MCP client:
```json
{
  "mcpServers": {
    "scmcp": {
      "url": "http://localhost:8000/mcp"
    }
  }
}
```

## 🤝 Contributing

If you have any questions, welcome to submit an issue, or contact me (hsh-me@outlook.com). Contributions to the code are also welcome!

## Citing

If you use scmcp in your research, please consider citing the following works:

> Wolf, F., Angerer, P. & Theis, F. SCANPY: large-scale single-cell gene expression data analysis. Genome Biol 19, 15 (2018). https://doi.org/10.1186/s13059-017-1382-0

> Dimitrov D., Schäfer P.S.L, Farr E., Rodriguez Mier P., Lobentanzer S., Badia-i-Mompel P., Dugourd A., Tanevski J., Ramirez Flores R.O. and Saez-Rodriguez J. LIANA+ provides an all-in-one framework for cell–cell communication inference. Nat Cell Biol (2024). https://doi.org/10.1038/s41556-024-01469-w

> Badia-i-Mompel P., Vélez Santiago J., Braunger J., Geiss C., Dimitrov D., Müller-Dott S., Taus P., Dugourd A., Holland C.H., Ramirez Flores R.O. and Saez-Rodriguez J. 2022. decoupleR: ensemble of computational methods to infer biological activities from omics data. Bioinformatics Advances. https://doi.org/10.1093/bioadv/vbac016

> Weiler, P., Lange, M., Klein, M. et al. CellRank 2: unified fate mapping in multiview single-cell data. Nat Methods 21, 1196–1205 (2024). https://doi.org/10.1038/s41592-024-02303-9

