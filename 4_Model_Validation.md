## Model Validation
The relevent measure of model quality: predictive accuracy
- a.k.a. how close the prediction to the actual

**How to do?**
>Summarize the model quality into an understanable way (such as a single metric) 

start with **Mean Absolute Error (MAE)**
the prediction error is
```error = actual - predicted```

- MAE is average(sum of abs(error))
- in plain english: 
    On average, our predictions are off by about X (the features).

```python
from sklearn.metrics import mean_absolute_error

predicted = model.predict(X)
mean_absolute_error(y, predicted)
```

**Warning: in-score sampling**
Don't use traing data and compare the prediction to the target values
- need to split the data into 2 groups
  - one for training
  - one for validation

use ```**train_test_split**```
```python
from sklearn.model_selection import train_test_split

train_X, val_X, train_y, val_y = train_test_split(X, y, random_state = 0)

the_model = DecisionTreeRegressor()
the_model.fit(train_X, train_y)

val_prediction = the_model.predict(val_X)
print(mean_absolute_error(val_y, val_prediction))
```

#### Notes
情境：我們要根據房子的**大小、位置、建齡等特徵**來預測**房價**
- features：coloumns label => x (**輸入**) 
- target values： => y (**輸出**)  
