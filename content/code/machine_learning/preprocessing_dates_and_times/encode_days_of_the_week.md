---
title: "Encode Days Of The Week"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to the days of the week for dates and times for machine learning in Python."
type: technical_note
draft: false
aliases: [/machine_learning/preprocessing_dates_and_times/encode_days_of_the_week/]
---
## Preliminaries


```python
# Load library
import pandas as pd
```

## Create Date And Time Data


```python
# Create dates
dates = pd.Series(pd.date_range('2/2/2002', periods=3, freq='M'))

# View data
dates
```




    0   2002-02-28
    1   2002-03-31
    2   2002-04-30
    dtype: datetime64[ns]



## Show Days Of The Week


```python
# Show days of the week
dates.dt.weekday_name
```




    0    Thursday
    1      Sunday
    2     Tuesday
    dtype: object


