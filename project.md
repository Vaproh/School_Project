# School Project
---
## Questions:

**A. Programming in Python**

1. To find the average and grade for given marks.
2. To find the sale price of an item with a given cost and discount (%).
3. To calculate the perimeter/circumference and area of shapes such as triangle, rectangle, square, and circle.
4. To calculate Simple and Compound interest.
5. To calculate profit-loss for given Cost and Sell Price.
6. To calculate EMI for Amount, Period, and Interest.
7. To calculate tax – GST/Income Tax.
8. To find the largest and smallest numbers in a list.
9. To find the third largest/smallest number in a list.
10. To find the sum of squares of the first 100 natural numbers.
11. To print the first ‘n’ multiples of a given number.
12. To count the number of vowels in a user-entered string.
13. To print the words starting with a particular alphabet in a user-entered string.
14. To print the number of occurrences of a given alphabet in a given string.
15. Create a dictionary to store names of states and their capitals.
16. Create a dictionary of students to store names and marks obtained in 5 subjects.
17. To print the highest and lowest values in the dictionary.

**B. Data Management: SQL Commands**

18. To create a database.
19. To create a student table with the student ID, class, section, gender, name, DOB, and marks as attributes where the student ID is the primary key.
20. To insert the details of at least 10 students in the above table.
21. To delete the details of a particular student in the above table.
22. To increase marks by 5% for those students who have Rno (Roll Number?) more than 20.
23. To display the entire content of the table.
24. To display Rno, Name, and Marks of those students who are scoring marks of more than 50.
25. To find the average of marks from the student table.
26. To find the number of students who are from section 'A'.
27. To add a new column 'email' in the above table with the appropriate data type.
28. To add the email IDs of each student in the previously created email column.
29. To display the information of all the students whose names start with 'AN' (Examples: ANAND, ANGAD, ...).
30. To display Rno, Name, DOB of those students who are born between '2005-01-01' and '2005-12-31'.
31. To display Rno, Name, DOB, Marks, Email of those male students in ascending order of their names.
32. To display Rno, Gender, Name, DOB, Marks, Email in descending order of their marks.
33. To display the unique sections available in the table.

---

## Answers:

#### A. Programming in Python

**1. Average and Grade:**
```python
num_marks = int(input("Enter the number of marks: "))
marks = []
for i in range(num_marks):
    mark = float(input(f"Enter mark {i+1}: "))
    marks.append(mark)

total_marks = sum(marks)
average = total_marks / num_marks

if average >= 90:
    grade = 'A'
elif average >= 80:
    grade = 'B'
elif average >= 70:
    grade = 'C'
elif average >= 60:
    grade = 'D'
else:
    grade = 'F'

print("Average Marks:", average)
print("Grade:", grade)
```

**2. Sale Price:**
```python
cost = float(input("Enter the cost of the item: "))
discount = float(input("Enter the discount: "))
sale = cost - (cost * discount)

print("\nThe sale price is:", sale)
```

