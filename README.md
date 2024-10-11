# Enhancing Physical Activity Monitoring with Colibri Wireless Unit

## Introduction and Project Background

The  rise of fitness trackers marks a significant evolution in the landscape of personal health technology. Originally developed as basic heart monitors in the 1980s, these devices have undergone substantial transformation, becoming intricate systems that offer rich insights into various health metrics and physical activities. Modern fitness trackers not only measure heart rates but also track sleep patterns, count steps, monitor various forms of physical activity, and even provide GPS tracking for outdoor activities. This development has been driven by advances in sensor technology, data analytics, and consumer demand for wearable health monitoring devices.

This project centers on the Colibri Wireless unit, an advanced inertial measurement unit (IMU). The Colibri unit stands out due to its unique configuration of incorporating multiple sensors that capture three-dimensional acceleration, angular rates, and magnetic fields, providing high-resolution data. This project aims to leverage these capabilities to offer more precise and detailed monitoring of physical activities than its competitors.

### Project Goals

The primary goal of this project is to enhance the utility of the Colibri Wireless unit in health and activity monitoring applications, with a specific focus on integrating BMI (Body Mass Index) calculations to improve health risk assessment and activity monitoring accuracy. By analysing detailed data captured from various daily and sports activities under controlled conditions, coupled with BMI and related health metrics, we aim to:

1. Investigate how BMI interacts with various health-related metrics to understand its impact on overall health and fitness device effectiveness.
2. Enhance device performance and user experience by Formulating actionable recommendations based on the study’s findings to optimise the fitness tracking device. These enhancements could involve adjustments to the device's sensors, algorithms, or user interface.
3. Address study design limitations.
4. Explore more sophisticated modelling techniques by incorporating additional variables that were not included in the initial study.
   
This integration of BMI into the Colibri Wireless unit will also allow for the evaluation of health trends and comparisons across different populations and regions over time, making the device a more versatile tool in both personal health management and broader epidemiological studies.

### Research Significance

This research is significant as it contributes to the field of personal health monitoring, where accurate and real-time data analysis is crucial for preventive healthcare. By improving the performance and capabilities of the Colibri Wireless unit, the project aligns with the broader goal of advancing health technology to better meet the needs of both individuals and healthcare providers. Moreover, the findings from this study could inform future developments in wearable technology, helping to shape innovations that enhance user well-being and health management.


## Data Collection and Analysis Setup

Data was collected from nine subjects equipped with three Colibri wireless IMUs and a BM-CS5SR heart-rate monitor. The subjects consisted of one female and eight males, aged 27.22 ± 3.31 years.

### Subject Details
Comprehensive demographic and physiological data were collected for each subject, including specific measurements like age, gender, height, weight, resting heart rate, and maximum heart rate. Detailed individual subject information is available in [Subject Information](./assets/subjectInformation.pdf).

### Data Collection Hardware
- **IMUs**: Three Colibri wireless inertial measurement units were used, placed over the wrist of the dominant arm, on the chest, and on the dominant side's ankle. These units sampled data at 100Hz, providing detailed measurements including 3D-acceleration, gyroscope, and magnetometer readings across multiple axes.
- **Heart Rate Monitor**: The heart rate was recorded using a BM-CS5SR monitor.

### Activities Performed
The subjects performed a structured set of 12 basic activities outlined in the [Data Collection Protocol](./assets/DataCollectionProtocol.pdf), with additional optional activities suggested from a list containing a wide range of everyday, household, and sports activities. The basic activities included:
1. Lying
2. Sitting/
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

Each activity was performed according to specific guidelines to ensure consistent data collection across subjects. A complete description of these activities, including their setup and execution, can be found in [Description of Activities](./assets/DescriptionOfActivities.pdf/).

### Data Collection Protocol
Each subject followed a detailed protocol for the data collection, performing the specified activities in a controlled environment. The protocol ensured that data was collected systematically for each activity, capturing physiological responses accurately. The protocol also suggested additional optional activities, enhancing the dataset with diverse physical exertions.

