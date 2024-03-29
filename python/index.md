# Python Basic Syntax

***Python is used in automation of taskes.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

# Introduction
***Python*** is a beginner-friendly, interpreted programming language known for its readability and versatility. With a vast standard library and cross-platform compatibility, it's widely used in ***web development***, ***data science***, and ***automation***.

### Print function
```python
print("it's meeeeeeeeeeee")
print('o----')
print(' ||||')


print('*' * 10)
```
{{< admonition type=warning title="output" open=false >}}
    it's meeeeeeeeeeee
    o----
    ||||
    **********
{{< /admonition >}}


### Datatype
```python
price = 10          # integer
rating = 4.9        # floating
name = 'sumit'      # string
is_present = False  # boolean
print(price)
```

### Input function
```python
name = input('what is your name? ')  # taking input and store as a 'name' variable
fav_colour = input('what is your favourite colour? ')
print(name + ' likes ' + fav_colour)

birth_year = input('Birth Year: ')
print(type(birth_year))
age = 2023 - int(birth_year)
print(type(age))
print(name + "'s age is: " + str(age))

weight_lbs = input('what is your weight(lbs): ')
weight_kg = int(weight_lbs) * 0.45
print ('weight in kg is: ' + weight_kg)


name = 'John Smith'
age = 20
is_new_patient = True
```


### String and character

#formatted string 
```python
first ='sumit'
last = 'kr'
message = first +'[' + last + '] is a programmer.'
msg = f'{first} [{last}] is a coder'  # <---formated give same output as message
print(message)
```
{{< admonition type=warning title="output" open=false >}}
    sumit [kr] is a programmer.
{{< /admonition >}}

### Length of a string
```python
string = 'you are awesome.'
print(len(string)) #general purpose function

# output->  16
```


### Converting lower case to uppercase
```python
compliment = 'You are awesome.'
print(compliment.upper())  #method 
# output-> YOU ARE AWESOME.
print(compliment.lower())
#output-> you are awesome.
```

### Returning the index of a character in a string
```python
statement = 'you are awesome.'
print(statement.find('o'))
# output-> 1
```



### Replacing a word in a string
```python
statement = 'hii this is sumit.'
print(statement.replace('sumit','sumit kr'))
# output-> hii this is sumit kr.
print(statement.replace('su','a'))
#output-> hii this is amit.
```

### Checking if the string contain a word or not
```python
statement = 'hii this is sumit.'
print('sumit' in statement)

#output-> True
```



### Arithmatic operations 
```python
print(10+3)    # output-> 13
print(10/3)    # output-> 3.333333
print(10//3)   # output-> 3
print(10%3)    # output-> 1
print(10 ** 3) # output-> 1000  (ten to the power three)
```

### Augmanted assignment operator
```python
x= 10
x = x + 3
x += 3  # <-- same as upper line which is 13
x -= 3  # output-> 7
x *= 3
x /= 3
```

### Presidence order 
1. parenthesis
2. exponentiation  2**3
3. multiplication or division
4. addition or subtraction
```python
x= 10 + 3 * 2 ** 2    #output-> 22
x= (10 + 3) * 2 ** 2  #output-> 56
```

### Math function 
```python
x= 2.9
print(round(x))   #output-> 3
print(abs(-2.9))  # output-> 2.9   (absolut function)

import math            # <--math module in python
print(math.ceil(2.9))  # output-> 3
print(math.floor(2.9)) # output-> 2
```

### If and else if statement
```python
is_hot = True
is_cold = False

if is_hot:
    print("It's a hot day")
    print("drink plenty of water")
elif is_cold:
    print("its a cold day")
    print("wear warm cloth")
else:
    print("its a lovely day")
```
{{< admonition type=warning title="output" open=false >}}
    It,s a hot day
    drink plenty of water
{{< /admonition >}}