**3. Area and Perimeter of Shapes:**
```python
import math

print("What do you want to calculate?")
print("1. Area")
print("2. Perimeter/Circumference")

calculation_choice = input("Enter your choice (1 or 2): ")

if calculation_choice == '1':  # Area calculations
    print("\nShape Menu:")
    print("1. Triangle")
    print("2. Rectangle")
    print("3. Square")
    print("4. Circle")

    shape_choice = input("Enter your shape choice (1-4): ")

    if shape_choice == '1':  # Triangle
        base = float(input("Enter the base of the triangle: "))
        height = float(input("Enter the height of the triangle: "))
        area = 0.5 * base * height
        print("Area:", area)
    elif shape_choice == '2':  # Rectangle
        length = float(input("Enter the length of the rectangle: "))
        width = float(input("Enter the width of the rectangle: "))
        area = length * width
        print("Area:", area)
    elif shape_choice == '3':  # Square
        side = float(input("Enter the side of the square: "))
        area = side * side
        print("Area:", area)
    elif shape_choice == '4':  # Circle
        radius = float(input("Enter the radius of the circle: "))
        pi = 3.14159  # Approximation
        area = pi * radius * radius
        print("Area:", area)
    else:
        print("Invalid shape choice.")

elif calculation_choice == '2':  # Perimeter/Circumference calculations
    print("\nShape Menu:")
    print("1. Triangle")
    print("2. Rectangle")
    print("3. Square")
    print("4. Circle")

    shape_choice = input("Enter your shape choice (1-4): ")

    if shape_choice == '1':  # Triangle
        print("Perimeter: Cannot calculate without all sides")  # For a general triangle
    elif shape_choice == '2':  # Rectangle
        length = float(input("Enter the length of the rectangle: "))
        width = float(input("Enter the width of the rectangle: "))
        perimeter = 2 * (length + width)
        print("Perimeter:", perimeter)
    elif shape_choice == '3':  # Square
        side = float(input("Enter the side of the square: "))
        perimeter = 4 * side
        print("Perimeter:", perimeter)
    elif shape_choice == '4':  # Circle
        radius = float(input("Enter the radius of the circle: "))
        pi = 3.14159
        circumference = 2 * pi * radius
        print("Circumference:", circumference)
    else:
        print("Invalid shape choice.")

else:
    print("Invalid calculation choice.")
```

**4. Simple and Compound Interest:**
```python
principal = float(input("Enter the principal amount: "))
rate = float(input("Enter the annual interest rate: "))
time = float(input("Enter the time (in years): "))

# Simple Interest
simple_interest = (principal * rate * time) / 100
simple_interest_amount = principal + simple_interest
print("Simple Interest Amount:", simple_interest_amount)

# Compound Interest
compound_interest_amount = principal * (1 + (rate / 100)) ** time
print("Compound Interest Amount (Annual):", compound_interest_amount)
```

**5. Profit/Loss:**
```python
cost_price = float(input("Enter cost price: "))
sell_price = float(input("Enter selling price: "))

if sell_price > cost_price:
    profit = sell_price - cost_price
    print(f"Profit: {profit}")
elif sell_price < cost_price:
    loss = cost_price - sell_price
    print(f"Loss: {loss}")
else:
    print("No profit, no loss")
```

**6. EMI Calculation:**

```python
principal = float(input("Enter principal amount: "))
rate = float(input("Enter annual interest rate (%): "))
time = float(input("Enter loan period (in years): "))

r = rate / (12 * 100)  # Monthly interest rate
n = time * 12  # Number of monthly installments

emi = (principal * r * (1 + r)**n) / ((1 + r)**n - 1)
print(f"EMI: {emi}")

```

**7. Tax Calculation (GST/Income Tax):**

```python
income = float(input("Enter income: "))
tax_type = input("Enter tax type (gst or income): ").lower()

if tax_type == "income":
    if income <= 250000:
        tax = 0
    elif income <= 500000:
        tax = (income - 250000) * 0.05
    elif income <= 1000000:
        tax = 12500 + (income - 500000) * 0.20
    else:
        tax = 112500 + (income - 1000000) * 0.30
elif tax_type == "gst":
    tax = income * 0.18  # Example 18% GST
else:
    print("Invalid tax type.")

print(f"Tax: {tax}")

```

**8. Largest and Smallest in a List:**

```python
numbers = []
num_count = int(input("Enter the amount of numbers you are inputting: "))

for i in range(num_count):
    num = float(input("Enter a number: "))
    numbers.append(num)

largest = numbers[0]
smallest = numbers[0]

for num in numbers:
    if num > largest:
        largest = num
    if num < smallest:
        smallest = num

print(f"Largest: {largest}")
print(f"Smallest: {smallest}")
```

**9. Third Largest/Smallest in a List:**

