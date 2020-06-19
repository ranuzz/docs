> by iterating and creating a new df

```python
row_list = []
for index, row in tqdm(parsed_df.iterrows()):
   row_list.append({
    'new_name': row["c_name"],
   }) 
df = pd.DataFrame(row_list)
```

> by renaming columns and dropping not required columns

```python
 parsed_df = pd.read_csv(data_path)
 renamed_df = parsed_df.rename(columns={
   'c_name' : 'new_name'
 })
 trimmed_df = renamed_df.drop(['rest' ], axis=1)
 #return trimmed_df
```
