# 02 Data Science My Tu Verras

<div class="row">
<div class="col tab-content">
<div class="tab-pane active show" id="subject" role="tabpanel">
<div class="row">
<div class="col-md-12 col-xl-12">
<div class="markdown-body">
<p class="text-muted m-b-15">
</p><h1>My Tu Verras</h1>
<p>Remember to git add &amp;&amp; git commit &amp;&amp; git push each exercise!</p>
<p>We will execute your function with our test(s), please DO NOT PROVIDE ANY TEST(S) in your file</p>
<p>For each exercise, you will have to create a folder and in this folder, you will have additional files that contain your work. Folder names are provided at the beginning of each exercise under <code>submit directory</code> and specific file names for each exercise are also provided at the beginning of each exercise under <code>submit file(s)</code>.</p>
<hr>
<table>
<thead>
<tr>
<th>My Tu Verras</th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<td>Submit directory</td>
<td>.</td>
</tr>
<tr>
<td>Submit file</td>
<td>my_tu_verras.ipynb</td>
</tr>
</tbody>
</table>
<h3>Description</h3>
<img src="https://danielfast.files.wordpress.com/2014/01/iceberg15501001_s.jpg" width="400">
<h2>Description</h2>
<p>House price is a recurring subject nowadays. In this project, you will build a model to predict the price base on predefined criteria.</p>
<p>We are providing a dataset, the <a href="https://storage.googleapis.com/qwasar-public/track-ds/boston.csv" target="_blank">Boston housing prices</a>.</p>
<p>This project is divided into two parts:
1# Understand the data
2# Build a linear regression prediction model.</p>
<h2>First Glance</h2>
<p>Let's get down to the brass task.</p>
<p>From a quick look, we know what is inside our dataset, like the different attributes:</p>
<p>• <strong>CRIM</strong> per capita crime rate by town
• <strong>ZN</strong> proportion of residential land zoned for lots over 25,000 sq.ft.
• <strong>INDUS</strong> proportion of non-retail business acres per town
• <strong>CHAS</strong> Charles River dummy variable (= 1 if tract bounds river; 0 otherwise)
• <strong>NOX</strong> nitric oxides concentration (parts per 10 million)
• <strong>RM</strong> average number of rooms per dwelling
• <strong>AGE</strong> proportion of owner-occupied units built before 1940
• <strong>DIS</strong> weighted distances to five Boston employment centers
• <strong>RAD</strong> index of accessibility to radial highways
• <strong>TAX</strong> full-value property-tax rate per $10,000
• <strong>PTRATIO</strong> pupil-teacher ratio by town
• <strong>B</strong> 1000(Bk - 0.63)^2 where Bk is the proportion of blacks by town
• <strong>LSTAT</strong> PERCENT lower status of the population
• <strong>MEDV</strong> Median value of owner-occupied homes is $ 1000's</p>
<p>Now that we loaded the data let's peek at it.</p>
<p>→ <strong>Load the data in a data frame and print the first rows.</strong></p>
<pre class=" language-plain"><code class=" language-plain">def load_dataset():
	...

boston_dataframe = load_dataset()


