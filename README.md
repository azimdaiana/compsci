# compsci
import math
import statistics as stat
import numpy as np
from matplotlib import pyplot as plt

# Basic Operations
def addition(x, y):
    print(x + y)
    return x + y

def subtraction(x, y):
    print(x - y)
    return x - y

def multiplication(x, y):
    print(x * y)
    return x * y

def division(x, y):
    print(x / y)
    return x / y

# Extended Operations
def square_root(x):
    print(x ** (1/2))
    return x ** (1/2)

def square(x):
    print(x ** 2)
    return x ** 2

def power(x, y):
    print(x ** y)
    return x ** y

def sinr(x):
    print(math.sin(x))
    return math.sin(x)

def sind(x):
    print(math.sin(math.radians(x)))
    return math.sin(math.radians(x))

def cosr(x):
    print(math.cos(x))
    return math.cos(x)

def cosd(x):
    print(math.cos(math.radians(x)))
    return math.cos(math.radians(x))

def tanr(x):
    print(math.tan(x))
    return math.tan(x)

def tand(x):
    print(math.tan(math.radians(x)))
    return math.tan(math.radians(x))

def asinr(x):
    print(math.asin(x))
    return math.asin(x)

def asind(x):
    print(math.asin(math.radians(x)))
    return math.asin(math.radians(x))

def acosr(x):
    print(math.acos(x))
    return math.acos(x)

def acosd(x):
    print(math.acos(math.radians(x)))
    return math.acos(math.radians(x))

def atanr(x):
    print(math.atan(x))
    return math.atan(x)

def atand(x):
    print(math.atan(math.radians(x)))
    return math.atan(math.radians(x))

def mean(x):
    print(stat.mean(x))
    return stat.mean(x)

def mode(x):
    print(stat.mode(x))
    return stat.mode(x)

def median(x):
    print(stat.median(x))
    return stat.median(x)

def sum_list(x):
    print(sum(x))
    return sum(x)

def fq(x):
    print(np.quantile(x, .25))
    return np.quantile(x, .25)
    
def tq(x):
    print(np.quantile(x, .75))
    return np.quantile(x, .75)
    
def iqr(x):
    print(np.quantile(x, .75) - np.quantile(x, .25))
    return np.quantile(x, .75) - np.quantile(x, .25)

def stdev(x):
    print(np.std(x))
    return np.std(x)
    
def pltpoints(pair1, pair2):
    table = np.array([pai1, pair2])
    plt.plot

# Menu function
def menu():
    print("--- My Enhanced Calculator ---")
    options = [
        "1. Addition", "2. Subtraction", "3. Multiplication", "4. Division",
        "5. Square Root", "6. Square", "7. Power", "8. Sin (Radians)",
        "9. Sin (Degrees)", "10. Cosine (Radians)", "11. Cosine (Degrees)",
        "12. Tan (Radians)", "13. Tan (Degrees)", "14. Arcsin (Radians)",
        "15. Arcsin (Degrees)", "16. Arccos (Radians)", "17. Arccos (Degrees)",
        "18. Arctan (Radians)", "19. Arctan (Degrees)", "20. Mean",
        "21. Mode", "22. Median", "23. Sum", "24. First Quantile", "25. Third Quantile", "26. Interquantile Range", "27. Standard Deviation",
        "28. Plot a line between two points", "29. Plot line in form y = x + b", "30. Plot Linear Equation", "31. Exit"
    ]
    for option in options:
        print(option)
    choice = input("Enter menu selection: ")
    while not choice.isdigit() or int(choice) < 1 or int(choice) > 31:
        print("Please enter a valid menu choice!")
        choice = input("Enter menu selection: ")
    return int(choice)

# Main loop
choice = menu()
while choice != 31:
    if choice <= 7:  # For operations requiring two inputs
        x = float(input("Input a number: "))
        y = float(input("Input another number: ")) if choice != 5 and choice != 6 else None
    elif choice in [20, 21, 22, 23, 24, 25, 26, 27]:  # List operations
            x = list(map(float, input("Enter a list of numbers separated by space: ").split()))
    else: 
        pair1 = np.array([float(input("Input the x of your first coordinate: ")), float(input("Input the y of your first coordinate: "))]) 
        x2 = float(input("Input the x of your second coordinate: ")) 
        y2 = float(input("Input the y of your second coordinate: ")) 
        pair2 = np.array([x2, y2]) 
    
    # Process the choice
    if choice == 1:
        addition(x, y)
    elif choice == 2:
        subtraction(x, y)
    elif choice == 3:
        multiplication(x, y)
    elif choice == 4:
        division(x, y)
    elif choice == 5:
        square_root(x)
    elif choice == 6:
        square(x)
    elif choice == 7:
        power(x, y)
    elif choice == 8:
        sinr(x)
    elif choice == 9:
        sind(x)
    elif choice == 10:
        cosr(x)
    elif choice == 11:
        cosd(x)
    elif choice == 12:
        tanr(x)
    elif choice == 13:
        tand(x)
    elif choice == 14:
        asinr(x)
    elif choice == 15:
        asind(x)
    elif choice == 16:
        acosr(x)
    elif choice == 17:
        acosd(x)
    elif choice == 18:
        atanr(x)
    elif choice == 19:
        atand(x)
    elif choice == 20:
        mean(x)
    elif choice == 21:
        mode(x)
    elif choice == 22:
        median(x)
    elif choice == 23:
        sum_list(x)
    elif choice == 24:
        fq(x)
    elif choice == 25:
        tq(x)
    elif choice == 26:
        iqr(x)
    elif choice == 27:
        stdev(x)
    elif choice == 28:
        pltpoints(pair1, pair2)

    choice = menu()
 
