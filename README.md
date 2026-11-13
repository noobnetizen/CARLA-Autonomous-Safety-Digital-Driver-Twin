# 🚗 CARLA Autonomous Safety Envelope & Digital Driver Twin Platform

An AI-powered autonomous driving telemetry, predictive hazard classification, and kinematic safety evaluation platform built on the **CARLA Simulator**. The application provides interactive dashboards for engineers, researchers, and students to log driving telemetry, replay routes with PID-guided AI corrections, map speed-vs-curvature safety envelopes, and profile synthetic driver behaviors.

---

## 🚀 Simulation & Environment

* **Simulator Engine:** CARLA Simulator (`localhost:2000`)
* **Supported Dashboards:** Pygame Unified Smart Dashboard (`1280×800`), RL Safety Envelope & DDT Profiler (`1280×800`), and CustomTkinter Native Telemetry Dashboard (`1100×680`).

The platform runs locally alongside the CARLA Unreal Engine server (`CarlaUE4.exe`) and supports real-time sensor streaming, dynamic weather switching, and NPC traffic simulation.

---

## 📖 About the Project

Validating Advanced Driver Assistance Systems (ADAS) and autonomous driving policies requires continuous testing across varying road geometries, surface friction levels, and driver styles. Traditional testing in physical environments is costly and dangerous when probing safety limits.

This project leverages **Machine Learning**, **Control Theory (PID)**, and **Vehicle Dynamics** inside CARLA to evaluate driving risk and compare human driving against AI-assisted control.

The autonomous safety workflow includes:

* Multi-Sensor Telemetry & GPS Waypoint Logging
* Menger Road Curvature & Tire Friction Utilization Estimation
* 11-Component Real-Time Kinematic Safety Envelope Evaluation
* Random Forest Hazard, Speed, and Lane-Drift Classification
* Upsampled PID Waypoint Replay with Live Traffic Avoidance
* Synthetic Digital Driver Twin (DDT) Behavioral Profiling

The user interfaces were built using **Pygame** and **CustomTkinter**, while the machine learning and vehicle dynamics pipelines were developed using **Python**, **Scikit-Learn**, and **NumPy**.

---

## 🧩 Key Features

✅ Manual Driving Mode with Live HUD & Telemetry Logging (`driving_data.csv`)

✅ PID-Guided Autonomous Waypoint Replay with Live Traffic Braking

✅ Random Forest Collision, Speed & Lane-Drift Risk Prediction

✅ Real-Time 11-Component Kinematic Safety Envelope Scoring

✅ Menger Curvature & Corner-Entry Physics Risk Estimation

✅ Live Speed-vs-Curvature Safety Boundary Scatter Mapping

✅ Digital Driver Twin (DDT) Profiler (Conservative, Normal, Aggressive, Inconsistent)

✅ Forward Radar Time-to-Collision (TTC) & Lane Offset Monitoring

✅ Dynamic Weather Presets (Clear, Cloudy, Rainy, Foggy, Night, Stormy) with Friction Scaling

✅ Multi-Camera Perspectives (Chase, Driver, Top) & NPC Traffic Spawning

---

## 🛠️ Tech Stack

### Simulation & Vehicle Physics
* CARLA Simulator Python API (`carla`)
* Menger Curvature & Kinematic Dynamics

### Machine Learning & Control
* Python 3.7+
* Scikit-Learn (`RandomForestClassifier`, `StandardScaler`)
* NumPy
* PID Steering Controller & Low-Pass Signal Filtering

### User Interface & Computer Vision
* Pygame (Neon Smart Dashboard & Safety Envelope Visualizer)
* CustomTkinter & Tkinter (Native Radar & Advisory Dashboard)
* OpenCV (`cv2`)
* Pillow (`PIL`)

### Development Tools
* VS Code
* CARLA Unreal Engine (`CarlaUE4.exe`)

---

## 🧠 Learning Outcomes

