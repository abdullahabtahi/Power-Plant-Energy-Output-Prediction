# Power Plant Energy Output Prediction

Predicting hourly net energy output of a Combined Cycle Power Plant using time-aware splits and tree-based ensemble models. 

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/14Nls7oSpJbg8mWsLRCRcfAyFDZD73-zP?usp=sharing)

## Overview

This project builds a machine learning model to forecast hourly net electrical energy output (PE, MW) for a Combined Cycle Power Plant using ambient conditions (AT, V, AP, RH). [page:4]
The goal is to support grid-commitment and operations planning by providing accurate, time-aware predictions that avoid information leakage. [page:4]

![Power Plant Energy Prediction Infographic](reports/Power%20Plant%20Energy%20Prediction%20Infographic.png)

## Dataset

- Source: Combined Cycle Power Plant (CCPP) dataset (UCI / Duke specialization). [page:4]  
- Size: 9,527 hourly records of plant operation. [page:4]  
- Features: AT (°C), V (cm Hg), AP (mbar), RH (%).  
- Target: PE – net hourly electrical energy output (MW). [page:4]

## Methodology

The notebook follows a CRISP-DM style workflow:

- Business Understanding: framing plant output prediction as a grid-commitment and penalty reduction problem. [page:4]
- Data Understanding: exploring 9.5k hourly records and the relationships between ambient conditions and output. [page:4]
- Data Preparation: enforcing a strict chronological Train–Validation–Test split (80/10/10) to avoid leakage. [page:4]
- Modeling: comparing Linear Regression vs Random Forest (150 trees) on the validation set. [page:4]
- Evaluation: reporting R², RMSE, and MAE on a held-out future test set. [page:4]
- Deployment / Next Steps: generating an executive dashboard and management summary for plant leadership. [page:4]

## Results

On the held-out test set, the Random Forest model achieves:

- R² ≈ 0.97 (explains about 96% of variance). [page:4]
- RMSE ≈ 3.12 MW. [page:4]
- MAE ≈ 2.30 MW (typical hourly error). [page:4]

Compared with a Linear Regression baseline, the Random Forest reduces validation RMSE by about 24%. [page:4]

![Executive Dashboard](reports/Executive%20Dashboard.png)

## How to run

1. Clone this repository:

   git clone https://github.com/abdullahabtahi/Power-Plant-Energy-Output-Prediction.git
   cd Power-Plant-Energy-Output-Prediction

2. Create a virtual environment and install dependencies:

   pip install -r requirements.txt

3. Download and place the CCPP dataset as CCPP_Data_(Cleaned).csv in the project root or data/

Open notebooks/power_plant_energy_output.ipynb in Jupyter or Colab and run all cells in order.

References
Pınar Tüfekci, “Prediction of full load electrical power output of a base load operated combined cycle power plant using machine learning methods,” International Journal of Electrical Power & Energy Systems, Volume 60, September 2014, Pages 126–140.

Heysem Kaya, Pınar Tüfekci, Sadık Fikret Gürgen, “Local and Global Learning Methods for Predicting Power of a Combined Gas & Steam Turbine,” Proceedings of the International Conference on Emerging Trends in Computer and Electronics Engineering (ICETCEE 2012), pp. 13–18, Dubai, 2012.