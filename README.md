# multilinearregression
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
#load dataset
df = pd.read_csv('/content/minihomeprices.csv')
#display first few rows of the dataset
print(df.head())
print(df.info())
print(df.describe())
print(df.isna().sum())
df['bedrooms']=df['bedrooms'].fillna(df['bedrooms'].median())
plt.figure(figsize=(10,7))
plt.figure("Bedroom wise price increase")
plt.xlabel("Bedrooms")
plt.ylabel('price')
sns.barplot(x='bedrooms',y='price',data=df)
plt.show()
plt.figure(figsize=(10,7))
sns.lmplot(x='bedrooms',y='price',data=df)
plt.title("price and bedroom wise  price line plot")
plt.xlabel("house bedrooms")
plt.ylabel("house price")
plt.show()
plt.figure(figsize=(10,5))
plt.title("price vs bedroom scatterplot")
plt.xlabel("house bedrooms")
plt.ylabel("house price")
sns.scatterplot(x='bedrooms',y='price',data=df)
plt.show()
