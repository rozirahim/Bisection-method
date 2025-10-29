# Bisection Method in Python

def f(x):
    
    return x**3 - 4*x - 9

def bisection(a, b, tol):
    if f(a) * f(b) >= 0:
        print("Bisection method fails. Choose different a and b.")
        return None

    c = a
    while (b - a) >= tol:
        # Find midpoint
        c = (a + b) / 2

        # Check if root found
        if f(c) == 0.0:
            break

        # Decide the side to repeat
        if f(a) * f(c) < 0:
            b = c
        else:
            a = c

    return c

# Example usage:
a = 2  # left bound
b = 3  # right bound
tolerance = 0.0001

root = bisection(a, b, tolerance)
print(f"The root is approximately: {root}") 