def print_summarize_dataset(dataset):
   print("Dataset dimension:")
   print(XXXXXXXX)
   print("
First 10 rows of dataset:")
   print(XXXXXXXX)
   print("
Statistical summary:")
   print(XXXXXXXX)

print_summarize_dataset(dataset)
</code></pre>
<p><strong>hint:</strong> Panda is cool.</p>
<p>We should see something similar to:</p>
<img src="https://storage.googleapis.com/qwasar-public/track-ds/boston_panda.png" width="700">
<p>Now that we have loaded the data frame, it is easier to see and investigate the data. Play around a bit and print some more values.
The data frame table is excellent but is hard to read. Can you tell from it what attributes have the most influence on the MEDV target?</p>
<p>From a quick sneak peek, we feel the MEDV decreases as the AGE increases. The correlation between MEDV and AGE is just a supposition, and we will try to corroborate it.
Do you see any other relationship between attributes?</p>
<h2>Cleaning and Pre-processing</h2>
<p>Just like we did with Mr Clean, cleaning is one of the first steps after receiving a dataset to explore. Here the dataset was made to be very clean, but just to be sure, let's look for any missing values.</p>
<p>→ <strong>Make a function that cleans the dataset from lines which any missing values.</strong></p>
<pre class=" language-plain"><code class=" language-plain">def clean_dataset(boston_dataframe):
	...
</code></pre>
<p>After this function, we should have <strong>zero</strong> missing values in the dataset.</p>
<h2>Data Analysis</h2>
<p>Now we are ready to cut to the chase. We will see if our supposition was correct by <strong>visualizing</strong> the data.</p>
<p>Visualization is critical to understanding the relationship between the target and the other features.</p>
<p>A great way to get a feel of the data we are dealing with is to plot each attribute in a histogram.</p>
<p>→ <strong>Plot each attribute in a histogram.</strong></p>
<p><strong>Hint:</strong> You can use <a href="https://matplotlib.org/api/_as_gen/matplotlib.pyplot.hist.html" target="_blank">matplotlib</a>, <a href="https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.hist.html" target="_blank">panda</a>, <a href="https://seaborn.pydata.org/generated/seaborn.distplot.html" target="_blank">seaborn</a> or any other libraries.</p>
<p>Here is the result for some of the attributes:</p>
<img src="https://storage.googleapis.com/qwasar-public/track-ds/boston_hist.png">
<p>→ <strong>Make a function that prints all the histograms.</strong></p>
<pre class=" language-plain"><code class=" language-plain">def print_histograms(boston_dataframe):
	...
</code></pre>
<h3>Looking for correlations</h3>
<p>So far, we have only taken a quick peek to get a general understanding of the kind of data we are manipulating. Now the goal will be to investigate deeper again.</p>
<p>The size of our dataset is not too large, so we can try to analyze <a href="https://en.wikipedia.org/wiki/Pearson_correlation_coefficient" target="_blank">linear correlations</a> between every pair of attributes.</p>
<p>→ <strong>Write a function compute_correlations_matrix to compute Pearson's correlations between every pair of attributes.</strong></p>
<p>The output of compute_correlation should be a dictionary. For example, print(correlations['MEDV']) should show the different correlation coefficients between the median value and other attributes.</p>
<pre class=" language-plain"><code class=" language-plain">def compute_correlations_matrix(boston_dataframe):
	...

correlations = compute_correlations(boston_dataframe)

print(correlations['MEDV'])

</code></pre>
<p>When the coefficient is close to 1 (in absolute value), there is a strong correlation between the two variables. If it is positive, it means the linear correction is positive. If it is negative... you get it.
Coefficients close to zero mean there is no linear correlation between the attributes.</p>
<p>→ <strong>What is the correlation coefficient between the median value and the number of rooms?</strong></p>
<p>This coefficient is positive and is the biggest. It means that the median value increases when the number of rooms increases. Well, that makes sense; we expect a house with many rooms to be more expensive than a single-room apartment.</p>
<p>→ <strong>Analyse the correlations between the median value and the other attributes. Which attribute is the most negatively correlated with the median value? Does it make sense to you?</strong></p>
<p>Mathematically, all this information can be seen in an object, the <a href="https://en.wikipedia.org/wiki/Covariance_matrix" target="_blank">covariance matrix</a>. The covariance matrix tells us a lot about our data's relationship and distribution.
For example, it can be used in <a href="https://en.wikipedia.org/wiki/Principal_component_analysis" target="_blank">Principal Component Analysis</a> to try and understand the most useful and relevant dimensions. But that's for another day.</p>
<p>Numbers are cool, but we, as human beings, love colors, pictures, and visual representations. We can easily spot correlations by visualizing the relationship between attributes on graphs.</p>
<p>→ <strong>Plot every attribute against each other.</strong></p>
<p><strong>hint</strong>: Visualizing every component against each other is usually done with a <strong>scatter matrix</strong>.</p>
<p>Here is an example:</p>
<img src="https://storage.googleapis.com/qwasar-public/track-ds/boston_scatter_matrix.png">
<p>Instead of representing straight lines, the main diagonal displays a histogram of the attributes.</p>
<p>→ <strong>Make a function that prints the scatter matrix.</strong></p>
<pre class=" language-plain"><code class=" language-plain">def print_scatter_matrix(boston_dataframe):
	...
</code></pre>
<p>Since the most linearly correlated feature is the average number of rooms, let's focus on the plot of MEDV as a function of RM.</p>
<p>→ <strong>Plot MEDV in function of RM</strong></p>
<p>We should see what the numbers told us before. We clearly see an upward trend. A strong positive linear correlation exists between the number of rooms and the median value.
Ok, now let's explore the influence of other attributes.</p>
<p>→ <strong>Plot the correlation scatter plot of the median value against LSTAT, AGE, and CRIME.</strong></p>
<img src="https://storage.googleapis.com/qwasar-public/track-ds/boston_lstat_age_crime.png">
<p>→ <strong>What can you observe? What can you say?</strong>.</p>
<p>→ <strong>Does the age seems to have any influence on the MEDV?</strong></p>
<p>Well, not so fast! the MEDV / AGE scatterplot does not show an apparent correlation between these attributes. But we can see that the LSTAT feature DOES influence MEDV.
The more LSTAT increases, the lower the MEDV value. We can see another correlation to be between LSTAT and MEDV. It is valuable information itself. Can we not go further?</p>
<p>Let's step back a minute. If LSAT influences MEDV, it means that if another attribute affects LSTAT itself, it actually circles back to influence MEDV!</p>
<p>→ <strong>Plot the scatter matrix or print the correlation coefficients for LSTAT. What are the attributes which are the most linearly correlated with LSAT?</strong></p>
<p>Here is an example, LSTAT against AGE:</p>
<img src="https://storage.googleapis.com/qwasar-public/track-ds/boston_lstat_age.png">
<p>Again, we clearly see a trend here. Points are not too dispersed and have an upward trend. LSAT seems to be positively linearly correlated with AGE.
So, all in all, AGE seems to influence (negatively) the median value. We could already observe this result on the graph of MEDV / AGE. Varying AGE cascades down (or <strong>back-propagates</strong>) to make MEDV varies.</p>
<p>You can go on experimenting with trying and finding more relationships between attributes to understand more deeply how they influence de MEDV target values.</p>
<h2>Prediction</h2>
<p>After exploring the data and gaining more insights, the next step is to do another round of data cleaning and find a model to predict the MEDV.</p>
<p>We are going to use a linear regression algorithm from sklearn.</p>
<pre class=" language-plain"><code class=" language-plain">from sklearn.linear_model import LinearRegression
</code></pre>
<p>→ <strong>Make a function that return a <a href="https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html" target="_blank">Fitted Estimator</a>.</strong></p>
<pre class=" language-plain"><code class=" language-plain">import sklearn

def boston_fit_model(boston_dataframe):
  # SELECT two columns from our
  model_dataset = boston_dataframe[["RM","MDEV"]]
  regressor = sklearn.linear_model.LinearRegression()
  # Extract column 1
  x = model_dataset.iloc[:, :-1].values
  # Extract column 2
  y = model_dataset.iloc[:, 1].values
  # Train the model
  regressor.fit(x, y)
  return regressor
</code></pre>
<p>→ <strong>Make a second function that will receive the <code>Fitted Estimator</code> and return a prediction.</strong></p>
<pre class=" language-plain"><code class=" language-plain">
# predict?
def boston_predict(estimator, array_to_predict):
 	...
</code></pre>
<pre class=" language-plain"><code class=" language-plain">data = [1, 2, 3]
estimator = boston_fit_model(dataset)
print(boston_predict(estimator, data))
</code></pre>
<h2>Technical Description</h2>
<p>You will have to implement multiple functions:</p>
<pre class=" language-plain"><code class=" language-plain">load_dataset()

# Analysis
print_summarize_dataset(dataset)
clean_dataset(dataset)
print_histograms(dataset)
compute_correlations_matrix(dataset)
print_scatter_matrix()

# Prediction
boston_fit_model(dataset)
boston_predict(estimator)
</code></pre>
<p>Gandalf will not accept any <code>pip install XXXX</code> inside your file.</p>
<p><strong>Additional resources</strong>
We like to print the evaluation prediction with this function:</p>
<pre class=" language-plain"><code class=" language-plain">def print_model_prediction_evaluator(base_test, prediction):
  print('Mean Absolute Error:', metrics.mean_absolute_error(base_test, prediction))
  print('Mean Squared Error:', metrics.mean_squared_error(base_test, prediction))
  print('Root Mean Squared Error:', np.sqrt(metrics.mean_squared_error(base_test, prediction)))

</code></pre>

<p></p>
</div>

</div>
</div>
</div>
<div class="tab-pane" id="resources" role="tabpanel">
</div>
</div>
</div>
