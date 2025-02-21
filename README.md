# Vanguard A/B Testing Project
## Project Overview
This project analyzes the impact of a new UI design on **user completion rates**, **error rates**, and **time to completion** for The Vanguard Group's online process. Using **A/B testing**, we compare a **Test Group** (new UI) against a **Control Group** (existing UI) to evaluate the effectiveness of the redesign.
## Objectives
The key research questions:
1. **Did the new UI help users complete the process faster?**
2. **Did the redesigned interface reduce user errors?**
3. **Did the new UI lead to higher completion rates?**
4. **Did the new UI provide at least a 5% improvement in completion rates (cost-effectiveness threshold)?**
## Data Sources
We used three primary datasets:
- **Client Profiles (`df_final_demo`)** – Age, gender, and account details to segment users.
- **Experiment Roster (`df_final_experiment_clients`)** – Identifies users assigned to the A/B test.
- **Digital Footprints (`df_final_web_data`)** – Logs user interactions and process steps.
## Methodology
### **Performance Metrics**
- **Completion Rate**: \( \frac{\text{visit_id reached “confirm” step}}{\text{Total visit_id that started}} \times 100\% \)
- **Mean Time Difference (Seconds)**: Average time taken to complete each process step.
- **Total Error Rate**: \( \frac{\text{Total count of step_regression}}{\text{Total count of process_step}} \times 100\% \)
- **Error Rate per Step**: \( \frac{\text{visit_id with at least one step regression}}{\text{Total visit_id that reached the step}} \times 100\% \)
### **Statistical Hypothesis Testing**
We conducted the following hypothesis tests:
#### **1. User Completion Rate** (One-Sided Proportion Z-Test)
- **H₀**: Completion Rate (Test) **≥** Completion Rate (Control)
- **H₁**: Completion Rate (Test) **<** Completion Rate (Control)
#### **2. Total Error Rate** (One-Sided Proportion Z-Test)
- **H₀**: Error Rate (Test) **≤** Error Rate (Control)
- **H₁**: Error Rate (Test) **>** Error Rate (Control)
#### **3. Total Time Taken** (Independent Welch’s t-test)
- **H₀**: Mean Time (Test) **≤** Mean Time (Control)
- **H₁**: Mean Time (Test) **>** Mean Time (Control)
#### **4. Completion Rate with Cost-Effectiveness Threshold**
- **H₀**: Completion Rate (Test) **≤** Completion Rate (Control) **+5%**
- **H₁**: Completion Rate (Test) **>** Completion Rate (Control) **+5%**
## Results
- **Completion Rate:** The **Test Group (58.52%) outperformed the Control Group (49.85%)**.
- **Error Rate:** The Test Group had a **higher error rate**, particularly in Step 1.
- **Time Taken:** The new UI took longer for some users, especially in earlier steps.
- **Cost-Effectiveness Threshold:** The Test Group **exceeded the +5% threshold**, proving the new UI is statistically beneficial.
| Group     | Total Sessions | Sessions with Confirm Step | Completion Rate |
|-----------|---------------|---------------------------|----------------|
| **Control** | 49,850       | 24,850                     | 49.85%         |
| **Test**    | 58,520       | 34,250                     | 58.52%         |
- **Z-Statistic:** **9.72** :marca_de_verificación_blanca:
- **P-Value:** **0.0000** :marca_de_verificación_blanca:
  *Conclusion: The new UI is significantly better than the control version.*
##  Visualizations
Our analysis was supported with **Tableau dashboards**:
- **Demographics Analysis**
- **Performance Per Step**
- **Major Success Indicators**
- **Error Rate Trends**
##  Business Conclusions
- **The new UI improved completion rates** but also led to **higher error rates and longer completion times**.
- **Older clients (70+) struggled**, with a completion rate drop to **38%**.
- **Step 1 had the highest error rate**, indicating possible confusion with the new UI.
##  Recommendations & Next Steps
:marca_de_verificación_gruesa: **Optimize the UI for faster navigation.**
:marca_de_verificación_gruesa: **Reduce error rate with real-time feedback & tooltips.**
:marca_de_verificación_gruesa: **Improve accessibility for older users (larger fonts, clearer navigation).**
:marca_de_verificación_gruesa: **Conduct further segmentation analysis & collect qualitative user feedback.**
##  Team Members
- **Lukas Günther**
- **Rebecca Woo**
- **Sandra Ngoing**
- **Víctor Ramírez**
