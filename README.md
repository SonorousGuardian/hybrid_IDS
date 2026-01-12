# 🛡️ Hybrid-IDS: Suricata + Machine Learning

![License](https://img.shields.io/badge/license-MIT-blue.svg) ![Python](https://img.shields.io/badge/python-3.8%2B-blue) ![Suricata](https://img.shields.io/badge/Suricata-IDS-orange) ![Status](https://img.shields.io/badge/status-Active-green)

## 📖 Overview

With the rapid expansion of network infrastructure, organizations face increasing challenges in safeguarding sensitive information. **Hybrid-IDS** is a robust Network Intrusion Detection System (NIDS) designed to bridge the gap between traditional signature-based detection and modern anomaly-based analysis.

This project combines the real-time packet analysis capabilities of **Suricata** (an open-source IDS/IPS engine) with the predictive power of **Machine Learning (ML)** algorithms. By leveraging Suricata's rule-based detection for known threats and integrating it with ML models trained to spot anomalous behaviors, this system aims to:
* Improve detection accuracy.
* Significantly reduce false positives.
* Adapt to evolving, zero-day cyber threats.

## 🚀 Key Features

* **Hybrid Detection Engine:** Merges signature-based inspection (Suricata) with anomaly-based detection (ML) for comprehensive coverage.
* **Real-Time Monitoring:** Continuous analysis of network traffic flow to detect unauthorized access immediately.
* **Advanced Threat Detection:** Capable of identifying DDoS attacks, malware infiltration, and brute-force attempts.
* **Reduced Noise:** ML models cross-reference alerts to lower false-positive rates, ensuring only critical threats are flagged.
* **Scalable Architecture:** Designed to operate efficiently in both controlled testbeds and larger network environments.

## 🏗️ Architecture

The system operates in two parallel streams:
1.  **Suricata Module:** Monitors live traffic and applies predefined rules (signatures) to catch known attack patterns.
2.  **ML Module:** Analyzes flow statistics and features to identify deviations from normal baselines (anomaly detection).

*(Optional: Add a diagram here showing Traffic -> Suricata / ML Model -> Aggregator -> Alert Dashboard)*

## 🛠️ Tech Stack

* **Core Engine:** [Suricata](https://suricata.io/)
* **Programming Language:** Python
* **Machine Learning:** Scikit-learn / TensorFlow / PyTorch (Update based on your actual library)
* **Data Processing:** Pandas, NumPy
* **Logging/Visualization:** ELK Stack (Elasticsearch, Logstash, Kibana) or similar (Update if applicable)

## 📊 Performance Metrics

We evaluate the system using standard cybersecurity metrics to ensure reliability:
* **Detection Rate (DR):** The percentage of actual attacks detected.
* **False Positive Rate (FPR):** The frequency of normal traffic flagged as malicious.
* **System Efficiency:** CPU and Memory usage during peak traffic analysis.

## ⚡ Getting Started

### Prerequisites
* Linux Environment (Ubuntu/Debian recommended)
* Python 3.8+
* Suricata installed and configured

### Installation

1.  **Clone the repository**
    ```bash
    git clone [https://github.com/yourusername/Hybrid-IDS.git](https://github.com/yourusername/Hybrid-IDS.git)
    cd Hybrid-IDS
    ```

2.  **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Configure Suricata**
    Ensure your `suricata.yaml` is pointing to the correct network interface.

4.  **Run the System**
    ```bash
    python main.py
    ```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
