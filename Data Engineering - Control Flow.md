# IF Statements


```python
#IF statement to check string user name 
user_name = "angela_catlady_87"

if user_name == "Dave":
  print("Get off my computer Dave!")
if user_name == "angela_catlady_87":
  print("I know it is you, Dave! Go away!")

```

    I know it is you, Dave! Go away!



```python
#Checking numeric values
x=20
y=20
if x == y:
    print("These numbers are the same")
```


```python
#CHeacking multiple conditions 
tatement_one = False

statement_two = True

credits = 120
gpa = 3.4

if gpa >= 2.0 and credits >= 120:
  print("You meet the requirements to graduate!")
```

    You meet the requirements to graduate!



```python
credits = 118
gpa = 2.0

if credits >= 120 or gpa >= 2.0:
  print("You have met at least one of the requirements.")
```

    You have met at least one of the requirements.



```python
credits = 120
gpa = 1.8

if not credits >= 120:
  print("You do not have enough credits to graduate.")

if not gpa >= 2.0:
  print("Your GPA is not high enough to graduate.")

if not (credits >= 120) and not (gpa >= 2.0):
  print("You do not meet either requirement to graduate!")

```

    Your GPA is not high enough to graduate.



```python
credits = 120
gpa = 1.9

if (credits >= 120) and (gpa >= 2.0):
  print("You meet the requirements to graduate!")
else:
  print("You do not meet the requirements to graduate.")

```

    You do not meet the requirements to graduate.



```python
grade = 86

if grade >= 90:
  print("A")
elif grade >= 80:
  print("B")
elif grade >= 70:
  print("C")
elif grade >= 60:
  print("D")
else:
  print("F")
```

    B


# Magic 8 Ball


```python
import random

name = "Tyler"
question = "Will become a data engineer?"
answer = ""

random_number = random.randint(1, 9)
# print(random_number)

if random_number == 1:
  answer = "Yes - definitely"
elif random_number == 2:
  answer = "It is decidedly so"
elif random_number == 3:
  answer = "Without a doubt"
elif random_number == 4:
  answer = "Reply hazy, try again"
elif random_number == 5:
  answer = "Ask again later"
elif random_number == 6:
  answer = "Better not tell you now"
elif random_number == 7:
  answer = "My sources say no"
elif random_number == 8:
  answer = "Outlook not so good"
elif random_number == 9:
  answer = "Very doubtful"
else:
  answer = "Error"
  
print(name + " asks: " + question)
print("Magic 8 Ball's answer: " + answer)
```

    Tyler asks: Will become a data engineer?
    Magic 8 Ball's answer: It is decidedly so


# Sals Shipping


```python
weight = 90

# Ground Shipping 

if weight <= 2:
  cost_ground = weight * 1.5 + 20
elif weight <= 6:
  cost_ground = weight * 3.00 + 20
elif weight <= 10:
  cost_ground = weight * 4.00 + 20
else:
  cost_ground = weight * 4.75 + 20

print("Ground Shipping $", cost_ground)
      
# Ground Shipping Premimum 

cost_ground_premium = 125.00

print("Ground Shipping Premimium $", cost_ground_premium)

# Drone Shipping 

if weight <= 2:
  cost_drone = weight * 4.5
elif weight <= 6:
  cost_drone = weight * 9.00
elif weight <= 10:
  cost_drone = weight * 12.00
else:
  cost_drone = weight * 14.25

print("Drone Shipping: $", cost_drone)
```

    Ground Shipping $ 447.5
    Ground Shipping Premimium $ 125.0
    Drone Shipping: $ 1282.5


# Errors

- SyntaxError: Error caused by not following the proper structure (syntax) of the language.
- NameError: Errors reported when the interpreter detects a variable that is unknown.
- TypeError: Errors thrown when an operation is applied to an object of an inappropriate type.

# Data Structures

# What is a List?



```python
heights = [61, 70, 67, 64, 65]

broken_heights = [65, 71, 59, 62]
```


```python
ints_and_strings = [1, 2, 3, "four", "five", "Six"]

sam_height_and_testscore = ["Sam", 67, 85.5, True]
```


```python
example_list = ["Sam", 67, 85.5, True]
#Using Append
example_list.append(5)
print(example_list)
```

    ['Sam', 67, 85.5, True, 5]



```python
#Using Remove
example_list.remove(5)
print(example_list)

```

    ['Sam', 67, 85.5, True]



