# Enhancing Physical Activity Monitoring with Colibri Wireless Unit: Comprehensive Analysis

## Introduction and Project Background

The advent of fitness trackers marks a significant evolution in the landscape of personal health technology. Originally developed as basic heart monitors in the 1980s, these devices have undergone substantial transformation, becoming intricate systems that offer rich insights into various health metrics and physical activities. Modern fitness trackers not only measure heart rates but also track sleep patterns, count steps, monitor various forms of physical activity, and even provide GPS tracking for outdoor activities. This development has been propelled by advances in sensor technology, data analytics, and consumer demand for wearable health monitoring devices.

This project centers on the Colibri Wireless unit, an advanced inertial measurement unit (IMU)  The Colibri unit stands out due to its unique configuration of incorporating multiple sensors that capture three-dimensional acceleration, angular rates, and magnetic fields, providing high-resolution data. This project aims to leverage these capabilities to offer more precise and detailed monitoring of physical activities than its competitors.

### Project Goals

The primary goal of this project is to enhance the utility of the Colibri Wireless unit in health and activity monitoring applications, with a specific focus on integrating BMI (Body Mass Index) calculations to improve health risk assessment and activity monitoring accuracy. By analysing detailed data captured from various daily and sports activities under controlled conditions, coupled with BMI and related health metrics, we aim to:

1. Develop algorithms that can accurately predict the type of activity being performed by an individual, factoring in BMI to refine the estimation of energy expenditure and health risk assessment.
2. Refine the unit's data processing capabilities to improve the accuracy and reliability of health metrics derived from raw sensor data and BMI calculations.

This integration of BMI into the Colibri Wireless unit will also allow for the evaluation of health trends and comparisons across different populations and regions over time, making the device a more versatile tool in both personal health management and broader epidemiological studies.

### Research Significance

This research is significant as it contributes to the field of personal health monitoring, where accurate and real-time data analysis is crucial for preventive healthcare. By improving the performance and capabilities of the Colibri Wireless unit, the project aligns with the broader goal of advancing health technology to better meet the needs of both individuals and healthcare providers. Moreover, the findings from this study could inform future developments in wearable technology, helping to shape innovations that enhance user well-being and health management.


## Data Collection and Analysis Setup

Data was collected from nine subjects equipped with three Colibri wireless IMUs and a BM-CS5SR heart-rate monitor. The subjects consisted of one female and eight males, aged 27.22 ± 3.31 years.

### Subject Details
Comprehensive demographic and physiological data were collected for each subject, including specific measurements like age, gender, height, weight, resting heart rate, and maximum heart rate. Detailed individual subject information is available in [subject Information](/subjectInformation.pdf/).

### Data Collection Hardware
- **IMUs**: Three Colibri wireless inertial measurement units were used, placed over the wrist of the dominant arm, on the chest, and on the dominant side's ankle. These units sampled data at 100Hz, providing detailed measurements including 3D-acceleration, gyroscope, and magnetometer readings across multiple axes.
- **Heart Rate Monitor**: The heart rate was recorded using a BM-CS5SR monitor.

### Activities Performed
The subjects performed a structured set of 12 basic activities outlined in the `DataCollectionProtocol.pdf`, with additional optional activities suggested from a list containing a wide range of everyday, household, and sports activities. The basic activities included:
1. Lying
2. Sitting
3. Standing
4. Walking
5. Running
6. Cycling
7. Nordic walking
8. Watching television
9. Computer work
10. Car driving
11. Ascending stairs
12. Descending stairs

Additional activities performed by some subjects included:
1. Vacuum cleaning
2. Ironing
3. Folding laundry
4. House cleaning
5. Playing soccer
6. Rope jumping

Each activity was performed according to specific guidelines to ensure consistent data collection across subjects. A complete description of these activities, including their setup and execution, can be found in [description of activities](/DescriptionOfActivities.pdf/).

### Data Collection Protocol
Each subject followed a detailed protocol for the data collection, performing the specified activities in a controlled environment. The protocol ensured that data was collected systematically for each activity, capturing physiological responses accurately. The protocol also suggested additional optional activities, enhancing the dataset with diverse physical exertions.

### Summary of Collected Data
Over 10 hours of data were collected, with nearly 8 hours labeled according to the 18 different activities performed. Due to the use of wireless sensors, some data points were missing, attributed to data dropping or hardware issues like connection losses or system crashes. Detailed summaries of the data collected for each activity by each subject are provided in [performed activities summary](/PerformedActivitiesSummary.pdf/).


## Libraries and Modules Utilised

A variety of Python libraries were employed for data analysis:

- **Pandas**: For data manipulation tasks such as merging data frames and handling missing values.
- **NumPy**: For heavy numerical computations.
- **Matplotlib** and **Seaborn**: For visual data exploration and creating plots.
- **SciKit-Learn**: For PCA, KMeans clustering, and regression models.

## Data Wrangling and Cleaning Process

Key steps included:

- **Consolidation**: Data from nine subjects consolidated into a single DataFrame.
- **Merging Additional Data**: Merged optional activity data for a fuller activity range.
- **Data Cleaning**: Removed unreliable sensor readings and filled missing values.

## Predictive Hypothesis and Analytical Methodology

The hypothesis assumed that physiological metrics could predict the type of physical activity and its intensity. This involved:

- **Dimensionality Reduction**: Using PCA to reduce data complexity.
- **Clustering**: Applying KMeans to group similar activity patterns.
- **Regression Analysis**: Developing models to predict activity types from physiological data.

## Detailed Analytical Results

Findings included:

- **Activity Patterns**: Variations in how subjects responded to similar activities.
- **Correlation Studies**: Significant correlations between BMI and activity intensity.

## Conclusions and Future Work

The study concluded significant potential for the Colibri unit in enhancing activity monitoring. Recommendations include:

- Enhancing sensor accuracy.
- Expanding data collection protocols.
- Developing real-time predictive algorithms.

## Repository and Documentation

All scripts and data are organized in a structured repository, ensuring transparency and ease of development or replication.

This README provides exhaustive documentation of the project from data collection through detailed analysis, aimed at ensuring clarity and thorough understanding for further research.
