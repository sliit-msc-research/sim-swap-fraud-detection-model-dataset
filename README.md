# SIM Swap Fraud Detection - Synthetic Dataset

This repository provides a synthetic dataset designed to support research and development of machine learning models for detecting **SIM swap fraud**. The dataset was generated using a custom Python script simulating realistic telecom and behavioral indicators associated with fraudulent SIM swapping activity.

---

## Files

- `sim_swap_fraud_dataset_100000.csv`  
  Contains 100,000 synthetic records with features relevant to SIM swap detection.

- `sim_swap_fraud_dataset_50000.csv`  
  Contains 50,000 synthetic records with features relevant to SIM swap detection.

---

## Dataset Features

| Feature Name                          | Description |
|--------------------------------------|-------------|
| `sim_swap_time_gap_minutes`          | Time between OTP request and SIM change |
| `device_change_flag`                 | Whether the device was recently changed |
| `sim_type_change_flag`               | SIM type modification (e.g., prepaid to postpaid) |
| `imsi_change_flag`                   | Change in International Mobile Subscriber Identity |
| `iccid_change_flag`                  | Change in SIM card identifier |
| `otp_and_sim_change_geo_hash_length`| Geolocation similarity between OTP use and SIM change |
| `recent_sim_activation_days`         | Days since last SIM activation |
| `num_sim_changes_last_30d`           | Number of SIM swaps in the past 30 days |
| `previous_sim_holder_tenure_days`    | Duration previous SIM was active |
| `account_age_days`                   | Age of mobile account |
| `ip_change_flag`                     | Whether IP address changed during activity |
| `sim_swap_flag`                      | **Target variable** – 1 if flagged as potential SIM swap fraud, else 0 |

---

## Fraud Scoring Logic

The `sim_swap_flag` is computed using a weighted combination of:

- Identity changes (device, SIM type, IMSI, ICCID)
- Geolocation mismatch
- SIM change urgency
- Behavioral risk signals (recent SIM activation, multiple swaps, IP change)

