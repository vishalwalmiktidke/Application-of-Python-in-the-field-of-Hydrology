# Application-of-Python-in-the-field-of-Hydrology
ASSIGNMENT NO. 02


Q.1) # To find the downstream depth of open channel
# Given Data
Q = float(input("Enter the value of Discharge (m³/s): "))
B1 = float(input("Enter the value of width at upstream (m): "))
B2 = float(input("Enter the value of width at downstream (m): "))
g = float(input("Enter the value of acceleration due to Gravity (m/s²): "))
y1 = float(input("Enter the value of upstream depth (m): "))

# Discharge per meter width
q1 = Q / B1
q2 = Q / B2
print("The value of discharge per meter width at upstream is:", q1)
print("The value of discharge per meter width at downstream is:", q2)

# Area calculation
A1 = B1 * y1
print("The value of upstream area is:", A1)

# Calculation of Froude Number
Fr1 = ((Q**2 * B1) / (g * A1**2))**0.5
print("The value of Froude number is:", Fr1)

if Fr1 > 1:
    print("The flow is Super Critical Flow")
else:
    print("The flow is Sub Critical Flow")

# Upstream Energy
E1 = y1 + (Q**2 / (2 * g * A1**2))
print("The value of Energy at initial section is:", E1)

# Minimum width to avoid choking condition
B2min = ((27 * Q**2) / (8 * g * E1**3))**0.5
print("The value of minimum width to be kept to avoid Choking is:", B2min)

if B2min > B2:
    print("Choking Condition")
else:
    print("SAFE")

# Critical Depth
yc = (Q**2 / (B2 * 8 * g))**(1/3)  # Corrected the formula for critical depth
print("The value of critical depth is:", yc)

# Critical Energy
Ec = 1.5 * yc
print("The value of critical Energy is:", Ec)

OUTPUT:
Enter the value of Discharge (m³/s): 100
Enter the value of width at upstream (m): 250
Enter the value of width at downstream (m): 12
Enter the value of acceleration due to Gravity (m/s²): 35
Enter the value of upstream depth (m): 14
The value of discharge per meter width at upstream is: 0.4
The value of discharge per meter width at downstream is: 8.333333333333334
The value of upstream area is: 3500.0
The value of Froude number is: 0.07636035483212125
The flow is Sub Critical Flow
The value of Energy at initial section is: 14.00001166180758
The value of minimum width to be kept to avoid Choking is: 0.5928028327040221
SAFE
The value of critical depth is: 1.43842395666197
The value of critical Energy is: 2.157635934992955
