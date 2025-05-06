# GDD Calculator and Drying Algorithm
**An interactive Jupyter Notebook that fetches daily temperature data from the Visual Crossing Weather API, computes Growing Degree Days (GDD) by various methods, and predicts crop drying progress using a field drying model.**

## Repository Structure

```
GDD_calculator_and_Drying_Algorithm/
├── GDD_Calculation_and_Drying_Algorithm.ipynb   # Main notebook with code and UI
├── requirements.txt                            # List of required Python packages
├── README.md                                   # Project documentation (this file)
└── LICENSE                                     # MIT open source license
```

## Installation and Setup

**1. Clone the repository:**

```
git clone https://github.com/ahjm59/GDD_calculator_and_Drying_Algorithm.git
cd GDD_calculator_and_Drying_Algorithm
```

**2. Create and activate a virtual environment:**  

```
python -m venv venv
# macOS/Linux
source venv/bin/activate
# Windows
venv\\Scripts\\activate
```

**3. Install dependencies:**

```
pip install -r requirements.txt
jupyter nbextension enable --py widgetsnbextension
```

**4. Configure API Key:**

  a) Sign up at https://www.visualcrossing.com to obtain a free API key.
  
  b) Open the notebook, and set:
```
API_KEY = "YOUR_API_KEY_HERE"
```

**5. Launch Jupyter Notebook:**
```
jupyter notebook
```
Then open GDD_Calculation_and_Drying_Algorithm.ipynb.


## Dependencies

The project relies on the following Python packages

  a) pandas
  
  b) plotly
  
  c) ipywidgets
  
  d) requests
  
  e) python-dateutil

You can install them manually:
```
pip install pandas plotly ipywidgets requests python-dateutil
```

## Usage

1. Run all cells in the notebook to initialize the UI.

2. Input controls include:

  a) City and State text fields
  
  b) Start Date & End Date (YYYY‑MM‑DD)
  
  c) GDD Method dropdown
  
  d) Base Temperature (T_base)
  
  e) Use Modified? checkbox (toggles T_lower & T_upper)
  
  f) Drying Parameters: initial moisture (%), target moisture (%), drying rate constant

3. Click Get Data & Calculate.

4. Output:

  a) Interactive Plotly chart showing cumulative GDD (primary y-axis)
  
  b) Estimated moisture content over time (secondary y-axis)
  
  c) Hover for detailed values; zoom and pan as needed.

## Code Overview

a) Data Retrieval: fetch_weather_data_from_api() builds the URL, fetches CSV, and returns a DataFrame.

b) GDD Calculations: Functions for each method plus optional modified logic.

c) Drying Algorithm: Implements the Rotz & Chen (1985) field drying model to project moisture loss.

d) UI: ipywidgets Text, Dropdown, Checkbox, Button controls with dynamic show/hide of thresholds.

e) Visualization: Plotly Express for responsive, interactive line charts.

## Customization

a) Widget Styling: Adjust layout (width, margin, border, background_color) or apply custom CSS.

b) Chart Themes: Use Plotly templates (plotly_dark, ggplot2) or specify color_discrete_sequence and line_shape for different looks.

c) Algorithm Extensions: Add weather variables (humidity, solar radiation) or support crop-specific models.

## Contributing

a) Fork the repo and create a feature branch

b) Commit changes and push to your fork

c) Submit a pull request for review

## Refrences

a) Rotz, C.A. & Chen, Y. (1985). Alfalfa Drying Model for the Field Environment. Transactions of the ASAE, 28(6), 1687–1672. https://doi.org/10.13031/2013.32500

## License
This project is licensed under the MIT License. See the LICENSE file for details



