# Age_Calculator
I have made this calculator to calculate your age. You can calculate your age by choosing the proper option. You can calculate your age by year months days hours minutes or seconds.Thank You...

from datetime import datetime

def Calculate_Age(birthdate , unit):
  now = datetime.now()
  delta = now - birthdate
  total_seconds = delta.total_seconds()

  if unit == 'years':
    return delta.days // 365
  elif unit == 'months':
    return delta.days // 30 * 12
  elif unit == 'days':
    return delta.days
  elif unit == 'hours':
    return int(total_seconds//3600)
  elif unit == 'minutes':
    return int(total_seconds//60)
  elif unit == 'seconds':
    return int(total_seconds)
  else:
    return 'Invalid unit'

def age_Calculater():


  birthdate = input("Enter your birthdate (YYYY-MM-DD): ")

  birthdate = datetime.strptime(birthdate, '%Y-%m-%d')

  print("1. years")
  print("2. months")
  print("3. days")
  print("4. hours")
  print("5. minutes")
  print("6. seconds")

  Option = input("Enter Option: ")

  units = {
    '1': 'years',
    '2': 'months',
    '3': 'days',
    '4': 'hours',
    '5': 'minutes',
    '6': 'seconds'
  }

  unit = units.get(Option, 'Invalid Option')
  if unit == 'Invalid Option':
    print("Invalid Option")
    return


  age = Calculate_Age(birthdate, unit)
  print(f"Your age is {age} {unit})")

age_Calculater()
