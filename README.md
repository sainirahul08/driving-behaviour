
# Driving Behaviour Pattern Analysis in Telematics Data Using K-Means Clustering  

## 📌 Project Overview  
This project analyzes **driving behaviour patterns** using telematics data and **K-Means clustering**. By extracting features such as speed, acceleration, distance, and idle time, we identify distinct driving styles. The clustering approach helps segment drivers into meaningful groups that can be useful for **fleet management, insurance analytics, and road safety insights**.  

---


## ⚙️ Workflow  

1. **Data Preprocessing**  
   - Dropped unnecessary columns (`telematics_id`, `fuel_lifetime`, etc.)  
   - Converted timestamps to datetime format  
   - Handled missing values and duplicates  
   - Segmented into driving sessions (time gap > 5 min)  

2. **Feature Engineering**  
   - **Average Speed** (considering only moving time)  
   - **Maximum Speed**  
   - **Average Acceleration**  
   - **Total Distance** (using odometer or Haversine formula)  
   - **Idle Fraction** (time spent at zero speed)  

3. **Clustering Approach**  
   - Standardized features using **StandardScaler**  
   - Applied **K-Means clustering** with `k` values from 2–10  
   - Evaluated with **Elbow Method** and **Silhouette Score**  
   - Selected **k = 3** for optimal balance between separation and interpretability  

4. **Visualization**  
   - PCA for 2D representation of clusters  
   - Scatter plots with **Seaborn** to show driver groupings  

---

## 📊 Results  

### Why **k = 3**  
- Elbow method shows a clear bend at `k=3`  
- Silhouette score remains strong at `k=3`  
- Provides well-separated and interpretable clusters  

### Cluster Interpretations  
- **Cluster 0 – Fast-paced and Long-Haul Driving**  
  - High speeds, minimal idling  
  - Indicates long-distance or highway driving  
  - May imply higher fuel efficiency but also higher wear and risk  

- **Cluster 1 – Slow and Idle-Prone**  
  - Low speeds, frequent idling  
  - Suggests congestion-prone or stop-heavy routes  
  - Lower safety risks but less efficient vehicle usage  

- **Cluster 2 – Moderate and Mixed-Pattern**  
  - Balanced speed, acceleration, and idle patterns  
  - Reflects typical **urban/suburban driving**  
  - Mix of stop-and-go with moderate cruising  

---

## 📂 Repository Structure  

```
├── data/                 # Raw telematics dataset (CSV)
├── notebooks/            # Jupyter Notebook / Scripts
├── images/               # Plots (Elbow, Silhouette, PCA clusters)
├── requirements.txt      # Required dependencies
├── main.py               # Main Python script (analysis + clustering)
└── README.md             # Project documentation
```

---


## 🛠️ Technologies Used  
- **Python** (pandas, numpy, scikit-learn, matplotlib, seaborn)  
- **Haversine** (distance calculation)  
- **PCA** (dimensionality reduction)  
- **K-Means Clustering** (unsupervised learning)  

---

## 📚 References  
- [Comprehensive Guide to K-Means Clustering – Analytics Vidhya](https://www.analyticsvidhya.com/blog/2019/08/comprehensive-guide-k-means-clustering/)  
- [Silhouette Score – Scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.silhouette_score.html)  
- [Haversine Distance – PyPI](https://pypi.org/project/haversine/)  
- [PCA + K-Means Tutorial – 365 Data Science](https://365datascience.com/tutorials/python-tutorials/pca-k-means/)  

---

## 🎯 Future Improvements  
- Compare K-Means with other clustering methods (DBSCAN, Gaussian Mixture Models)  
- Incorporate weather and traffic data for deeper insights  
- Develop a dashboard for real-time driver behaviour monitoring  

---

🔥 **This project demonstrates how machine learning can uncover hidden driving behaviour patterns, useful for fleet optimization, insurance, and road safety.**
