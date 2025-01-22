## Intro
Decision tree -> difficult dicision
Deep tree -> overfit
Shallow tree -> poor performance

Random forest
- use many trees
- predicted by averaging the predictrions of each component tree

### Example

```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.matrics import mean_absolute_error

forest_model = RandomForestRegressor(random_state=1)
forest_model.fit(train_X, train_y)
melb_preds = forest_model.predict(val_X)
print(mean_absolute_error(val_y, melb_preds))
```

output = 191669.753
improve from 250000