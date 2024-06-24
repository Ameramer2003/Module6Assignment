# Module6Assignment
6HW

Problems 1 and 2-

While changing the code to accommodate the current time, I encountered a problem where my script created an infinite for loop.  I will post the code.

Script:

import sys
from datetime import datetime, timedelta

for line in sys.stdin:
    data = line.strip().split("\t")
    if len(data) == 6:
        date_str, time_str, store, item, cost, payment = data
        dt = datetime.strptime(f"{date_str} {time_str}")

        dt_minus_60_sec = dt - timedelta(seconds=60)
        dt_plus_2_years = dt_minus_60_sec.replace(year=dt_minus_60_sec.year + 2)

        print("Original datetime:", dt)
        print("subtract 60 seconds:", dt_minus_60_sec)
        print("add 2 years:", dt_plus_2_years)
        print("{0}\t{1}".format(item, cost))
Code:

C:\Users\halam\PycharmProjects\pythonProject\.venv\Scripts\python.exe "C:\Users\halam\PycharmProjects\pythonProject\Module 6 HW.py" 

Problem 3- 

With this problem, we can create a timedelta object representing the given times and units to represent these times.  We can easily input a dateime timedelta to represent each of the times being 10 days, 100 hours, and 13 minutes.

Script:
from datetime import timedelta

d = timedelta(days=100, hours=10, minutes=13)

print("Days:", d.days)
print("Seconds:", d.seconds)
print("Microseconds:", d.microseconds)
Code:
C:\Users\halam\PycharmProjects\pythonProject\.venv\Scripts\python.exe "C:\Users\halam\PycharmProjects\pythonProject\Module 6 HW.py" 
Days: 100
Seconds: 36780
Microseconds: 0

Process finished with exit code 0

*No microseconds because it was not specified.

Problem 4-

This problem similarly uses the timedelta function, but instead we take 2 different units and convert them using this function to aquire like terms.  From here we can simply add the two in order to get a combined answer for a sum of inches.  Here is the Script and Code

Script:
from datetime import datetime, timedelta


def add_feet_inches_to_current_datetime(feet, inches):
    current_datetime = datetime.now()
    print("Current datetime:", current_datetime)

    total_inches = (feet * 12) + inches

    total_seconds = total_inches

    time_delta = timedelta(seconds=total_seconds)

    new_datetime = current_datetime + time_delta

    print("New datetime:", new_datetime)
    print('Type of new datetime:', type(new_datetime))

    return new_datetime
Code:
* With an example of how it's applied:
# Example usage
feet = 5
inches = 8
new_dt = add_feet_inches_to_current_datetime(feet, inches)
Result:
C:\Users\halam\PycharmProjects\pythonProject\.venv\Scripts\python.exe "C:\Users\halam\PycharmProjects\pythonProject\Module 6 HW.py" 
Current datetime: 2024-06-23 21:04:19.107634
New datetime: 2024-06-23 21:05:27.107634
Type of new datetime: <class 'datetime.datetime'>

Process finished with exit code 0

