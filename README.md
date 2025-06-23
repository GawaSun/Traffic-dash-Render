### Live Demo: [https://traffic-dash-render-vbqsdvhakghyew5ppdxsxu.streamlit.app/]

# Traffic Behavior Dashboard with Machine Learning 

A comprehensive, interactive dashboard for analyzing, visualizing, and predicting traffic patterns in Lithuania (2017–2023). Built with **Streamlit**, integrated with a live traffic API, and powered by machine learning models, this project showcases data analysis/visualization, geospatial mapping, time series analytics, and predictive modeling skills.

---

## Project Overview

* **Interactive Web App**: Multi-tab Streamlit dashboard offering exploratory analysis, geospatial maps, calendar heatmaps, holiday comparisons, clustering, and forecasting.
* **Machine Learning**: Two trained models:

  * **Average Speed Predictor** (`avg_speed_model.pkl`)
  * **Traffic Volume Predictor** (`volume_model.pkl`)
* **Live Data Integration**: Real-time traffic intensity via REST API (`eismoinfo.lt/traffic-intensity-service`).
* **Data Source**: \~50 MB CSV of traffic counts (`traffic_data_approx_50MB.csv`), managed via Git LFS for smooth collaboration.

---

## Key Features

1. **Homepage & Summary**: Random data samples, descriptive statistics, and summary tables.
2. **Trend Analysis**: Histograms, line charts, and bar plots for speeds and volumes over days, months, and years.
3. **Geospatial Mapping**:

   * Static scatter-map of average traffic per road segment.
   * Live map of current traffic intensity (green/orange/red) with hover details.
4. **Clustering**: K‑Means clustering on road segments by speed & volume, visualized on a map.
5. **Holiday vs. Non-Holiday**: Box plots comparing traffic volumes on Lithuanian public holidays.
6. **Calendar Heatmap**: Monthly calendar grid showing daily vehicle counts, top-10 busiest days, and holiday annotations.
7. **Speed Behavior**: Seasonal analysis of speeding vs. compliant vehicles across major roads.
8. **Country & Direction Analysis**: Traffic breakdown by license-plate country and direction (N vs. T).
9. **Vehicle-Type Insights**: Contribution of different vehicle types to congestion on selected roads.
10. **Predictive Modeling**: User-input forms driving ML models to forecast average speed or volume under custom scenarios.

---

## Technologies & Libraries

* **Web & UI**: Streamlit, Plotly, Matplotlib, Seaborn, Calplot
* **Data Processing**: Pandas, NumPy, GeoPandas, Shapely
* **Geospatial**: PyProj, OpenStreetMap tiles
* **Machine Learning**: scikit-learn (KMeans, StandardScaler), LightGBM
* **Model Management**: Joblib
* **APIs & External Data**: `requests`, Lithuanian public holidays via `holidays` library, live REST API integration
* **Utilities**: Python 3.11, Git LFS, requirements managed in `requirements.txt`

---

## Getting Started

1. **Clone & Install**

   ```bash
   git clone <your-repo-url>
   cd <your-repo>
   pip install -r requirements.txt
   ```
2. **Set Runtime (Streamlit Cloud)**

   ```text
   # runtime.txt
   python-3.11.4
   ```
3. **Run Locally**

   ```bash
   streamlit run trafficdata.py
   ```

## Repository Structure

```text
├── trafficdata.py           # Main Streamlit app
├── traffic_data_approx_50MB.csv  # Raw traffic dataset (Git LFS)
├── avg_speed_model.pkl      # Pre-trained speed prediction model
├── volume_model.pkl         # Pre-trained volume prediction model
├── requirements.txt         # Project dependencies
├── runtime.txt              # Python version spec for deployment
└── README.md                # Project documentation
```

---

## Deployment

* **Streamlit Cloud**: Connect GitHub, ensure `runtime.txt` is in root, clear cache & deploy.
* **Render**: Define `Build Command: pip install -r requirements.txt` and `Start Command: streamlit run trafficdata.py`.
* **Docker**: (Optional) Containerize for reproducibility.

---

## Skills Demonstrated

* End-to-end data pipeline: ingestion, cleaning, caching, aggregation, and visualization.
* Geospatial transformations and mapping.
* Time-series analysis with pandas and calendar plotting.
* REST API integration and caching strategies.
* Clustering and supervised ML modeling.
* Productionizing Python apps with Streamlit and cloud deployment.
* Version control of large datasets via Git LFS.