### Summary of Collected Data
Over 10 hours of data were collected, with nearly 8 hours labeled according to the 18 different activities performed. Due to the use of wireless sensors, some data points were missing, attributed to data dropping or hardware issues like connection losses or system crashes. Detailed summaries of the data collected for each activity by each subject are provided in [Performed Activities Summary](./assets/PerformedActivitiesSummary.pdf/).


## Libraries and Modules Utilised

For comprehensive data analysis and modeling, a variety of Python libraries and modules were employed, as detailed below:

- **Pandas**: Used for data manipulation tasks such as merging data frames and handling missing values.
- **NumPy**: Utilised for heavy numerical computations.
- **Matplotlib** and **Seaborn**: Employed for visual data exploration and creating insightful plots.
- **SciKit-Learn**: Used for several machine learning tasks including Principal Component Analysis (PCA), linear regression models, and feature selection.
- **StatsModels**: Applied for more detailed statistical modeling and hypothesis testing. This includes using the Empirical Cumulative Distribution Function (ECDF) for non-parametric analysis.
- **StandardScaler**: From SciKit-Learn, used for normalising features before applying machine learning models.
- **SequentialFeatureSelector**: Also from SciKit-Learn, employed to identify the best subset of features for predictive modeling.
- **Train Test Split**, **Mean Squared Error**, and **R2 Score**: Utilised for model evaluation, specifically to assess the performance of regression models.
- **Linear Regression**: Implemented for predictive modeling, essential for understanding relationships between variables.

### Data Wrangling and Cleaning Process

#### Data Consolidation
- **Source Data**: Data from nine subjects consolidated into a single DataFrame from multiple .dat files.
- **Method**: The data files were concatenated using pandas to create a unified DataFrame with consistent column titles, ensuring seamless integration of all subjects' data.

#### Merging Additional Data
- **Additional Data**: Merged optional activity data to enrich the dataset.
- **Process**: For subjects with optional activity data, these data were merged with their main dataset, expanding the range of activities analysed and enhancing data depth.

#### Data Cleaning
- **Handling Missing Values**: Removed NaN values from the DataFrame after the 'heart rate (bpm)' column was filled using forward and backward filling methods, to preserve data continuity without introducing bias.
- **Adjustments in Data**:
  - Activity data with activityID of 0, indicating transitional or unlabeled activities, were removed to maintain focus on relevant activity data.
  - Specific sensor data columns identified as unreliable were excluded from further analysis.
  - Orientation data, found to be invalid, were discarded to prevent skewed analysis.

#### Data Integration and Enrichment
- **BMI Calculation**: Introduced new columns for Body Mass Index (BMI), calculated from subjects' height and weight, facilitating health-related insights.
- **Activity Duration**: Computed the duration of each activity, offering a detailed view of time allocation among different physical activities.

#### Data Structure Optimisation
- **Normalisation**: Standardised the dataset to prepare for principal component analysis, ensuring that features contribute equally without scale bias.
- **Feature Reduction**: Removed less impactful features, focusing the analysis on significant variables and improving computational efficiency.

### Predictive Hypothesis and Analytical Methodology

The hypothesis assumes that physiological metrics derived from Colibri Wireless units can accurately predict the type of physical activity and its intensity. The analytical methodology involves the following main stages:

1. **Dimensionality Reduction**: Utilise Principal Component Analysis (PCA) to reduce the complexity of the dataset while preserving essential features. This transformation helps simplify the subsequent analysis by focusing on the most significant variables that contribute to variance in the data.

2. **Regression Analysis**: Develop regression models to predict Body Mass Index (BMI) based on physiological and temporal data metrics. These models aim to correlate specific physiological responses and time-related variables with BMI, providing a predictive framework for understanding how different metrics influence BMI values..


## Analytical Results

#### Activity Patterns:
It was observed from the bar charts that not all subjects participated in every activity and did not spend the same duration doing each activity, showcasing varied engagement levels. 

