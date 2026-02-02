# Candidate-Centric Election Forecasting Model

The presented candidate model uses individual candidate characteristics and historical data to predict election results.

## Notes

- Please note that the setup uses a fixed random seed. The impact of randomly assigned seeds has not been thoroughly analysed, but while testing with roughly 1,000 different seed values, I noticed that the number of correctly predicted candidates fluctuated between 140 and 160.
- Subsequently, a potential improvement would be to incorporate formal prediction intervals. Instead of point predictions, future iterations could use bootstrapping or ensemble modeling (running across multiple seeds) to generate a probability distribution for each candidate. This would move beyond a static "winner list" to provide a coverage metric and communicate the probabilistic likelihood of election for each candidate.

## Requirements

- **Python**: 3.10 or higher (tested with Python 3.13.5)
- **Dependencies**: Listed in `requirements.txt`

Key packages include:
- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computing
- `scikit-learn` - Machine learning algorithms
- `xgboost` - Gradient boosting framework
- `matplotlib` & `seaborn` - Data visualization
- `shap` - Model interpretability
- `jupyterlab` - Interactive notebook environment

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd candidate-model
   ```

2. **Create a virtual environment**
   ```bash
   python3 -m venv .venv
   ```

3. **Activate the virtual environment**
   ```bash
   source .venv/bin/activate
   ```

4. **Install dependencies**
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

## Usage

After installation, launch Jupyter Lab to explore the notebooks:

```bash
# Launch Jupyter Lab
jupyter lab
```

## What's Included
This repository contains:
- **Ex ante forecast analysis** (`ex-ante-forecast-2023.ipynb`) - The model used to predict the 2023 Finnish Parliamentary Elections before the elections took place
- **Candidate model notebook** (`candidate-model.ipynb`) - Notebook for analyzing and adjusting the candidate model
- **Training data** - Historical candidate and election data used for model development
- **Candidate information** - Comprehensive dataset of candidate characteristics, names of candidates removed
- **Data generation documentation** - Process documentation for data preparation

## Feedback & Issues

Please don't hesitate to reach out if you find any problems or mistakes in the code or manuscript. My contact information is available in the published manuscript.
