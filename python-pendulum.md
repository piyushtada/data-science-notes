Pendulum module provide good tools for dealing with date time objects in python.
[Pendulum Documentation](https://pendulum.eustace.io/docs/)
```python
# Import the pendulum module
import pendulum

# Create a now datetime for Tokyo: tokyo_dt
tokyo_dt = pendulum.now('Asia/Tokyo')

# Covert the tokyo_dt to Los Angeles: la_dt
la_dt = tokyo_dt.in_timezone('America/Los_Angeles')

# Print the ISO 8601 string of la_dt
print(la_dt.to_iso8601_string())
```
```python
# Iterate over date_ranges
for start_date, end_date in date_ranges:

    # Convert the start_date string to a pendulum date: start_dt 
    start_dt = pendulum.parse(start_date, strict = False)
    # Just pass it a date string and it will attempt to convert into a valid pendulum datetime. By default, .parse() can process dates in ISO 8601 format. To allow it to parse other date formats, pass strict = False.
    
    # Convert the end_date string to a pendulum date: end_dt 
    end_dt = pendulum.parse(end_date, strict = False)
    
    # Print the End and Start Date
    print(end_dt, start_dt)
    
    # Calculate the difference between end_dt and start_dt: diff_period
    diff_period = start_dt - end_dt
    
    # Print the difference in days
    print(diff_period.in_days())
```