#### BMI Insights:
Individuals were categorised into 'Healthy' and 'Overweight' groups based on their BMI, with no participants falling into 'Underweight' or 'Obese' categories. This categorisation was crucial in analysing patterns, as shown in the box-and-whisker plots that detailed the time taken for activities and heart rates, indicating different physical exertion levels across BMI categories.

#### Data Distribution:
The dataset was divided based on BMI categories ('Underweight' and 'Healthy' versus 'Overweight' and 'Obese'), and histograms were used to study the data distribution within these groups, revealing a non-normally distributed pattern.

#### Principal Component Analysis (PCA):
PCA was applied to simplify the dataset, successfully reducing it to a few principal components that captured the core differences in data. The analysis revealed that the first three components explained over 60% of the variance, with the primary component predominantly influenced by weight and BMI.

#### Correlation Studies:
Three regression models were utilised:
1. **BMI Regression:** Employing Ordinary Least Squares (OLS), this model showed a high explanatory power with an R-squared value of 0.995, affirming strong dependencies between BMI, weight, and height.
2. **Heart Rate Regression:** With an R-squared value of 0.582, this model suggested moderate explanatory power. Factors like age and height positively correlated with heart rate, whereas weight and activity duration showed negative correlations.

### Empirical Cumulative Distribution Function (ECDF) Plots:
ECDF plots were employed to emphasise the distinct BMI profiles across the two separated DataFrames, highlighting the importance of BMI in categorising subjects for this analysis.

## Conclusions

The study conducted has provided essential insights into the usage and effectiveness of a fitness tracking device, utilising a limited but informative sample size. Through a series of activities ranging from minimal to moderately intense, and through initial analyses involving graphical representations and mathematical models, several actionable recommendations have been formulated. These recommendations, derived from the findings, aim to optimise the device’s performance and enhance user experience by addressing identified limitations in study design and demographic inclusivity.

**Key Observations:**

- **Gender Balance and Participant Diversity:**
  - The study reveals a significant lack of gender balance and limited diversity in participant body weight categories.
  - The dominance of males and the concentration of individuals classified as 'healthy' or 'overweight' could skew results.
  - This lack of representation diminishes the generalisability of the study’s outcomes, particularly for those in the 'underweight' or 'obese' categories who might benefit from such a device.

- **Activity Completion and Exercise Intensity:**
  - There is an absence of comprehensive activity completion and a lack of intensity in the exercises chosen.
  - These factors result in a dataset that, while useful, is not fully representative of the potential variability in a more diverse population.
  - Integration of BMI: A software to add Body Mass Index (BMI) is crucial. The analysis has demonstrated the impact of BMI and how it would be a great add to the device. Therefore, calculating BMI when users input their weight and height will enhance accuracy. Additionally, BMI can help users monitor their progress, set goals, and enable the device to offer personalised recommendations and insights based on their BMI category (e.g., underweight, healthy, overweight, or obese). This may include customised exercise plans, dietary advice, or goal adjustments. On the other hand, inputting the user's gender and BMI into the device can allow the device to educate the user on potential health concerns and encourage them to seek professional guidance when necessary.

## Future Work

- Improve the study results by addressing the limitations identified in the initial research.
- Expand the participant base to ensure a balanced gender representation.
- Include a broader range of weight categories to enhance the study's applicability.
- Incorporate more intense physical activities to test the device's effectiveness thoroughly.
- Ensure that all participants complete the designated activities to increase data robustness and reliability.
- To extend the functionality of the device further, future iterations could include additional sensors for measuring metrics such as muscle mass and calories burned. These enhancements would not only improve the precision of health assessments provided by the device but also motivate users by allowing them to track their progress more effectively.

The implementation of these recommendations and the subsequent analysis of their impact will be crucial in evolving the device's capabilities and ensuring it meets the needs of a broader user base. Continued innovation and adaptation, based on empirical data and user feedback, will be key to maintaining and enhancing the relevance and effectiveness of the fitness tracking device in promoting health and wellbeing.
