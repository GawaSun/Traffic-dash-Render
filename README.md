- Live demo of app: https://traffic-dash-render.onrender.com
Currently facing issues on RENDERs free option because my project file is too large. Will find a fix soon. 
The project can be ran locally with streamlit. If you are Lithuanian, or curious by nature you may find it worth the effort.

# Traffic Behavior Dashboard with Machine Learning

This project presents an interactive dashboard built using Streamlit to analyze and predict traffic behavior using a real-world traffic dataset. The original dataset was quite large, so efficient techniques were employed for model training and deployment. The dashboard includes two machine learning models:

- `avg_speed_model.pkl`: Predicts average speed of vehicles
- `volume_model.pkl`: Predicts traffic volume (number of vehicles)

Both models are trained using a combination of numerical and categorical features, including derived features like 'Road_Type', and are visualized through a user-friendly interface.

## Features

- Predict average speed and traffic volume based on user inputs
- Interactive map visualization
- Clean UI for interpreting traffic patterns
- Efficiently trained models capable of handling large datasets
- Utilizes derived 'Road_Type' for more accurate predictions.

## Technologies Used

- Python
- Pandas
- scikit-learn
- Streamlit
- joblib (for saving/loading models)
- Plotly (for interactive visualizations)
- geopandas (for mapping)
-`LightGBM` (for efficient model training)
## Files in This Repository

- `trafficdata.py`: Main Streamlit app containing the dashboard logic
- `traffic_data_approx_50MB.csv`: Full dataset (managed with Git LFS) used for model training and potentially for dashboard analysis.
- `avg_speed_model.pkl`: Trained model to predict average speed
- `volume_model.pkl`: Trained model to predict number of vehicles
- `requirements.txt`: Lists all Python dependencies for deployment.
- `README.md`: This documentation file

## How to Run the Project

### Prerequisites

- Git and Git LFS installed (for cloning and handling large files)
- Python 3.9+ installed

### Option 1: Run Locally

1.  **Clone this repository (ensure Git LFS is installed and active):**
    ```bash
    git clone your-repository-url
    cd your-repository-name
    ```
2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Run the Streamlit app:**
    ```bash
    streamlit run trafficdata.py
    ```

### Option 2: Run on Google Colab (for Development/Retraining)

1.  **Upload all project files** (including `trafficdata.py`, `traffic_data2.csv`, `avg_speed_model.pkl`, `volume_model.pkl`, and `requirements.txt`) to your Colab session.
2.  **Ensure correct package versions:**
    ```python
    !pip install -r requirements.txt --force-reinstall
    ```
3.  **Run your Streamlit app from Colab:**
    ```python
    !streamlit run trafficdata.py --server.port 8501 --server.headless true
    # You might need ngrok for a public URL if not deploying to Render directly.
    # from pyngrok import ngrok
    # public_url = ngrok.connect(port='8501')
    # print("Streamlit app URL:", public_url)
    ```

### Option 3: Deploy to Render (Recommended for Production)

This project is configured for easy deployment to Render.

1.  **Ensure all files are committed to your GitHub repository**, including:
    * `trafficdata.py`
    * `avg_speed_model.pkl`
    * `volume_model.pkl`
    * `traffic_data2.csv` (tracked with Git LFS)
    * `requirements.txt`
2.  **Go to your Render Dashboard** (dashboard.render.com).
3.  **Create a New Web Service.**
4.  **Connect your GitHub repository.**
5.  **Configure the service with the following settings:**
    * **Runtime:** `Python 3`
    * **Build Command:** `pip install -r requirements.txt`
    * **Start Command:** `streamlit run trafficdata.py`
    * Choose your desired **Plan Type** (consider a paid plan if you encounter memory issues with `traffic_data2.csv` on the free tier).
6.  **Click "Create Web Service"** and monitor the deployment logs. Once deployed, Render will provide your live application URL.