```python
orders = ["daisy", "buttercup", "snapdragon", "gardenia", "lily"]

# Create new orders here:
new_orders = ["lilac", "iris"]

orders_combined = orders + new_orders

broken_prices = [5, 3, 4, 5, 4] + [4]
print(broken_prices)
print(orders_combined)
```

    [5, 3, 4, 5, 4, 4]
    ['daisy', 'buttercup', 'snapdragon', 'gardenia', 'lily', 'lilac', 'iris']



```python
employees = ["Michael", "Dwight", "Jim", "Pam", "Ryan", "Andy", "Robert"]

employee_four = employees[3]
print(employees[4])
```

    Ryan



```python
shopping_list = ["eggs", "butter", "milk", "cucumbers", "juice", "cereal"]

last_element = shopping_list[-1]

index5_element = shopping_list[5]

print(last_element)
print(index5_element)
```

    cereal
    cereal



```python
 # Checkpoint 1
order_list = ["Celery", "Orange Juice", "Orange", "Flatbread"]
print(order_list)

# Checkpoint 2
order_list.remove("Flatbread")
print(order_list)

# Checkpoint 3
new_store_order_list = ["Orange", "Apple", "Mango", "Broccoli", "Mango"]
print(new_store_order_list)

# Checkpoint 4
new_store_order_list.remove("Mango")
print(new_store_order_list)

```

    ['Celery', 'Orange Juice', 'Orange', 'Flatbread']
    ['Celery', 'Orange Juice', 'Orange']
    ['Orange', 'Apple', 'Mango', 'Broccoli', 'Mango']
    ['Orange', 'Apple', 'Broccoli', 'Mango']



```python
#2d lists
heights = [["Jenny", 61], ["Alexus", 70], ["Sam", 67], ["Grace", 64], ["Vik", 68]]

ages = [["Aaron", 15], ["Dhruti", 16]]
ages
```




    [['Aaron', 15], ['Dhruti', 16]]




```python
#Checkpoint 1
class_name_test = [["Jenny", 90], ["Alexus", 85.5], ["Sam", 83], ["Ellie", 101.5]]
print(class_name_test)

#Checkpoint 2
sams_score = class_name_test[2][1]
print(sams_score)

#Checkpoint 3
ellies_score = class_name_test[-1][-1]
print(ellies_score)
```

    [['Jenny', 90], ['Alexus', 85.5], ['Sam', 83], ['Ellie', 101.5]]
    83
    101.5


# Working with Lists

![Image%201-16-23%20at%201.29%20PM.jpg](attachment:Image%201-16-23%20at%201.29%20PM.jpg)


```python
front_display_list = ["Mango", "Filet Mignon", "Chocolate Milk"]
print(front_display_list)

# Your code below: 

# Checkpoint 2
front_display_list.insert(0, "Pineapple")
print(front_display_list)
```

    ['Mango', 'Filet Mignon', 'Chocolate Milk']
    ['Pineapple', 'Mango', 'Filet Mignon', 'Chocolate Milk']



```python
data_science_topics = ["Machine Learning", "SQL", "Pandas", "Algorithms", "Statistics", "Python 3"]
print(data_science_topics)

# Your code below: 

# Checkpoint 2
data_science_topics.pop()
print(data_science_topics)

# Checkpoint 3
data_science_topics.pop(3)
print(data_science_topics)
```

    ['Machine Learning', 'SQL', 'Pandas', 'Algorithms', 'Statistics', 'Python 3']
    ['Machine Learning', 'SQL', 'Pandas', 'Algorithms', 'Statistics']
    ['Machine Learning', 'SQL', 'Pandas', 'Statistics']



```python
# Checkpoint 1
number_list = range(9)
print(list(number_list))

# Checkpoint 2
zero_to_seven = range(8)
print(list(zero_to_seven))
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8]
    [0, 1, 2, 3, 4, 5, 6, 7]



```python
#Slicing
suitcase = ["shirt", "shirt", "pants", "pants", "pajamas", "books"]

beginning = suitcase[0:4]

# Your code below: 
print(beginning)

# Checkpoint 2 
beginning = suitcase[0:2]

# Checkpoint 3
middle = suitcase[2:4]
print(middle)
```

    ['shirt', 'shirt', 'pants', 'pants']
    ['pants', 'pants']



```python
suitcase = ["shirt", "shirt", "pants", "pants", "pajamas", "books"]

# Your code below: 

# Checkpoint 1
last_two_elements = suitcase[-2:]
print(last_two_elements)

