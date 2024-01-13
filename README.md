# PANDAS-Adding-Removing-Data
Adding / Removing 
1. Series - # To create a series. ( Homogeneous Data, Size Immutable, Values Mutable )
pd.Series(data, index=, dtype=, name=) 
Series([1,2,3,4], index=list(‘abcd’), name=’new’) ,
pd.Series(np.random.random(3), index =[‘delhi’,’mumbai’,’agra’]), 
Series({‘a’:1, 2:’b’, ‘c’:’ram’}), 
pd.Series(data) , data=[[1,2,3],[4,5,6]]. 
2. DataFrame - # To create a dataframe. ( Hetrogenous Data , Size Mutable, Data Mutable ) 
pd.DataFrame(data=, index=, columns= ) , 
pd.DataFrame( np.arange(1,10).reshape(3,3), index=[‘a’,’b’,’c’], columns = list(‘XYZ’)) , 
pd.DataFrame({‘A’:[‘a’,’b’], ‘B’:list(‘cd’), ‘C’:[1,2], ‘D’:list(‘34’) })
pd.DataFrame( [[1,2,3],[4,5,6],[7,8,9]] ) 
pd.DataFrame( np.random.rand(4,5) ) 
3. Adding a new DF to existing - df2 = df2.append( df1 ) 
 # It will append the rows of df1 at the end of df2. 
4. Reindexing a DataFrame - df_r = df1.reindex(index=[0,2,5,7] , columns = ['A', 'C' , 'B']) 
# It will create a new dataframe with the mentioned indexes only of df1. 
df2.reindex_like( df1, method = ‘ffill’ , limit = 1 )
5. Adding New Row/Index # To add a new row in the series 
s.loc[‘new index’] , 
s.loc[6]=’rohit’ , 
s.loc[‘new’]=39 
6. Removing Row/Index # To remove a row from the series. 
s.drop(‘index’) , 
s.drop(6) , 
s.drop(‘new’) 
7. Adding New Column - # To add new column in the DF. 
df[‘New_col’]= , 
df[‘C’] = list(‘qwerty’) , 
df.insert(2, ‘C’, [1,2,3,4,5]) 
df.insert( index , ‘new_column_name’, new_column_values) - To insert a New column at a particular 
position with values in it.
8. Adding New Row - # To add new row in the DF. 
df.loc[‘New_row’]= , 
df.loc[‘R’] = list(‘12345’) , 
df.loc[‘R’ , 2:5] = 78 
9. Assign ( ) - # It is used for creating new variables on the fly , or for deriving new 
column from existing ones. 
df.assign( H = lambda x:x[‘C’]+2 ) , 
df.assign(I=21 , J = list(‘qwerty’)) 
10. Removing Rows - 
df.drop(‘index_name’) , 
df.drop(index_value) , 
df.drop(‘index_name’, axis=0, inplace=True), 
df.drop( [‘Row1’ , ‘Row2’ , ‘Row3’] ) , df.drop( [1,2,4] ). 
11. Removing Columns - 
df.drop(‘Col_name’ , axis=1) , 
del df[‘Col_name’] , 
df.drop( [‘Col1’ , ‘Col2’, ‘Col3’ ], axis=1 ) 
df.pop(‘Col_name’) 
12. Creating missing values - 
df.loc[‘Row_index’] = np.nan , 
df[‘Col_name’] = None
13. pd.merge( df1, df2, on=’Col_Name’ , how=’inner/outer/left/right’ ) 
# Merge ( ) - Column names must be same. Default – Inner Join.
14. pd.merge( df1, df2, left_on=’df1_Col_Name’ , right_on=’df2_Col_Name’, how=’inner/outer’ ) 
• inner - works on common indexes/columns/elements only , outer - works on all 
indexes/columns/elements
• left - works on left DF , right - works on right DF. 
15. df1.join(df2, how = ‘inner/outer/left/right’) , df1.join( [df2,df3] ) 
# Join ( ) - Indexes may or may not be same. Column names must be different. Default - Left join.
16. pd.concat( [df1,df2] , axis=0/1 , join=’inner/outer’ ) 
# DF Concat - In concat(with rows axis) - Rows below Rows without merge/sort and Columns will 
merge/sort . In concat(with columns axis1) - Columns side by side without merge/sort and Rows will 
merge/sort.
17. pd.concat( [S1,S2,S3], axis=1, join=’outer/inner’) 
