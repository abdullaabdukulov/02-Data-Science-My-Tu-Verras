## Task
1. pd.read_csv("https://storage.googleapis.com/qwasar-public/track-ds/boston.csv"): This line is used to fetch the boston.csv file from the internet. It utilizes the read_csv method of the "pandas" library to read the file into a DataFrame.

2. return: It is used to return the loaded DataFrame. By doing this, the function returns the loaded data to the calling code.

In summary, the load_dataset function is responsible for loading the data and returning it in the form of a DataFrame.
## Description
Load Dataset: Loads the Boston housing dataset from a CSV file hosted online.
Print Dataset Summary: Prints the dimensions, displays the first 10 rows, and provides a statistical summary of the dataset.
Clean Dataset: Removes rows with missing values from the dataset.
Print Histograms: Generates histograms for each numerical attribute in the dataset.
Print Scatter Matrix: Displays a scatter plot matrix for the dataset.
Compute Correlation Matrix: Computes the correlation matrix for all numerical attributes in the dataset using the Pearson correlation method and prints the correlation coefficients for the target variable "MDEV".
## Installation
To run the code, make sure you have the following Python libraries installed:

pandas
numpy
matplotlib
scikit-learn
## Usage
These scripts are designed to assist you in loading, analyzing, visualizing, and learning from data. You can use the following functions:

load_dataset(): Used to load the dataset.
print_summarize_dataset(dataset): Used to print a brief summary of the data.
clean_dataset(boston_dataframe): Used to clean the data.
print_histograms(boston_dataframe): Used to print histograms.
print_scatter_matrix(boston_dataframe): Used to print a scatter matrix.
compute_correlations_matrix(data): Used to compute the correlation matrix.
