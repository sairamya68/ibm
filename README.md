# ibm
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv('DoctorVisit.csv')
df.head(15)
df.tail(10)
df.info()
df.shape
df.columns
df['illness'].value_counts()
df['gender'].value_counts()
y=list(df.income)
plt.boxplot(y)
plt.show()
df.columns
df.groupby(['gender','reduced']).mean()
plt.figure(figsize=(10,10))
sns.heatmap(df.corr(),cbar=True,annot=True,cmap='Blues')
plt.figure(figsize=(10,10))
plt.scatter(x='income',y='visits',data=df)
plt.xlabel('income')
plt.ylabel('visits')
sns.histplot(df.gender,bins=2)
db=df.groupby('gender')['reduced'].sum().to_frame().reset_index()
#creating the bar chart
plt.barh(db['gender'],db['reduced'],color=['cornflowerblue','lightseagreen'])
#adding the aesthetics
plt.title('Bar Chart')
plt.xlabel('gender')
plt.ylabel('reduced activity')
plt.show()
df['freepoor'].hist()
plt.xlabel('freepoor')
plt.ylabel('count')
plt.title('freepoor count')
plt.show()
df['age'].hist()
plt.xlabel('age')
plt.ylabel('count')
plt.title('age count')
plt.show()
df['gender'].hist()
plt.xlabel('gender')
plt.ylabel('count')
plt.title('gender count')
plt.show()
df=df.drop_duplicates()
