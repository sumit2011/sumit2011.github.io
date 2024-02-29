# Python Basic Syntax

***Python is used in automation of taskes.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

# Introduction
***Python*** is a beginner-friendly, interpreted programming language known for its readability and versatility. With a vast standard library and cross-platform compatibility, it's widely used in ***web development***, ***data science***, and ***automation***.

### print function
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


### datatype
```python
price = 10          # integer
rating = 4.9        # floating
name = 'sumit'      # string
is_present = False  # boolean
print(price)
```

### input function
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


### string and character

#formatted string 
```python
first ='sumit'
last = 'kr'
message = first +'[' + last + '] is a coder.'
msg = f'{first} [{last}] is a coder'  # <---formated give same output as message
print(message)
```
{{< admonition type=warning title="output" open=false >}}
    sumit [kr] is a coder.
{{< /admonition >}}

### length of a string
```python
string = 'you are awesome.'
print(len(string)) #general purpose function

# output->  16
```


### converting lower case to uppercase
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



### replacing a word in a string
```python
statement = 'hii this is sumit.'
print(statement.replace('sumit','sumit kr'))
# output-> hii this is sumit kr.
print(statement.replace('su','a'))
#output-> hii this is amit.
```

### checking if the string contain a word or not
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

### augmanted assignment operator
```python
x= 10
x = x + 3
x += 3  # <-- same as upper line which is 13
x -= 3  # output-> 7
x *= 3
x /= 3
```

### presidence order 
1. parenthesis
2. exponentiation  2**3
3. multiplication or division
4. addition or subtraction
```python
x= 10 + 3 * 2 ** 2    #output-> 22
x= (10 + 3) * 2 ** 2  #output-> 56
```

### math function 
```python
x= 2.9
print(round(x))   #output-> 3
print(abs(-2.9))  # output-> 2.9   (absolut function)

import math            # <--math module in python
print(math.ceil(2.9))  # output-> 3
print(math.floor(2.9)) # output-> 2
```

### if and else if statement
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

### comparision operator
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

### while loops
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

            

### Task: guess number
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

### Task: car game
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

for x_count in numbers:
    print('x' * x_count)

for x_count in numbers:
    output = ''
    for count in range(x_count):
        output += 'x'
    print(output)
```

### lists
```python
names = ['arjun', 'kaishar', 'saif', 'prateek', 'sumit']
print(names)       # output-> ['arjun', 'kaishar', 'saif', 'prateek', 'sumit']
print(names[2])    # output-> saif
print(names[-1])   # output-> sumit
print(names[2:])   # output-> ['saif', 'prateek', 'sumit']
print(names[2:4])  # output-> ['saif', 'prateek']

```
### task
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

***To be continued.....***
