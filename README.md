# SiF-fish-Health
The clinical significance of blood biochemical parameters as a rapid diagnostic indicator of health status in salmonid aquaculture.
##  Author: 
Dr. Shahadate Rezvy, Research Fellow, University of West of Scotland
shahadate.rezvy@uws.ac.uk
##  Major Python Modules/Libraries: 
scikit-learn, shap, dash, Plotly, keras, seaborn, matplotlib, pandas
##  Installation: 
All the modules can be installed from either PyPI or conda-forge:

pip install 'module-name'

or

conda install -c conda-forge 'module-name'


##  Modelling Workflow : Explainable AI
![model](https://user-images.githubusercontent.com/31511385/115147556-66a8cb80-a053-11eb-86cf-ca1a6c60368e.png)


### Summary Plots Using SHAP Library: Biomarker expression in All samples
![Summary Plot](https://user-images.githubusercontent.com/31511385/115146931-a3bf8e80-a050-11eb-83bb-859ecc2ef547.png)

### Global Feature Importance Plots
![Biomarker Plot](https://user-images.githubusercontent.com/31511385/115146915-96a29f80-a050-11eb-9e40-9d65d7aca7fd.png)

Biomarkers: Top 4 from the summary plots for healthy fishes (ALDO, LACTA, CO2, NA/K)

Top 4 from Summary plots of unhealthy fishes (CK, CK MB, LDH, ALT).

A combined waterfall plot with global feature importance plot can show further on how many samples we may have under each decision node in our random forest models.

In the diagram shown above, with CK MB values alone, the model is capable of organizing/ separate more than 30% of its total observations to healthy and unhealthy. With further information on LDH increases the coverage/cumulative ratio to >50% and so on. 

###  Depndence Plots: Biomarker Range Identification
From the dependence plots, it is possible to identify biomarker ranges that are impacting the model positively or negatively based on the data the model has seen during training, for example, a CK MB value below 7K is showing some negative impact on the model as models positive case is Unhealthy by configuration. So some observations/samples are having more impact on the model than the others.
![Dependence plot](https://user-images.githubusercontent.com/31511385/115146945-b4700480-a050-11eb-9fca-91e3c07213c1.png)

Example Insight:
Based on the SHAP dependence plots, fishes, that were Healthy tend to have the following features:
CK MB < 10K;
LDH <1000;
NA/K > 150.
On the other hand, opposite may apply for most unhealthy cases:
CK MB > 10K;
have LDH >1000;
NA/K < 150.
From the waterfall plot these three conditions can separate out 60% of the observations in our dataset.


### Force Plots for individual fish health and explaining models prediction
![Force_Plots](https://user-images.githubusercontent.com/31511385/115146921-9b675380-a050-11eb-8859-704b4b95950b.png)
### Further Exploratory Analysis : Dashboads and bubble plots
![Bubble Plots](https://user-images.githubusercontent.com/31511385/115148783-0fa5f500-a059-11eb-8c69-75befb32bd7f.png)

### Unsupervised Explorlation: K-means and t-SNE for hybrid semi-supervised model development

![Cluster](https://user-images.githubusercontent.com/31511385/115149080-58aa7900-a05a-11eb-9807-e3581bd3a8e3.PNG)
With 3 clusters, we can assign cluster 2 and 3 as healthy with some unhealthy’s in them aand cluster 1 as unhealthy, which would lead to better accuracy in terms of cluster to supervised label alignment.
### UWS News/Related Link
https://www.uws.ac.uk/news/leading-research-at-uws-set-to-improve-fish-health-and-boost-aquaculture-sector/



