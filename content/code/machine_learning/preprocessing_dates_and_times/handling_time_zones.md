---
title: "Handling Time Zones"
author: "Chris Albon"
date: 2017-12-20T11:53:49-07:00
description: "How to handle timezones for machine learning in Python."
type: technical_note
draft: false
aliases: [/machine_learning/preprocessing_dates_and_times/handling_time_zones/]
---
## Preliminaries


```python
# Load libraries
import pandas as pd
from pytz import all_timezones
```

## View Timezones


```python
# Show ten time zones
all_timezones[0:10]
```




    ['Africa/Abidjan',
     'Africa/Accra',
     'Africa/Addis_Ababa',
     'Africa/Algiers',
     'Africa/Asmara',
     'Africa/Asmera',
     'Africa/Bamako',
     'Africa/Bangui',
     'Africa/Banjul',
     'Africa/Bissau']



## Create Timestamp With Time Zone


```python
# Create datetime
pd.Timestamp('2017-05-01 06:00:00', tz='Europe/London')
```




    Timestamp('2017-05-01 06:00:00+0100', tz='Europe/London')



## Create Timestamp Without Time Zone


```python
# Create datetime
date = pd.Timestamp('2017-05-01 06:00:00')
```

## Add Time Zone


```python
# Set time zone
date_in_london = date.tz_localize('Europe/London')
```

## Convert Time Zone


```python
# Change time zone
date_in_london.tz_convert('Africa/Abidjan')
```




    Timestamp('2017-05-01 05:00:00+0000', tz='Africa/Abidjan')