# Checkpoint 2
slice_off_last_three = suitcase[:-3]
print(slice_off_last_three)
```

    ['pajamas', 'books']
    ['shirt', 'shirt', 'pants']



```python
votes = ["Jake", "Jake", "Laurie", "Laurie", "Laurie", "Jake", "Jake", "Jake", "Laurie", "Cassie", "Cassie", "Jake", "Jake", "Cassie", "Laurie", "Cassie", "Jake", "Jake", "Cassie", "Laurie"]

# Checkpoint 1
jake_votes = votes.count("Jake")

# Checkpoint 2
print(jake_votes)
```

    9



```python
addresses = ["221 B Baker St.", "42 Wallaby Way", "12 Grimmauld Place", "742 Evergreen Terrace", "1600 Pennsylvania Ave", "10 Downing St."]
addresses.sort()
print(addresses)


# Checkpoint 3
names = ["Ron", "Hermione", "Harry", "Albus", "Sirius"]
names.sort()


# Checkpoint 4 & 5
cities = ["London", "Paris", "Rome", "Los Angeles", "New York"]
sorted_cities = cities.sort(reverse=True)
print(sorted_cities)
print(cities)
```

    ['10 Downing St.', '12 Grimmauld Place', '1600 Pennsylvania Ave', '221 B Baker St.', '42 Wallaby Way', '742 Evergreen Terrace']
    None
    ['Rome', 'Paris', 'New York', 'Los Angeles', 'London']



```python
games = ["Portal", "Minecraft", "Pacman", "Tetris", "The Sims", "Pokemon"]

# Your code below:
# Checkpoint 1
games_sorted = sorted(games)

# Checkpoint 2
print(games)
print(games_sorted)
```

    ['Portal', 'Minecraft', 'Pacman', 'Tetris', 'The Sims', 'Pokemon']
    ['Minecraft', 'Pacman', 'Pokemon', 'Portal', 'Tetris', 'The Sims']



```python
#Zip
names = ["Jenny", "Alexus", "Sam", "Grace"]
heights = [61, 70, 67, 64]
names_and_heights = zip(names, heights)
print(names_and_heights)
converted_list = list(names_and_heights)
print(converted_list)
```

    <zip object at 0x7ff5085f91c0>


# For Loops
for <temporary variable> in <collection>:
  <action>

```python
board_games = ["Settlers of Catan", "Carcassone", "Power Grid", "Agricola", "Scrabble"]

sport_games = ["football", "hockey", "baseball", "cricket"]

for game in board_games:
  print(game)
```

    Settlers of Catan
    Carcassone
    Power Grid
    Agricola
    Scrabble



```python
promise = "My name is Tyler"

for temp in range(5): 
  print(promise)
```

    My name is Tyler
    My name is Tyler
    My name is Tyler
    My name is Tyler
    My name is Tyler


# While Loops
while <conditional statement>:
  <action>

```python
# Your code below: 
countdown = 10
while countdown >= 0: 
  print(countdown)
  countdown -= 1
print("We have liftoff!")
```


```python
ingredients = ["milk", "sugar", "vanilla extract", "dough", "chocolate"]
length = len(ingredients)
index = 0
 
while index < length:
    print(ingredients[index])
    index -= 1
```

    milk
    chocolate
    dough
    vanilla extract
    sugar
    milk



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    Input In [5], in <cell line: 5>()
          3 index = 0
          5 while index < length:
    ----> 6     print(ingredients[index])
          7     index -= 1


    IndexError: list index out of range



```python
python_topics = ["variables", "control flow", "loops", "modules", "classes"]

length = len(python_topics)
index = 0

while index < length:
  print("I am learning about " + python_topics[index])
  index += 1
```

    I am learning about variables
    I am learning about control flow
    I am learning about loops
    I am learning about modules
    I am learning about classes



```python
dog_breeds_available_for_adoption = ["french_bulldog", "dalmatian", "shihtzu", "poodle", "collie"]
dog_breed_I_want = "dalmatian"

for dog_breed in dog_breeds_available_for_adoption:
    print(dog_breed)
    if dog_breed == dog_breed_I_want:
        print("They have the dog I want!")
        break

```

    french_bulldog
    dalmatian
    They have the dog I want!



```python
ages = [12, 38, 34, 26, 21, 19, 67, 41, 17]

for i in ages:
    if i >= 21:
    print(i)
```

    38
    34
    26
    21
    67
    41



```python
sales_data = [[12, 17, 22], [2, 10, 3], [5, 12, 13]]
scoops_sold = 0 
for location in sales_data:
    print(location)
    for element in location:
        scoops_sold += element 
