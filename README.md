# Arrest Probability Inference: Logistic Regression & Criminology

## Executive Summary
In criminal justice administration, understanding the structural factors that lead to an arrest is crucial for evaluating law enforcement performance and systemic biases. 

This repository contains an inferential data analysis of the Chicago Police Department Crime Dataset. Instead of utilizing pure predictive machine learning models, this project applies Logistic Regression to calculate the mathematical probability of an arrest based on the incident's primary type, location, and domestic status. By extracting "Odds Ratios," the model provides definitive, quantitative proof of how specific factors structurally increase or decrease the likelihood of an arrest.

## Tech Stack & Data Engineering
* **Language & Libraries:** Python, Pandas, Scikit-Learn, Seaborn, Matplotlib, Requests
* **Live Data Integration:** Configured a direct API pipeline using Socrata Query Language (SoQL) to fetch the most recent 100,000 crime records dynamically from the Chicago Data Portal, eliminating the need for static CSV files.
* **Methodology:** One-Hot Encoding, Logistic Regression, Log-Odds Exponentiation, and Forest Plot Visualization.

## The Analytical Pivot: Handling Class Imbalance
The initial classification report yielded a highly respectable 91% overall accuracy. However, a deeper clinical inspection revealed a fundamental reality of the criminal justice system: **Class Imbalance**. 

While the model exhibited a 99% recall for non-arrests, its recall for actual arrests was significantly lower (34%). This reflects the operational reality that the vast majority of reported crimes (e.g., historical theft, deceptive practices) do not result in an immediate arrest. 

Because the justice system is inherently imbalanced toward non-arrests, deploying this model as a pure "predictive black-box" would be analytically flawed. Therefore, the focus of this project pivots from *prediction* to *inference*.

## Key Inferential Findings (Odds Ratios)
By exponentiating the logistic coefficients, we calculated the Odds Ratio (OR) for each feature and visualized them using an epidemiological Forest Plot:

* **High Probability Drivers (OR > 1):** Proactive policing scenarios (such as Narcotics interventions or Weapons violations) inherently result in immediate arrests, showing a massive mathematical increase in baseline arrest probability.
* **Low Probability Drivers (OR < 1):** Reactive reports filed long after the perpetrator has left the scene (such as Motor Vehicle Theft or Deceptive Practice) mathematically crash the likelihood of an immediate arrest.
* **Domestic Violence Protocols:** The model successfully
