# Description

House price is a recurring subject nowadays. In this project, you will build a model to predict the price base on predefined criteria.

We are providing a dataset, the Boston housing prices.

This project is divided into two parts: 1# Understand the data 2# Build a linear regression prediction model.

# Task

Just like we did with Mr Clean, cleaning is one of the first steps after receiving a dataset to explore. Here the dataset was made to be very clean, but just to be sure, let's look for any missing values.

→ Make a function that cleans the dataset from lines which any missing values.

def clean_dataset(boston_dataframe):
	...
After this function, we should have zero missing values in the dataset.

Now we are ready to cut to the chase. We will see if our supposition was correct by visualizing the data.

Visualization is critical to understanding the relationship between the target and the other features.

A great way to get a feel of the data we are dealing with is to plot each attribute in a histogram.

→ Plot each attribute in a histogram.

Hint: You can use matplotlib, panda, seaborn or any other libraries.

Here is the result for some of the attributes:

# Installation

python -m venv venv

source venv/bin/activate

# Usage

./my_project argument1 argument2