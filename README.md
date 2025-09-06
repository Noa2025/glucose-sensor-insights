# glucose-sensor-insights
Type 1 diabetes is a chronic condition in which the body cannot produce insulin, a hormone essential for regulating blood glucose (BG) levels. Achieving stable glucose control is critical: good control reduces the risk of long-term complications such as cardiovascular disease, kidney failure, and vision loss. However, tight glucose management comes with the danger of hypoglycemia, particularly at night while the patient is asleep. Nocturnal hypoglycemia can go unnoticed and poses a serious health risk.
To address these challenges, modern diabetes care increasingly uses the concept of “closing the loop”. This approach combines a continuous glucose monitoring (CGM) sensor with an insulin pump. The CGM provides real-time glucose readings, while the pump delivers insulin in two ways:
*	Basal insulin: a continuous background infusion set by pre-determined rates.
*	Bolus insulin: larger doses administered at meals.
The pump not only receives glucose readings but also generates alerts for abnormal levels or technical issues. Some models, such as the Paradigm MINIMED 640G that was used here, include a suspend feature that automatically halts insulin infusion in response to critically low glucose readings, helping prevent severe hypoglycemia.
### Data Source
This dataset contains six months of insulin pump logs from a single patient. It includes:
* Timestamps
* Blood glucose (BG) readings
* Basal insulin infusion rates
* Alerts on glucose or technical events
As expected in real-world data, there are occasional gaps caused by sensor malfunctions.
### Tools & Programming
The analysis is implemented in Python, using the following libraries and tools: pandas, numpy, matplotlib, seaborn
### Purpose
The goal of this analysis is to create a report for both patient and physician, covering:
* Glucose patterns over time, including time in range (90–180 mg/dL), hypoglycemia (<70 mg/dL), and hyperglycemia (>200 mg/dL).
* Temporal patterns in BG and alerts.
* An evaluation of whether basal insulin settings are appropriate overnight.
### Results Summary
1.	Glucose Statistics
* Time in Range (90–180 mg/dL): 43.8%
* Hypoglycemia (<70 mg/dL): 4.1%
* Hyperglycemia (>200 mg/dL): 29.9%
2.	Hourly & Daily Distribution
* Highest average BG: 4:00 → 257 mg/dL
* Lowest average BG: 14:00 → 141.2 mg/dL
* Highest weekday BG: Friday → 183.2 mg/dL
* Lowest weekday BG: Wednesday → 152.5 mg/dL
3.	Trend
* Slope: +0.074 mg/dL per day (increasing trend).
4.	Overnight Drift
* Median: 0.0 mg/dL
* Nights with >20 mg/dL rise: 7.7%
* Nights with >20 mg/dL drop: 11.5%
5.	Alerts
* Low Sugar alerts peak: Weekday 16:00 (36 counts), Weekend 18:00 (14 counts).
* High Sugar alerts peak: Weekday 23:00 (18 counts), Weekend 20:00 (12 counts).
Conclusion
This type of analysis provides valuable insight into a patient’s glucose dynamics and insulin pump behavior. By highlighting patterns in blood glucose, alert frequency, and overnight drift, the results can help physicians fine-tune basal insulin infusion settings, minimizing both hyperglycemia and hypoglycemia risks.
Importantly, this visualization approach works without requiring information on carbohydrate intake, making it useful even when meal data are unavailable. It offers a practical, data-driven perspective to support personalized diabetes care.