```python
numbers = []
num_count = int(input("Enter the amount of numbers you are inputting: "))

for i in range(num_count):
    num = float(input("Enter a number: "))
    numbers.append(num)

if len(numbers) < 3:
    print("List must have at least 3 elements.")
else:
    sorted_numbers = sorted(numbers)  # Sort the list
    third_largest = sorted_numbers[-3]
    third_smallest = sorted_numbers[2]

    print(f"Third largest: {third_largest}")
    print(f"Third smallest: {third_smallest}")

```

**10. Sum of Squares of First 100 Natural Numbers:**

```python
n = 100
sum_of_squares = sum(i**2 for i in range(1, n + 1))
print(f"Sum of squares: {sum_of_squares}")

```

**11. First 'n' Multiples:**

```python
num = int(input("Enter a number: "))
n = int(input("Enter how many multiples to print: "))

for i in range(1, n + 1):
    print(f"{num} x {i} = {num * i}")

```

**12. Count Vowels:**

```python
string = input("Enter a string: ").lower()
vowel_count = 0
vowels = "aeiou"

for char in string:
    if char in vowels:
        vowel_count += 1

print(f"Number of vowels: {vowel_count}")

```

**13. Words Starting with a Letter:**

```python
string = input("Enter a string: ")
letter = input("Enter a letter: ").lower()

words = string.split()
for word in words:
    if word.lower().startswith(letter):
        print(word)

```

**14. Occurrences of a Letter:**

```python
string = input("Enter a string: ")
letter = input("Enter a letter: ").lower()

count = 0
for char in string:
    if char.lower() == letter:
        count += 1

print(f"Number of occurrences of '{letter}': {count}")

```

**15. States and Capitals Dictionary:**

```python
states_capitals = {
    "Andhra Pradesh": "Hyderabad",
    "Arunachal Pradesh": "Itanagar",
    "Assam": "Dispur",
    "Bihar": "Patna",
    "Chhattisgarh": "Raipur",
    "Goa": "Panaji",
    "Gujarat": "Gandhinagar",
    "Haryana": "Chandigarh",
    "Himachal Pradesh": "Shimla",
    "Jharkhand": "Ranchi",
    "Karnataka": "Bengaluru",
    "Kerala": "Thiruvananthapuram",
    "Madhya Pradesh": "Bhopal",
    "Maharashtra": "Mumbai",
    "Manipur": "Imphal",
    "Meghalaya": "Shillong",
    "Mizoram": "Aizawl",
    "Nagaland": "Kohima",
    "Odisha": "Bhubaneswar",
    "Punjab": "Chandigarh",
    "Rajasthan": "Jaipur",
    "Sikkim": "Gangtok",
    "Tamil Nadu": "Chennai",
    "Telangana": "Hyderabad",
    "Tripura": "Agartala",
    "Uttar Pradesh": "Lucknow",
    "Uttarakhand": "Dehradun",
    "West Bengal": "Kolkata"
}

print(states_capitals)
```

**16. Students and Marks Dictionary:**

```python
students_marks = {
    "Alice": [85, 92, 78, 90, 88],
    "Bob": [76, 80, 92, 85, 79],
    "Charlie": [90, 85, 88, 95, 92],
    "David": [70, 75, 80, 85, 90],
    "Eve": [95, 90, 85, 80, 75]
}

print(students_marks)
```

**17. Highest/Lowest Values in Dictionary:**

```python
students_marks_choice = input("Do you want to input student marks (yes/no)? ").lower()

if students_marks_choice == "yes":
    students_marks = {}
    num_students = int(input("Enter the number of students: "))
    for _ in range(num_students):
        student_name = input("Enter student name: ")
        marks_str = input("Enter marks for 5 subjects (separated by commas): ")
        marks = [int(mark) for mark in marks_str.split(",")]  # Convert to integers
        students_marks[student_name] = marks
elif students_marks_choice == "no":
    students_marks = {
        "Alice": [85, 92, 78, 90, 88],
        "Bob": [76, 80, 92, 85, 79],
        "Charlie": [90, 85, 88, 95, 92],
        "David": [70, 75, 80, 85, 90],
        "Eve": [95, 90, 85, 80, 75]
    }
    print("Using example student marks data:\n", students_marks) # Print example data first
else:
    print("Invalid choice. Using example data.")
    students_marks = {
        "Alice": [85, 92, 78, 90, 88],
        "Bob": [76, 80, 92, 85, 79],
        "Charlie": [90, 85, 88, 95, 92],
        "David": [70, 75, 80, 85, 90],
        "Eve": [95, 90, 85, 80, 75]
    }
    print("Using example student marks data:\n", students_marks) # Print example data first


# highest and lowest marks
highest_marks = max(max(marks) for marks in students_marks.values())
lowest_marks = min(min(marks) for marks in students_marks.values())

print(f"Highest Marks: {highest_marks}")
print(f"Lowest Marks: {lowest_marks}")


for student, marks in students_marks.items():
    average_marks = sum(marks) / len(marks)
    print(f"Average marks for {student}: {average_marks:.2f}")
```

