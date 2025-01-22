## Data

use pandas
` import pandas as pd`

``` python
file = 'path'
the_data = pd.read_csv(file)
the_data.describe() # show some commom stat value
```

count: could be used to see if there is some value misses or not
mean: average
std: standard deviation., how the values are spreaded
min, 25%, 50%, 765%, max: percentile, getting aftert sorting