# Dealing with datetime
```python
# Import the datetime object from datetime
from datetime import datetime

# Iterate over the dates_list 
for date_str in dates_list:
    # Convert each date to a datetime object: date_dt
    date_dt = datetime.strptime(date_str, '%m/%d/%Y')
    
    # Print each date_dt
    print(date_dt)
    
# Loop over the first 10 items of the datetimes_list
for item in datetimes_list[:10]:
    # Print out the record as a string in the format of 'MM/DD/YYYY'
    print(datetime.strftime(item, '%m/%d/%Y'))
    
    # Print out the record as an ISO standard string
    print(datetime.isoformat(item))

```
# when we want to find the monthly count of something
```python
# Create a defaultdict of an integer: monthly_total_rides
monthly_total_rides = defaultdict(int)

# Loop over the list daily_summaries
for daily_summary in daily_summaries:
    # Convert the service_date to a datetime object
    service_datetime = datetime.strptime(daily_summary[0],'%m/%d/%Y')

    # Add the total rides to the current amount for the month
    monthly_total_rides[service_datetime.month] += int(daily_summary[4])
    
# Print monthly_total_rides
print(monthly_total_rides)

```

# what is current time?
```python
# Import datetime from the datetime module
from datetime import datetime

# Compute the local datetime: local_dt
local_dt = datetime.now()

# Print the local datetime
print(local_dt)

# Compute the UTC datetime: utc_dt
utc_dt = datetime.utcnow()

# Print the UTC datetime
print(utc_dt)
```

```python
# Import timedelta from the datetime module
from datetime import timedelta

# Build a timedelta of 30 days: glanceback
glanceback = timedelta(days=30)

# Iterate over the review_dates as date
for date in review_dates:
    # Calculate the date 30 days back: prior_period_dt
    prior_period_dt = date - glanceback
    
    # Print the review_date, day_type and total_ridership
    print('Date: %s, Type: %s, Total Ridership: %s' %
         (date, 
          daily_summaries[date]['day_type'], 
          daily_summaries[date]['total_ridership']))

    # Print the prior_period_dt, day_type and total_ridership
    print('Date: %s, Type: %s, Total Ridership: %s' %
         (prior_period_dt, 
          daily_summaries[prior_period_dt]['day_type'], 
          daily_summaries[prior_period_dt]['total_ridership']))
```