print(scoops_sold)
```

    [12, 17, 22]
    [2, 10, 3]
    [5, 12, 13]
    96



```python
numbers = [2, -1, 79, 33, -45]
doubled = [num * 2 for num in numbers]
print(doubled)
```

    [4, -2, 158, 66, -90]


# List Comprehensions: Introduction



```python
numbers = [2, -1, 79, 33, -45]
doubled = []
 
for number in numbers:
    doubled.append(number * 2)
 
print(doubled)
```

    [4, -2, 158, 66, -90]



```python
numbers = [2, -1, 79, 33, -45]
doubled = [num * 2 for num in numbers]
print(doubled)
```

    [4, -2, 158, 66, -90]



```python
heights = [161, 164, 156, 144, 158, 170, 163, 163, 157]
can_ride_coaster = []
can_ride_coaster = [height for height in heights if height > 161]

print(can_ride_coaster)
```

    [164, 170, 163, 163]


# Modules


```python
import random
# Create random_list below:
random_list = [random.randint(1,100) for i in range(101)]

# Create randomer_number below:
randomer_number = random.choice(random_list)

# Print randomer_number below:
print(randomer_number)
```

    71


# Functions 


```python
# Your code below: 
def directions_to_timesSq():
  print("Walk 4 mins to 34th St Herald Square train station")
  print("Take the Northbound N, Q, R, or W train 1 stop")
  print("Get off the Times Square 42nd Street stop")

print(directions_to_timesSq())
```


```python
def calculate_expenses(plane_ticket_price, car_rental_rate, hotel_rate , trip_time):
  car_rental_total = car_rental_rate * trip_time
  hotel_total = hotel_rate * trip_time - 10
  print(car_rental_total + hotel_total + plane_ticket_price)

calculate_expenses(345, 100, 100, 5)
```

    1335



```python
current_budget = 3500.75

def print_remaining_budget(budget):
  print("Your remaining budget is: $" + str(budget))

print_remaining_budget(current_budget)

# Write your code below: 
def deduct_expense(budget, expense):
  return budget - expense

shirt_expense = 9

new_budget_after_shirt = deduct_expense( current_budget, shirt_expense )

print_remaining_budget(new_budget_after_shirt)
```

    Your remaining budget is: $3500.75
    Your remaining budget is: $3491.75



```python
def top_tourist_locations_italy():
  first = "Rome"
  second = "Venice"
  third = "Florence"
  return first, second, third 
  
most_popular1, most_popular2, most_popular3 = top_tourist_locations_italy()

print(most_popular1)
print(most_popular2)
print(most_popular3)
```

    Rome
    Venice
    Florence


# Classes - Object Oriented Programming


```python
print(type(5))

my_dict = {}
print(type(my_dict))

my_list = []
print(type(my_list))
```

    <class 'int'>
    <class 'dict'>
    <class 'list'>



```python
class Rules:
    def washing_brushes(self):
        return "Point bristles towards the basin while washing your brushes."

print(Rules())
type(Rules())
```

    <__main__.Rules object at 0x7fd538131bb0>





    __main__.Rules




```python
class Circle:
  pi = 3.14
  
  def area(self, radius):
    return Circle.pi * radius ** 2
  
circle = Circle()
pizza_area = circle.area(12 / 2)
teaching_table_area = circle.area(36 / 2)
round_room_area = circle.area(11460 / 2)

```




    __main__.Circle




```python
class Shouter:
    def __init__(self):
        print("HELLO?!")
 
shout1 = Shouter()
# prints "HELLO?!"
 
shout2 = Shouter()
# prints "HELLO?!"
```

    HELLO?!
    HELLO?!



```python
can_we_count_it = [{'s': False}, "sassafrass", 18, ["a", "c", "s", "d", "s"]]

for element in can_we_count_it:
  if hasattr(element, "count"):
    print(str(type(element)) + " has the count attribute!")
  else:
    print(str(type(element)) + " does not have the count attribute :(")
```

    <class 'dict'> does not have the count attribute :(
    <class 'str'> has the count attribute!
    <class 'int'> does not have the count attribute :(
    <class 'list'> has the count attribute!



```python
class Circle:
  pi = 3.14
  def __init__(self, diameter):
    print("Creating circle with diameter {d}".format(d=diameter))
    # Add assignment for self.radius here:
    
    self.radius = diameter / 2
    
  def circumference(self):
    return 2 * self.pi * self.radius
  
