# importing-datsets
Manipulation on attributes of Dataframes(head, tail, describe, info )
# Import pandas library
import pandas as pd

# Read the online file by the URL provides above, and assign it to variable "df"
other_path = "https://s3-api.us-geo.objectstorage.softlayer.net/cf-courses-data/CognitiveClass/DA0101EN/auto.csv"
df = pd.read_csv(other_path, header=None)
print("The first 5 rows of the dataframe & last 10") 
df.head(5)
df.tail(10)
headers = ["symboling","normalized-losses","make","fuel-type","aspiration", "num-of-doors","body-style",
         "drive-wheels","engine-location","wheel-base", "length","width","height","curb-weight","engine-type",
         "num-of-cylinders", "engine-size","fuel-system","bore","stroke","compression-ratio","horsepower",
         "peak-rpm","city-mpg","highway-mpg","price"]
print("headers\n", headers)
df.columns = headers
df.head(10)
df.dropna(subset=["price"], axis=0)
print(df.columns)
# check the data type of data frame "df" by .dtypes
print(df.dtypes)
# describe all the columns in "df" 
df.describe(include = "all")
df[['length', 'compression-ratio']].describe()
print(df.info)
