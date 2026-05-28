# 🌌 CellChat Galaxy Tool

[![Galaxy](https://img.shields.io/badge/Galaxy-Tool-blue.svg)](https://galaxyproject.org/)
[![Docker](https://img.shields.io/badge/Docker-Containerized-blueviolet.svg)](https://www.docker.com/)
[![R](https://img.shields.io/badge/R-Script-lightgrey.svg)](https://www.r-project.org/)

A reproducible and scalable wrapper to integrate the [CellChat](https://github.com/jinworks/CellChat) R package into the [Galaxy Ecosystem](https://usegalaxy.eu). 

This tool democratizes single-cell transcriptomics by allowing researchers without command-line experience to infer, analyze, and visualize cell-cell communication (CCC) networks from scRNA-seq data directly through a web-based Graphical User Interface (GUI).

## ✨ Key Features

* **No-Code Interface:** Fully abstracts the underlying R codebase via a standard Galaxy XML GUI.
* **Seurat v5 & v4 Compatibility:** Features a dynamic `tryCatch` extraction algorithm that automatically handles structural differences between Seurat v4 (`slots`) and Seurat v5 (`layers`).
* **Dependency Hell Resolved:** Uses a custom Docker container (via Mamba and CRAN) to solve historical compilation conflicts with the `NMF` package on modern architectures.
* **FAIR Compliant:** Ensures 100% computational reproducibility.

## 📁 Repository Structure

```text
cellchat_galaxy/
├── docker/
│   └── Dockerfile              # Miniforge3 base image with R, Mamba, and CellChat dependencies
├── scripts/
│   └── cellchat_wrapper.R      # The core R script connecting Galaxy inputs to CellChat logic
├── tool/
│   └── cellchat.xml            # Galaxy Tool definition (GUI, inputs, and outputs mapping)
└── README.md