medium_pizza = Circle(12)
teaching_table = Circle(36)
round_room = Circle(11460)

print(medium_pizza.circumference())
print(teaching_table.circumference())
print(round_room.circumference())
```

    Creating circle with diameter 12
    Creating circle with diameter 36
    Creating circle with diameter 11460
    37.68
    113.04
    35984.4


# Dictionaries


```python
translations = {"mountain": "orod", "bread": "bass", "friend": "mellon", "horse": "roch"}
translations
```




    {'mountain': 'orod', 'bread': 'bass', 'friend': 'mellon', 'horse': 'roch'}




```python
animals_in_zoo = {}
animals_in_zoo['zebras'] = 8
animals_in_zoo['monkeys'] = 12
animals_in_zoo['dinosaurs'] = 0
print(animals_in_zoo)
```

    {'zebras': 8, 'monkeys': 12, 'dinosaurs': 0}



```python
#Using update to add to a dictionary
user_ids = {"teraCoder": 9018293, "proProgrammer": 119238}
user_ids.update({"theLooper": 138475, "stringQueen": 85739})
print(user_ids)
```

    {'teraCoder': 9018293, 'proProgrammer': 119238, 'theLooper': 138475, 'stringQueen': 85739}



```python
oscar_winners = {"Best Picture": "La La Land", "Best Actor": "Casey Affleck", "Best Actress": "Emma Stone", "Animated Feature": "Zootopia"}

oscar_winners["Supporting Actress"] = "Viola Davis"
oscar_winners["Best Picture"] = "Moonlight"
print(oscar_winners)
```

    {'Best Picture': 'Moonlight', 'Best Actor': 'Casey Affleck', 'Best Actress': 'Emma Stone', 'Animated Feature': 'Zootopia', 'Supporting Actress': 'Viola Davis'}



```python
drinks = ["espresso", "chai", "decaf", "drip"]
caffeine = [64, 40, 0, 120]
zipped_drinks = zip(drinks, caffeine)
drinks_to_caffeine = {key: value for key, value in zipped_drinks}
drinks_to_caffeine
```




    {'espresso': 64, 'chai': 40, 'decaf': 0, 'drip': 120}




```python
user_ids = {"teraCoder": 100019, "pythonGuy": 182921, "samTheJavaMaam": 123112, "lyleLoop": 102931, "keysmithKeith": 129384}

tc_id = user_ids.get("teraCoder", 100000)
stack_id = user_ids.get("superStackSmash", 100000)

print(tc_id)
print(stack_id)
```

    100019
    100000



```python
available_items = {"health potion": 10, "cake of the cure": 5, "green elixir": 20, "strength sandwich": 25, "stamina grains": 15, "power stew": 30}
health_points = 20

health_points += available_items.pop("stamina grains", 0)
health_points += available_items.pop("power stew", 0)
health_points += available_items.pop("mystic bread", 0)

print(available_items)
print(health_points)
```

    {'health potion': 10, 'cake of the cure': 5, 'green elixir': 20, 'strength sandwich': 25}
    65



```python
available_items.keys()
```




    dict_keys(['health potion', 'cake of the cure', 'green elixir', 'strength sandwich'])




```python
for score_list in available_items.values():
    print(score_list)
```

    10
    5
    20
    25



```python
pct_women_in_occupation.items()
```




    dict_items([('CEO', 28), ('Engineering Manager', 9), ('Pharmacist', 58), ('Physician', 40), ('Lawyer', 37), ('Aerospace Engineer', 9)])




```python
pct_women_in_occupation = {"CEO": 28, "Engineering Manager": 9, "Pharmacist": 58, "Physician": 40, "Lawyer": 37, "Aerospace Engineer": 9}

for occupation, percentage in pct_women_in_occupation.items():
    print("Women make up " + str(percentage) + " percent of " + occupation + "s.") 
```

    Women make up 28 percent of CEOs.
    Women make up 9 percent of Engineering Managers.
    Women make up 58 percent of Pharmacists.
    Women make up 40 percent of Physicians.
    Women make up 37 percent of Lawyers.
    Women make up 9 percent of Aerospace Engineers.



```python
print("CEO" in pct_women_in_occupation)
```

    True


# Strings


```python
my_name = "Python Person"
my_name[0]
```




    'P'




```python
first_name = "Rodrigo"
last_name = "Villanueva"

print(last_name[:5])
print(last_name[2:6])
```

    Villa
    llan



```python
first_name = "Julie"
last_name = "Blevins"