#### B. SQL Commands

**18. Create a database:**

```sql
CREATE DATABASE student_database;
```

**19. Create a student table:**

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    class VARCHAR(50),
    section CHAR(1),
    gender CHAR(1),
    name VARCHAR(255),
    DOB DATE,
    marks INT
);
```

**20. Insert student details (10+ students):**

```sql
INSERT INTO students (student_id, class, section, gender, name, DOB, marks) VALUES
(1, '10A', 'A', 'M', 'Anand', '2005-03-15', 85),
(2, '10A', 'B', 'F', 'Priya', '2005-06-20', 92),
(3, '10B', 'A', 'M', 'Rahul', '2005-09-10', 78),
(4, '10B', 'B', 'F', 'Sneha', '2006-01-25', 88),
(5, '11A', 'A', 'M', 'Vikram', '2004-04-05', 95),
(6, '11A', 'B', 'F', 'Neha', '2004-07-18', 82),
(7, '11B', 'A', 'M', 'Siddharth', '2004-10-02', 75),
(8, '11B', 'B', 'F', 'Anjali', '2005-02-12', 90),
(9, '12A', 'A', 'M', 'Aryan', '2003-05-28', 80),
(10, '12A', 'B', 'F', 'Diya', '2003-08-09', 87),
(11, '12B', 'A', 'M', 'Karan', '2003-11-15', 72);
```

**21. Delete a student:**

```sql
DELETE FROM students WHERE student_id = 5; -- Example: Delete student with ID 5
```

**22. Increase marks by 5% for Rno > 20:**

```sql
UPDATE students SET marks = marks * 1.05 WHERE student_id > 20; -- Assuming Rno is student_id
```

**23. Display entire table:**

```sql
SELECT * FROM students;
```

**24. Display Rno, Name, Marks for marks > 50:**

```sql
SELECT student_id, name, marks FROM students WHERE marks > 50;
```

**25. Average marks:**

```sql
SELECT AVG(marks) FROM students;
```

**26. Number of students in section 'A':**

```sql
SELECT COUNT(*) FROM students WHERE section = 'A';
```

**27. Add email column:**

```sql
ALTER TABLE students ADD COLUMN email VARCHAR(255);
```

**28. Add email IDs (example):**

```sql
UPDATE students SET email = 'anand@example.com' WHERE student_id = 1;
UPDATE students SET email = 'priya@example.com' WHERE student_id = 2;
-- ... and so on
```

**29. Students whose names start with 'AN':**

```sql
SELECT * FROM students WHERE name LIKE 'AN%';
```

**30. Students born between '2005-01-01' and '2005-12-31':**

```sql
SELECT student_id, name, DOB FROM students WHERE DOB BETWEEN '2005-01-01' AND '2005-12-31';
```

**31. Male students in ascending order of names:**

```sql
SELECT student_id, name, DOB, marks, email FROM students 
WHERE gender = 'M' ORDER BY name ASC;
```

**32. Students in descending order of marks:**

```sql
SELECT student_id, gender, name, DOB, marks, email FROM students ORDER BY marks DESC;
```

**33. Unique sections:**

```sql
SELECT DISTINCT section FROM students;
```
