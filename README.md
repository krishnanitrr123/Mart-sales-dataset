This repository contains data cleaning steps performed on the Big Mart Sales dataset. The focus of this project is on identifying and handling missing values and duplicate entries to prepare the data for further analysis or modeling.
In this dataset two columns(Outlet_Size, Item_Weight) has the huge number of missing values(NaN).
Both column has different datatype(string, integer).
Method apply to handle these missing values-
Median- for integer
Mode- string

Main function used in this method- (df-is a variable for main dataset)
1.df=pd.read_csv('Train.csv')
#To read the dataset
2.df.isnull().sum()
3.df['Outlet_Size'] = df['Outlet_Size'].map({"Small":1,"Medium":2,"High":3})
#To convert string  to integers we use the mapping.
4.df['Item_Weight']=df['Item_Weight'].fillna(df['Item_Weight'].median())
#We  use the median to fill the missing integer value
5.df['Outlet_Size'].fillna(df['Outlet_Size'].mode()[0], inplace=True)
#We use the mode to fill the  missing string values.