### Task
```python
price = 1000000
has_good_credit = True

if has_good_credit:
    down_payment = 0.1 * price
else:
    down_payment = 0.2 * price
print(f"Down Payment: {down_payment}")
```
{{< admonition type=warning title="output" open=false >}}
    100000
{{< /admonition >}}

### Logical opoerators
### Task
```python
has_high_income = True
has_good_credit = True

if has_high_income and has_good_credit:   # and operator both condition should be true
    print("Eligible for loan")
else:
    print("not eligible for loan")

# output-> Eligible for loan
    
has_high_income = True
has_good_credit = False

if has_high_income or has_good_credit:  # or operator
    print("Eligible for loan")
else:
    print("not eligible for loan")
# output-> Eligible for loan
    
has_good_credit = True
has_criminal_record = False

if has_good_credit and not has_criminal_record:   # not operator
    print("Eligible for loan")
else:
    print("not eligible for loan") 
```
{{< admonition type=warning title="output" open=false >}}
    Eligible for loan
{{< /admonition >}} 

### Comparision operator
   > , < , >= , <= , == , !=
### Task
```python
temperature = 30

if temperature >= 30:
    print("it's a hot day")
elif temperature < 30:
    print("it's a cold day")
```
{{< admonition type=warning title="output" open=false >}}
    it's a hot day
{{< /admonition >}} 

    
### Task
```python
name = input("enter name: ")
if len(name) < 3:
    print("name should be greater than 3.")
elif len(name) > 30:
    print("should be less than 30 characters.")
else:
    print('looks good.')
```

### While loops
```python  
i = 1
while i <= 5:
    print('*' * i)
    i= i +1
print('Done')
```
{{< admonition type=warning title="output" open=false >}}
    *
    **
    ***
    ****
    *****
    Done
{{< /admonition >}} 

            

### Task: Guess number
```python
secreat_number = 9
guess_count = 0
guess_limit = 3

while guess_count < guess_limit:
    guess = int(input('Guess: '))
    guess_count += 1
    if guess == secreat_number:
        print('you are right.')
        break
else:
    print('sorry you failed')
```

### Task: Car game
```python
command = " "
started = False
while True:
    command = input("> ").lower()
    if command  == "start":
        if started:
            print("Car is already started!")
        else:
            started = True
            print("Car started...")
    elif command  == "stop":
        if not started:
            print("Car is already stopped!")
        else:
            print("Car stopped.")
            started = False
    elif command == "quit":
        break
    elif command == "help":
        print("""
start - to start the car
stop - to stop the car
quit - to quit
        """)
    else:
        print("Sorry, I don't understand that.")
```

### For loop
```python
for item in 'python':
    print(item)

for item in ['balram','sumit', 'prateek', 'shams']:
    print(item)

for item in [1,2,3,4]:
    print(item)

for item in range(10):  # range-> builtin fun
    print(item)         # output-> 0 to 9

for item in range(5,10):
    print(item)         # output-> 5 to 9

for item in range(5,10,2):
    print(item)         # output-> 5,7,9


```
### Task
```python
prices = [10,20,30]
total = 0
for price in prices:
    total = total + price

print(f"Total: {total}")    # output-> 60
```

### Nested loop
adding one loop in the another loop
```python
for x in range(4):
    for y in range(3):
        print(f'({x},{y})')
```

### Task
```python
numbers = [5,2,5,2,2]

# method 1
for x_count in numbers:
    print('x' * x_count)

# method 2
for x_count in numbers:
    output = ''
    for count in range(x_count):
        output += 'x'
    print(output)
```
{{< admonition type=warning title="output" open=false >}}
    xxxxx
    xx
    xxxxx
    xx
    xx

    xxxxx
    xx
    xxxxx
    xx
    xx
{{< /admonition >}} 

