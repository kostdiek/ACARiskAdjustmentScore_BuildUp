# ACARiskAdjustmentScore_BuildUp
Code to calculated our ACA members Risk Score as a function of time. The code breaks down the risk score by its components (demographic, diagnosis code, pharmacy NDC, and medical HCPCs).

The Affordable Care Act has built within it something similar to how Medicare is operated. 
Briefly, there is a set of medical conditions that are deemed "important" enough to be indicative of a member's overall health and their
medical claims cost. Typical examples would include conditions such as asthma, cancer, diabetes, among many others. Each condition may have 
multiple diagnosis codes that map to that condition - or to a certain severity of that condition. Each condition then has a coefficient
assigned to it; the higher the coefficient, the higher that medical cost is expected to be for the condition and that member. A member's 
demographics are also part of the equation as well, such as age, gender, and enrollment duration. 

Each year, the Center for Medicare and Medicaid publishes a new model - new coefficients for conditions, new conditions where needed, etc. 
The model expects to take in the following tables of information:

1. Person - Demographic information for each eligible member,
2. Diagnosis - Diagnosis Codes billed on medical claims for our members,
3. HCPCs - HCPCs Codes billed on medical claims for our members, and
4. NDC - Prescription NDC Codes billed on pharmacy claims.

The code here sets out to pull this information from our data warehouse tables, manipulate that data so that it is in the format that
the model expects, run the tables through the model, and export the outputs - specifically the average member risk score per month for 
the year of interest. This graph should look something like this (absolute risk score value is not included as it is propritary):

![Risk Score by Month Graph](https://github.com/kostdiek/ACARiskAdjustmentScore_BuildUp/blob/master/2018_Graph_deIdentified.JPG)


This code also serves to show off some of the skills that I have in SAS, many of which also translate well to SQL. 
