```python
row_list = []
for index, row in tqdm(parsed_df.iterrows()):
   row_list.append({
    'new_name': row["c_name"],
   }) 
df = pd.DataFrame(row_list)
```