Through this project, I gained practical experience in:

* Autonomous Vehicle Telemetry & Sensor Fusion (RGB Camera, Radar, Collision, Lane Invasion)
* Vehicle Kinematics, Menger Road Curvature & Tire Friction Utilization Modeling
* 11-Component Weighted Safety Envelope Design
* PID Controller Tuning & Trajectory Waypoint Upsampling
* Supervised Machine Learning Classification with Random Forests
* Real-Time Multi-Threaded GUI Development in Pygame & CustomTkinter
* Behavioral Driver Profiling via Digital Driver Twins

---

## 🧰 Installation & Setup

### Clone Repository
```bash
git clone https://github.com

cd CARLA-Autonomous-Safety-Digital-Driver-Twin
```

### Create Virtual Environment
```bash
python -m venv venv

venv\Scripts\activate
```

### Install Dependencies
```bash
pip install pygame carla numpy scikit-learn customtkinter opencv-python pillow
```

### Start CARLA Server
Launch `CarlaUE4.exe` and ensure the simulation server is listening on `localhost:2000`.

### Run Applications

**1. Unified Manual Drive & AI Replay Dashboard:**
```bash
python carla_unified_dashboard.py
```

**2. RL Safety Envelope & Digital Driver Twin Dashboard:**
```bash
python carla_rl_safety_dashboard.py
```

**3. Native Radar & Advisory Dashboard:**
```bash
python carla_native_dashboard.py
```

---

## 📁 Project Structure

```text
CARLA-Autonomous-Safety-Digital-Driver-Twin
│
├── data
│   ├── driving_data.csv
│   └── rl_safety_data.csv
│
├── models
│   └── driving_model.pkl
│
├── carla_unified_dashboard.py
├── carla_rl_safety_dashboard.py
├── carla_native_dashboard.py
├── safety_advisor.py
│
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
```

---

## 📊 Safety Evaluation & ML Models

The platform combines a deterministic physics-based safety evaluator with supervised ML models:

### 11-Component Safety Envelope Evaluator
Evaluates frame-by-frame risk (`SAFE`, `WARNING`, `UNSAFE`) across weighted metrics:
* Collision Events & Obstacle Proximity
* Lane Departure Offset & Yaw Stability
* Lateral/Longitudinal Acceleration & Jerk
* Tire Friction Utilization & Curve-Entry Physics ($\frac{v^2 \kappa}{\mu g}$)
* Time-to-Collision (TTC) & Speed Limit Compliance

### Random Forest Risk Classifiers
Three `RandomForestClassifier` models trained on normalized driving telemetry (`speed`, `throttle`, `brake`, `steer`, `weather`, `rain`, `fog`, `num_vehicles`):
* **Collision Risk Classifier** (`Safe`, `Warning`, `Danger`)
* **Speed Advisory Classifier** (`Slow Down`, `Maintain`, `Accelerate`)
* **Lane-Drift Classifier** (`Lane OK`, `Lane Drift`)

---

## 📈 Human vs. AI & Digital Driver Twin Analytics

The dashboards provide real-time and post-run comparative analytics to evaluate driving safety and efficiency:

### Benefits:
* Side-by-Side Human vs. AI Telemetry Comparison (Max/Avg Speed, Steer Jerk, Fuel Saved, Safety Score)
* Live GPS Minimap with Red/Orange Mistake Markers
* Real-Time Speed-vs-Curvature Boundary Visualization
* Quantitative Risk Exposure Profiling Across Four Driver Personas

---

## 🙌 Contributions

Contributions, issues, and feature requests are welcome! Feel free to fork this repo and submit a pull request.

---

## 🧑‍💻 Developed by

**R.Krishnan**

Machine Learning & Data Analytics Enthusiast

🔗 GitHub: https://github.com/noobnetizen

🔗 LinkedIn: https://www.linkedin.com/in/krishnan-r-8697771b6/
