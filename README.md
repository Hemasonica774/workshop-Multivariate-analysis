# workshop-Multivariate-analysis

## Aim:

To Perform Bivariate/Multivariate Analysis

## Algorithm:

    1.Read the given data 2.Get information from the data 3.Perform the Bivariate/Multivariate Analysis
    2.Save the clean data to File

## program:

NAME : HEMASONICA.P
REG.NO : 212222230048

```

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("FlightInformation.csv")
df
df.head()
df.info()
df.isnull().sum()
df['Route'] = df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops'] = df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
df.shape
plt.figure(figsize=(8,5))
plt.xticks(rotation = 80)
sns.barplot(df["Airline"],df["Price"],hue=df["Total_Stops"])
states=df.loc[:,["Source","Price"]]
states=states.groupby(by=["Source"]).sum().sort_values(by="Price")
plt.figure(figsize=(8,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SOURCE")
plt.ylabel=("PRICE")
plt.show()
plt.figure(figsize=(5,7))
sns.scatterplot(df['Source'], df['Price'], hue=df['Destination'])
plt.xticks(rotation = 90)
df_count = df.groupby(by=["Source"]).count()
labels=[]
for i in df_count.index:
    labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette("Set2")
plt.pie(df_count["Price"], colors = colors, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.title("Source")
plt.show()
df['Airline'].value_counts()
df['Duration'].value_counts()
df_segment = df.groupby(by=["Total_Stops"]).count()
labels = []
for i in df_segment.index:
    labels.append(i)

plt.figure(figsize=(6,6))
colors = sns.color_palette('pastel')
pie = plt.pie(df_segment["Price"], colors = colors, autopct = "%0.0f%%",shadow = True)
plt.title("Total Stops")
plt.legend(pie[0], labels, loc="upper right")
plt.show()
df_region = df.groupby(by=["Destination"]).count()
labels = []
for i in df_region.index:
    labels.append(i)
    
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
pie = plt.pie(df_region["Price"], colors = colors, autopct = "%0.0f%%",shadow = True)
plt.title("Destination")
plt.legend(pie[0], labels, loc="upper right")
plt.show()

```

# Output:

![image](https://user-images.githubusercontent.com/118361409/229036291-55f9599e-1584-45fa-9f05-872741ed2277.png)

![image](https://user-images.githubusercontent.com/118361409/229036328-8dbff007-f1f0-40d5-b57b-398cd429198f.png)

![image](https://user-images.githubusercontent.com/118361409/229036361-91fd04a6-4094-41f3-8144-241b120cd508.png)

![image](https://user-images.githubusercontent.com/118361409/229036401-65588610-4dee-490b-ac67-dd96f7e34958.png)

![image](https://user-images.githubusercontent.com/118361409/229036466-d9012eeb-d33c-422c-af93-f115b8e32bc3.png)

![image](https://user-images.githubusercontent.com/118361409/229036506-ded3576a-c5e4-4cc5-ac44-00069007d8e9.png)

![image](https://user-images.githubusercontent.com/118361409/229036550-14dca1a8-f04d-4516-8dad-7767fef40225.png)

![image](https://user-images.githubusercontent.com/118361409/229036581-529c3598-9bb0-4b06-ba22-635c710e3373.png)

![image](https://user-images.githubusercontent.com/118361409/229036617-4c655a98-6dfd-459f-9dbb-e46f94c8b2d1.png)

![image](https://user-images.githubusercontent.com/118361409/229036750-a23f72de-d727-4a74-a2f2-7a5250d039c5.png)

![image](https://user-images.githubusercontent.com/118361409/229036835-2e90d38f-816b-475f-b303-1fd37a36a9de.png)

![image](https://user-images.githubusercontent.com/118361409/229036924-c76de99e-9f3f-4854-9bae-4fcbd12de522.png)

![image](https://user-images.githubusercontent.com/118361409/229037003-611cbe2d-d6e1-480d-ac1b-7749763991b8.png)

![image](https://user-images.githubusercontent.com/118361409/229037055-e75c92dc-8f42-4a90-a7ab-fdb670b4e898.png)

![image](https://user-images.githubusercontent.com/118361409/229037200-fd883c96-cb84-4420-9c97-99b41a5a1e72.png)


## Result :

Thus we applied Bivariate/Multivariate Analysis Successfully






