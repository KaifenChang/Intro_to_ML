# Summary
***
> Dataframe 
> - Row: data
> - Column: features

### RandomForest Model quick look
**The steps**
1. Define the model and parameters
2. Fit the data into the pattern
3. Predict
4. Evaluate for accuracy (val_data - train_data)
```python
import pandas as pd
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_absolute_error
from sklearn.model_selection import train_test_split

# import the data
file = 'path'
the_data = pd.read_csv(file)
the_data.describe()

# Get the features X (input)
# target value : y (actual output)
X = the_data[features]

# 1. Define the model
# 	split the data into trained and validated
the_model = RandomForestRegressor(random_state=1)
train_X, val_X, train_y, val_y = train_test_split(X, y, random_state = 0)

# 2. Fit (plot the traning data) 
the_model.fit(train_X, train_y)

# 3. Predict 
# (use for accurency, so must not be the training data)
prediction = the_model.predict(val_X)

# 4. Evaluate (use mean absolute error to determine the accurency)
mean_absolute_error(val_y, prediction)

```
