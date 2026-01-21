# PhysGAT: Physics-Guided Heterogeneous Graph Attention Network

PhysGAT is a deep learning framework designed for precise environmental pollution source apportionment. It integrates geospatial physical priors—such as Digital Elevation Models (DEM), wind fields, and hydrological data—with Heterogeneous Graph Attention Networks (GATv2) to achieve quantitative contribution analysis from receptors back to pollution sources, including ensemble-based uncertainty quantification.

## 🌟 Core Features

- **Physics-Guided Architecture**: Integrates DEM elevation gradients, wind dynamics, and spatial transport models as prior constraints for the graph neural network.
- **Heterogeneous GATv2**: Explicitly distinguishes between Source and Receptor nodes, utilizing cross-domain attention mechanisms to learn complex, non-linear transport patterns.
- **Deep Ensemble Learning**: Trains multiple sub-models to provide robust mean predictions and confidence intervals (uncertainty quantification).
- **Explainable AI (XAI)**: Extracts real attention weights to visualize and validate the critical transport paths of pollutants.
- **End-to-End Analysis**: Built-in modules for Nemerow index calculation, pollution level assessment, and automatic generation of high-quality scientific visualizations.

## 📂 Project Structure

```text
physgat_project/
├── configs/            # Configuration files (Hydra/YAML)
├── data/               # Raw datasets (CSV)
├── src/                # Core source code
│   ├── model.py        # PhysGAT network architecture
│   ├── data_utils.py   # Graph construction & physical feature extraction
│   ├── ensemble.py     # Ensemble training logic
│   ├── visualization.py # Scientific visualization suite (Figures 1-18)
│   └── ...             # Utility and analysis modules
└── main.py             # Main entry point for training and prediction
```

## 🛠️ Installation

### Prerequisites

- Python 3.9+
- PyTorch 2.0+
- PyTorch Geometric (PyG)

### Setup Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/YourUsername/PhysGAT.git
   cd PhysGAT
   ```
2. Install dependencies:

   ```bash
   pip install -r physgat_project/requirements.txt
   ```
3. (Optional) Configure GDAL/PROJ environment:
   The project includes `proj_fix.py` to handle geographic library path compatibility across Windows and Linux.

## 🚀 Quick Start

### 1. Data Preparation

Place your source and receptor data in CSV format within the `physgat_project/data/` directory. Refer to the provided sample files for the required schema.

### 2. Run the Model

Start the full training, prediction, and analysis workflow using the default configuration:

```bash
python physgat_project/main.py
```

### 3. View Results

All analysis reports (Excel), prediction results (CSV), and scientific figures (PNG/PDF) are automatically saved in the `run_outputs/` directory.

## 📊 Visualizations

The project supports automatic generation of 18 types of scientific figures, including:

- Source-Receptor spatial distribution maps.
- Pollutant contribution heatmap matrices.
- Training loss evolution curves.
- Weight allocation consistency checks (XAI).

## 🤝 Contributing

Contributions are welcome!

1. **Report Bugs**: Use GitHub Issues to report any problems.
2. **Feature Requests**: Fork the repository, create a feature branch (`git checkout -b feature/AmazingFeature`), commit your changes, and open a Pull Request.
3. **Academic Citation**: If this project assists your research, please cite the corresponding paper (forthcoming).

## 📄 License

This project is licensed under the [MIT License](LICENSE).