def account_generator(first_name, last_name):
    account_name = first_name[:3] + last_name[:3]
    return account_name

new_account = account_generator(first_name, last_name)

print(new_account)
```

    JulBle



```python
first_name = "Reiko"
last_name = "Matsuki"

def password_generator(first_name, last_name):
    temp_password = first_name[len(first_name)-3:] + last_name[len(last_name)-3:]
    return temp_password

temp_password = password_generator(first_name, last_name)
print(temp_password)
```

    ikouki



```python
first_name[-4:]
```




    'eiko'




```python
first_name[3:]
```




    'ko'




```python
#Escape characters
password = "theycallme\"crazy\"91"
print(password)
```

    theycallme"crazy"91



```python
favorite_fruit = "blueberry"
counter = 0
for character in favorite_fruit:
    if character == "r":
        counter = counter + 1
print(counter)
```

    2



```python
poem_title = "spring storm"
poem_author = "William Carlos Williams"

poem_title_fixed = poem_title.title()

print(poem_title)
print(poem_title_fixed)

poem_author_fixed = poem_author.upper()

print(poem_author)
print(poem_author_fixed)
```

    spring storm
    Spring Storm
    William Carlos Williams
    WILLIAM CARLOS WILLIAMS



```python
line_one = "The sky has given over"
line_one_words = line_one.split()
print(line_one_words)
```

    ['The', 'sky', 'has', 'given', 'over']



```python
reapers_line_one_words = ["Black", "reapers", "with", "the", "sound", "of", "steel", "on", "stones"]

reapers_line_one = ' '.join(reapers_line_one_words)
print(reapers_line_one)
```

    Black reapers with the sound of steel on stones



```python
winter_trees_lines = ['All the complicated details', 'of the attiring and', 'the disattiring are completed!', 'A liquid moon', 'moves gently among', 'the long branches.', 'Thus having prepared their buds', 'against a sure winter', 'the wise trees', 'stand sleeping in the cold.']

winter_trees_full = '\n'.join(winter_trees_lines)

print(winter_trees_full)
```

    All the complicated details
    of the attiring and
    the disattiring are completed!
    A liquid moon
    moves gently among
    the long branches.
    Thus having prepared their buds
    against a sure winter
    the wise trees
    stand sleeping in the cold.



```python
god_wills_it_line_one = "The very earth will disown you"

disown_placement = god_wills_it_line_one.find("disown")
print(disown_placement)
```

    20


# Reading in Files


```python
#Reading lines of text in file
with open('how_many_lines.txt') as lines_doc:
  for line in lines_doc.readlines():
    print(line)
```


```python
import csv

with open('cool_csv.csv') as cool_csv_file:
  cool_csv_dict = csv.DictReader(cool_csv_file)
  for row in cool_csv_dict:
    print(row['Cool Fact'])
```


```python
access_log = [{'time': '08:39:37', 'limit': 844404, 'address': '1.227.124.181'}, {'time': '13:13:35', 'limit': 543871, 'address': '198.51.139.193'}, {'time': '19:40:45', 'limit': 3021, 'address': '172.1.254.208'}, {'time': '18:57:16', 'limit': 67031769, 'address': '172.58.247.219'}, {'time': '21:17:13', 'limit': 9083, 'address': '124.144.20.113'}, {'time': '23:34:17', 'limit': 65913, 'address': '203.236.149.220'}, {'time': '13:58:05', 'limit': 1541474, 'address': '192.52.206.76'}, {'time': '10:52:00', 'limit': 11465607, 'address': '104.47.149.93'}, {'time': '14:56:12', 'limit': 109, 'address': '192.31.185.7'}, {'time': '18:56:35', 'limit': 6207, 'address': '2.228.164.197'}]
fields = ['time', 'address', 'limit']

import csv

with open('logger.csv', 'w') as logger_csv:
  log_writer = csv.DictWriter(logger_csv, fieldnames=fields)
  log_writer.writeheader()
  for line in access_log:
    log_writer.writerow(line)

```


```python
with open('message.json') as message_json:
  message = json.load(message_json)
  print(message['text'])
```


```python
data_payload = [
  {'interesting message': 'What is JSON? A web application\'s little pile of secrets.',
   'follow up': 'But enough talk!'}
]

import json

with open('data.json', 'w') as data_json:
  json.dump(data_payload, data_json)
```


```python
data_json
```




    <_io.TextIOWrapper name='data.json' mode='w' encoding='UTF-8'>




```python

```
