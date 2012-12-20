##Notes

* use `set time_zone = '<zone>';`
  * to grab zone names: `select name from time_zone_name;`
* `str_to_date()` will convert a string into a date object
* If you are impatient or want to find the current time/etc:
  * `current_time()` or `current_date()` or `current_timestamp`

###Date format requirements

1. Date YYYY-MM-DD 
1. Datetime YYYY-MM-DD HH:MI:SS 
1. Timestamp YYYY-MM-DD HH:MI:SS 
1. Time HHH:MI:SS

###Manipulation

* `date_add(<current>, interval <amount> <interval>)`: perfect for
adding todays date by 5 days...or 3 minutes...or 10 years
* `select last_day(<date>)`: will select the last day in the month of
the date object
* `convert_tz()` would be used if you wanted to convert a specific time
zone
* Extract is used to return strings corresponding to specific parts of
the date object
  * `select extract(<year|day|hour|etc> from '<date>')`
* `datediff('<date1>', '<date2>')` will return the differance in days
between two dates
