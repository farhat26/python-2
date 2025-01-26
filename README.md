import pandas as pd
df= pd.read_csv("D:\\pf\\dataa 45.csv")
df.shape
# Cleaning of data
df.info()
#df = pd.DataFrame(df)
column = list(df.columns)
column
# check empty values
df.isna().sum()
#cleaning of empty data set
df.dropna()
df.dropna(inplace=True)
df
# Replacing of empty values
df.fillna(22)
# Replacing of specific column
df['Name'].fillna(44)

# mean
df['Teaching'].mean() # take out average
# mode
df['Teaching'].mode()# most common
# median
df['Teaching'].median()# middle value
# Duplications of data
df.duplicated()
#pd.set_option("display.max_rows",None)
#pd.set_option("display.max_columns",None)
#df.duplicated()
df.drop_duplicates()
df.describe()
df.describe(include="all").iloc[[0,10,]]# fetch data from index or position
df.describe(include="all").loc[["min","max"]]#fetch data from values of list
# Adding new column in data frame
df['min']=9
df
# Remove a column
df.drop(columns=['min'],inplace=True)
df
# Add a row
a=pd.DataFrame({' University':100,
                'Country':'Pakistan',
                  'city':'Lahore'},
                  index=[5])
a
df=pd.concat([a,df])
df
# Remove a row
df.drop(5,inplace=True)
df
# Slicing in code
df[3:7]
df[3:7:2]
df[['Name']][45:56]
# Flow charts
df['International Students'].value_counts().plot(kind="bar")
df['International Students'].value_counts().plot(kind="barh")
df['International Students'].value_counts().plot(kind="box")
df['International Students'].value_counts().plot(kind="density")
df['International Students'].value_counts().plot(kind="pie")
df['International Students'].value_counts().plot(kind="line")
df['International Students'].value_counts().plot(kind="kde")
df['International Students'].value_counts().plot(kind="hist")
# Data aggregation
df.aggregate(['sum', 'min'])
df['International Students'].sum()
# Standard derivation
df['Teaching'].std()
# Varience calculations
df['Teaching'].var()
# Data preprocessing
df.isnull().sum() 
# Data saving
pip install openpyxl
df = pd.read_csv("D:\\pf\\dataa 45.csv")
df
df.to_excel("newdata.xlsx", sheet_name="newsheet")
