# Wearable Sensor Human Activity Recognition — PAMAP2

A data analytics and machine learning case study using the **PAMAP2 Physical Activity Monitoring Dataset** to investigate how wearable sensor placement affects human activity recognition.

The project analyzes data from wrist, chest, and ankle IMUs alongside heart rate to classify six everyday activities:

**Sitting · Standing · Walking · Running · Ascending Stairs · Descending Stairs**

## 🎯 Project Questions

* Which sensor location is most effective for activity recognition?
* How do movement patterns differ across activities?
* Does heart rate provide information that motion sensors cannot?
* Can a model classify activities for subjects it has never seen during training?

## 🔬 Methodology

Following the **Ask → Prepare → Process → Analyze → Share → Act** framework:

* Cleaned and validated PAMAP2 sensor data
* Removed invalid/transient measurements and orientation columns
* Calculated acceleration magnitude for wrist, chest, and ankle sensors
* Performed exploratory and statistical analysis by activity and sensor location
* Engineered **102 statistical features** from 2.56-second signal windows
* Trained a **Random Forest classifier**
* Evaluated using **Leave-One-Subject-Out validation**
* Visualized activity patterns using charts, boxplots, and a confusion matrix

## 📊 Key Findings

* **Ankle sensors provided the strongest activity discrimination**, with a much larger acceleration range than chest or wrist sensors.
* **Chest acceleration alone was weak for activity recognition** because torso movement remains relatively stable across several activities.
* **Heart rate complemented motion sensors**, particularly for distinguishing sitting and standing.
* The Random Forest achieved approximately **91% accuracy** on subjects excluded from training.
* **Ankle gyroscope features** were among the most predictive signals, highlighting the importance of rotational motion for gait-related activities.
* **Ascending vs. descending stairs** remained a challenging classification problem.
  
<img width="1007" height="624" alt="Screenshot 2026-09-07 at 9 45 25 PM" src="https://github.com/user-attachments/assets/1c7444f0-f940-4883-b43d-6190b883540d" />

## 💡 Wearable Design Insights

The analysis suggests that:

* An **ankle-mounted IMU** can be highly effective for activity recognition.
* Motion sensing should be combined with **heart rate** when distinguishing low-movement activities.
* Stair classification may benefit from additional sensing such as a **barometer** or longer observation windows.
* Models should ultimately be validated on larger and more diverse free-living populations.

## 🛠️ Tools & Skills

**Python:** pandas · scikit-learn · matplotlib · seaborn
**Data:** PAMAP2 · IMU signals · heart rate
**Skills:** Data Cleaning · EDA · Feature Engineering · Statistical Analysis · Machine Learning · Data Visualization · Data Storytelling

## 📁 Dataset

**PAMAP2 Physical Activity Monitoring Dataset**
UCI Machine Learning Repository — collected by the German Research Center for Artificial Intelligence (DFKI).

[Dataset →] https://archive.ics.uci.edu/dataset/231/pamap2+physical+activity+monitoring

## ⚠️ Limitations

* Small sample size with 8 usable subjects
* Predominantly male participants aged 23–32
* Controlled laboratory protocol rather than free-living activity
* Potential heart-rate lag between consecutive activities
* Dataset collected in 2012 using older sensor hardware

## 🚀 Future Work

* Test additional machine learning models
* Compare subject-independent vs. subject-dependent performance
* Explore deep learning approaches for raw sensor signals
* Validate on larger and more diverse datasets
* Investigate real-time activity recognition for wearable applications

