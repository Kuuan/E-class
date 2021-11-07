# 十分鐘學會Python

![image](https://user-images.githubusercontent.com/89329117/140632109-56a45359-4ba9-4674-96e2-e0d2315dac38.png)

# CODE
````c
# task 1: string variable
name = "Kuuan"
print(name)

# task 2: number variable
number = 26
print(number)
print(number*3)
print(number/2)
print(number + number)
print(number - number)

# task 3: function

def printName(firstName, lastName):
  print(lastName + ' ' + firstName)

printName('Kuuan', 'Taoyuan')

# task 4: if else

def printName(firstName, lastName, isCool):
  if isCool:
    print(lastName + ' ' + firstName + ' very cool!')
  else:
    print(lastName + ' ' + firstName + ' not cool!')

# Start
printName('Kuuan', 'Taoyuan', True)
printName('Kuuan', 'Taoyuan', False)

# task 5: for loop

def printName(firstName, lastName, isCool, num):
  for i in range(1, num):
    if isCool:
      print(i, lastName + ' ' + firstName + ' very cool!')
    else:
      print(i, lastName + ' ' + firstName + ' not cool!')

# Start
printName('Kuuan', 'Taoyuan', True, 10)

````
