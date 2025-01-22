## Selecting data for modeling

- could be start by picking a few variable using our intuition

Need the column label (.columns)
```python
import pandas as pd
the_file_path = 'path'
the_data = pd.read_csv(the_file_path)
print(the_data.columns)
```
`output: index(['label1', 'label2', ...], dtype = 'object')`

fundemental approaches
1. Dot notation, use for selecting "prediction target"
2. Selecting with a column list, use for selecting "features"

**Prediction target**
`Y = the_data.The_column`

**Features**
`X = the_data['column_labels']`

## Building the model
- use **scikit_learn** library
- when coding, this library is written as **sklearn**

**The steps to building and using a model**
1. **Define**:
   - what type of the model will it be?
   - what are the parameters?
2. **Fit**: capture the patterns from provided data
3. **Predict**
4. **Evaluate**: determine how accurate the model's predictions are?


##### Example
```python
from sklearn.tree import DecisionTreeRegressor

# Define model
# random_state would specify the seed
the_model=DecisionTreeRegressor(random_state=1)

# fit model
the_model.fit(x,y)

print("Making predictions for the following 5 ___:")
print(the_data.head())
print("The predictions are")
print(the_model.predict(the_data.head()))
```
**random_state**
- 一個控制隨機性的**參數**，用來指定隨機生成器的「種子」(seed)
- 指定相同random_state後（相同種子）可以保證隨機生成器生成的隨機數列一樣
  - 同隨機數列可以實現結果重現

```python
# 沒有指定 random_state
random_num_sequence(random_state=None)  # 每次執行結果不同

# 指定種子值
random_num_sequence(random_state=1)  # 生成序列 no.1
random_num_sequence(random_state=2)  # 生成序列 no.2

# 使用相同種子再次生成
random_num_sequence(random_state=1)  # 再次生成序列 no.1
```


