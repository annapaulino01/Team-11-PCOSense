# Team-11-PCOSense
A platform that looks for patterns associated with PCOS. The detection tool will guide users through a set of questions related to menstrual health, hormonal symptoms, and other related questions, it will then generate a risk-based assessment based on clinical criteria. This tool is not intended to diagnose PCOS, but rather provide understanding.

# Features
**Automated Data Ingestion**
 - Pulls survey responses directly from Google Sheets
 - Handles emptly datasets with built-in sample data

**Probabilistic Risk Model**
 - Uses log-odds (based on accredited medical resources) + sigmoid function to compute PCOS probability
 
 **Clinical Logic Integration**
 - Applies Rotterdam Criteria (3 domains) for PCOS screening
 - Generates interpretable flags across multiple health domains

# Model Overview
**Computes PCOS probability using:**
 - Total log-odds = Σ log(Pi / (1 - Pi))
 - P_final = 1 / (1 + e^(-Total log-odds))

**Risk Classification**
 - 70% or 2+ Rotterdam domains = High risk
 - 45-69% or 1 domain = Moderate risk
 - 25-44% = Low-moderate risk
 - <25% = Low risk

# Directions for Use
**Secrets:**  Put secrets in colab to allow code to run 

**Name:** EMAIL_PASSWORD | **Value:** iyln flfe okjc kupl

**Name:** SENDER_EMAIL | **Value:** PCOSenseData@gmail.com

The code is autoloping every 5 minutes. **Colab must be left open** to allow the survey and email to be sent.

# How it Works
 1. Pull data from Google Sheets
 2. Clean and map survey responses
 3. Apply probabilistic scoring model
 4. Generate:
    - Risk classification
    - Feature breakdown
    - Recommendations
 5. Output:
    - Deashboard visualization
    - Email notification with PDF report
    - Sheet export

# Disclaimer
 - This tool is intended for **screening purposes only** and is **not a medical diagnosis**. Users are encouraged to consult a licensed healthcare provider for clinical evaluation.
 - PCOSense platform development was **AI assisted**.

# Future Improvements
 - Machine learning model to enhance efficiency
 - Integration with wearable device
 - Improved personalization of recommendations


