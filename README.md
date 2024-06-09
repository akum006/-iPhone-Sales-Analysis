# -iPhone-Sales-Analysis

import pandas as pd
import numpy as np
import plotly.express as px
import plotly.graph_objects as go

data = pd.read_csv('/content/apple_products.csv')
data.head()
data.isnull().sum()
data.describe()

highest_rated = data.sort_values('Star Rating',ascending = False)
highest_rated = highest_rated.head(10)
highest_rated['Product Name']

iphones = highest_rated['Product Name'].value_counts()
label = iphones.index

counts = highest_rated['Number Of Ratings']

fig = px.bar(highest_rated, x = label, y = counts, title = "Number of Ratings of Highest Rated iPhones")
fig.show()

iphones = highest_rated['Product Name'].value_counts()
label = iphones.index
counts = highest_rated['Number Of Reviews']

fig = px.bar(highest_rated, x = label, y = counts, title = "Number of Ratings of Highest Rated iPhones")
fig.show()

figure = px.scatter(data_frame = data, x = 'Number Of Ratings', y = 'Sale Price', size = 'Discount Percentage', trendline = 'ols', title="Relationship between Sale Price and Number of Ratings of iPhones")
figure.show()

figure = px.scatter(data_frame = data, x = 'Number Of Ratings', y = 'Discount Percentage', size = 'Sale Price', trendline = 'ols', title="Relationship between Sale Price and Number of Ratings of iPhones")
figure.show()