### Lists
```python
names = ['arjun', 'kaishar', 'saif', 'prateek', 'sumit']
print(names)       # output-> ['arjun', 'kaishar', 'saif', 'prateek', 'sumit']
print(names[2])    # output-> saif
print(names[-1])   # output-> sumit
print(names[2:])   # output-> ['saif', 'prateek', 'sumit']
print(names[2:4])  # output-> ['saif', 'prateek']

```
### Task: Largest no
find the largest number in the list
```python
numbers = [2,3,6,7,4,9,10]
max = numbers[0]
for item in numbers:
    if item > max:
        max = item
print(max)

# output-> 10
```

### 2D lists
```python
matrix = [
    [1,2,3],
    [4,5,6],
    [7,8,9]
]

print(matrix[0][1])  # output-> 2

matrix[0][1] = 20
print(matrix[0][1])  # output-> 20

for row in matrix:
    for item in row:
        print(item)  # output-> 1 to 9 in seperate line
```

### List methods
```python
numbers = [5,2,1,7,4]
numbers.append(20)
print(numbers)      # output-> [5,2,1,7,4,20]
numbers.insert(0, 10)
print(numbers)      # output-> [10,5,2,1,7,4,20]

numbers.remove(5)
print(numbers)      # output-> [10,2,1,7,4,20]

numbers.clear()
print(numbers)      # output-> []

numbers = [5,2,1,7,4]                        
numbers.pop()               # output-> [5, 2, 1, 7]
print(numbers)

numbers = [5,2,1,7,4]
print(numbers.index(5))     # output-> 0
# print(numbers.index(50))  # output-> 50 is not in the list
print(50 in numbers)        # output-> False

numbers = [5, 2, 1, 5, 7, 4]
print(numbers.count(5))     # output-> 2

numbers.sort()
print(numbers)              # output-> [1, 2, 4, 5, 5, 7]
numbers.reverse()
print(numbers)              # output-> [7, 5, 5, 4, 2, 1]
numbers2 = numbers.copy()
numbers.append(10)
print(numbers)              # output-> [7, 5, 5, 4, 2, 1, 10]
print(numbers2)             # output-> [7, 5, 5, 4, 2, 1]
```

### Task: Remove duplicates
write a program to remove the duplicates in a list.
```python
numbers = [2, 2, 4, 6, 3, 4, 6, 1]
uniques = []
for number in numbers:
    if number not in uniques:
        uniques.append(number)
print(uniques)

# output-> [2, 4, 6, 3, 1]
```
### Tuples
similar to list.
we dont have append or insert method here.
we also dont have remove, clear, pop.
we have count, index
```python
numbers = (1,2,3)   # cant be modified
print(numbers[0])   # output-> 1

number[0] = 10      # output-> error message

```

### Unpacking
```python
coordinates = (1,2,3)
x = coordinates[0] 
y = coordinates[1]
z = coordinates[2]

x, y, z = coordinates
print(x)        # output-> 1
print(y)        # output-> 2
print(z)        # output-> 3

```
### Dictionaries

```python
customer = {
    "name": "sumit kr",
    "age": 30,
    "is_verified": True
}
print(customer["name"])     # output-> sumit kr

customer["name"] = "Sumit"
print(customer["name"])     # output-> Sumit

customer["birthdate"] = jan 1 2002
print(customer["birthdate"])   # output-> jan 1 2002

```

### Task: Digits to word
translate digits to words
```python
phone = input("Phone: ")
digits_mapping = {
    "1": "One",
    "2": "Two",
    "3": "Three",
    "4": "Four",
    "5": "Five",
    "6": "Six",
    "7": "Seven",
    "8": "Eight",
    "9": "Nine",
    "0": "Zero"
}

output = ""
for ch in phone:
    output += digits_mapping.get(ch, "!") + " "
print(output)
```
{{< admonition type=warning title="output" open=false >}}
    >Phone: 123456
     One Two Three Four Five Six 
{{< /admonition >}} 

### Emoji Converter :)
```python
message = input(">")
words = message.split(' ')

emojis = {
    ":)": " "
    ":(": " "
}

```

***To be continued.....***
