## Underfitting v.s, Overfitting
**Underfitting**: 
- the model is too simple (shallow)
- too many data in a singular group
  - not acurate

**Overfitting**: 
- the model is too complex (deep)
- More depth, more splited groups 
- the features are too specific
  - train data well
  - val data not fit


### Example

```python
from sklearn.metrics import mean_absolute_error
from sklearn.tree import DecesionTreeRegressor

def get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y):
    model = DecisionTreeRegressor(max_leaf_nodes= max_leaf_nodes, random_state = 0)
    model.fit(train_X, train_y)
    preds_val = model.prediction(val_X)
    mae = mean_absolute_error(val_y, preds_val)
    return(mae)
```

use for loop to compare the accuracy of how the max node is
```python
for max_leaf_nodes in [5, 50, 500, 5000]:
    my_mae = get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y)
    print("Max leaf nodes: %d  \t\t Mean Absolute Error:  %d" %(max_leaf_nodes, my_mae))
```
```
Max leaf nodes: 5  		 Mean Absolute Error:  347380
Max leaf nodes: 50  		 Mean Absolute Error:  258171
Max leaf nodes: 500  		 Mean Absolute Error:  243495
Max leaf nodes: 5000  		 Mean Absolute Error:  254983
```
where 500 nodes have the least error