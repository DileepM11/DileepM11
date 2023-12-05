# Import necessary libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the education data from a CSV file
education_data = pd.read_csv('education_data.csv')

# Display the first few rows of the dataset
print("Sample of the Education Data:")
print(education_data.head())

# Explore basic statistics of the dataset
print("\nBasic Statistics of the Education Data:")
print(education_data.describe())

# Visualize student performance
plt.figure(figsize=(10, 6))
sns.histplot(education_data['Student_Scores'], bins=20, kde=True)
plt.title('Distribution of Student Scores')
plt.xlabel('Scores')
plt.ylabel('Frequency')
plt.show()

# Explore correlation between variables
correlation_matrix = education_data.corr()
plt.figure(figsize=(10, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', linewidths=0.5)
plt.title('Correlation Matrix of Education Data')
plt.show()

# Identify at-risk students based on a threshold (adjust as needed)
threshold = 60
at_risk_students = education_data[education_data['Student_Scores'] < threshold]

# Display at-risk students
print("\nAt-Risk Students:")
print(at_risk_students)

# Additional analysis based on specific objectives

# Save the analysis results or visualizations as needed
# For example: plt.savefig('analysis_result.png')
