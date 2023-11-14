# Ex-01_DS_Data_Cleansing
## DATE:


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

## Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

## CODE and OUTPUT

```
DEVELOPED BY :HARINI V
REG NO : 212222230044
```
```
import pandas as pd
df = pd.read_csv("SAMPLEDS - Sheet1.csv")
df.shape
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/6eaa6cfe-3d00-41b8-936b-badc33c4c1d0)
```
df.head()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/8fd44750-4fd9-4cd6-9c03-593fbebd773a)
```
df.tail()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/3787a1e0-4e52-4175-bca5-4c4496db2686)
```
df.dropna(how='any').shape
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/19cf1215-2746-4ae0-adea-8830805951a4)
```
x=df.dropna(how='any')
x
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/6e3a0042-9fd3-4cd0-a036-a86227a03941)
```
df.dropna(how='all').shape
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/fa31be01-7b43-4aaf-8cc3-7d7b8471487c)
```
tot=df.dropna(subset=['TOTAL'],how='any')
tot
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/4228748b-9458-4e81-ad23-78ac068442f9)
```
tot=df.dropna(subset=['M1','M2','M3','M4'],how='any')
tot
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/6c089800-de78-45d9-ac80-62a5970608cd)
```
df.fillna(0)
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/46478637-5bb7-4975-b3d7-8d6a5a7b52a0)
```
df.fillna(method='ffill')
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/deea7dc4-f8e1-407c-9200-406b1482374f)
```
df.fillna(method='bfill')
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/0efc5712-bdcf-4f05-9a94-4cbb9e236719)
```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/250fe794-a40d-4223-8ecf-aa97389639f3)
```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/091ecdd4-6ba4-49d5-ba0b-7ddf4868e396)
```
df.duplicated()
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/48c4d219-18e4-4563-9cce-57dd86de1a7a)
```
df.drop_duplicates(inplace=True)
df
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/70294b50-5498-4b6b-bd75-04c5d6a9f544)
```
df['cd']=pd.to_datetime(df['DOB'])
df
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/94661451-6a91-4c87-b073-1b6868135b7c)
```
for x in df.index:
  if df.loc[x,"AVG"]>100:
    df.drop(x,inplace=True)
df
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/69c408f8-82d6-4e6f-a491-9a171aac300e)
```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01/assets/118343698/a1f17f1e-80f1-4514-8e29-331c260d531d)

## RESULT
Thus,the given data is read,cleansed and the cleaned data is saved into the file.
