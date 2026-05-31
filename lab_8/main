import math
import numpy as np
def sequence(x, n):
    return [(x ** k) / k for k in range(1, n + 1)]
def product(n):
    p = 1
    for i in range(1, n + 1):
        p *= 1 / (i + math.factorial(i))
    return p
def determinant(n):
    a = [[0] * n for _ in range(n)]

    for i in range(n):
        a[i][i] = 2
        if i < n - 1:
            a[i][i + 1] = 3
        if i > 0:
            a[i][i - 1] = 1

    def det(m):
        if len(m) == 1:
            return m[0][0]
        if len(m) == 2:
            return m[0][0]*m[1][1] - m[0][1]*m[1][0]
        res = 0
        for c in range(len(m)):
            minor = [row[:c] + row[c+1:] for row in m[1:]]
            res += (-1) ** c * m[0][c] * det(minor)
        return res
    return det(a)
def sum_d(n):
    if n <= 0:
        return 0
    a = [0, 1]
    for i in range(2, n):
        a.append(a[i - 1] + a[i - 2])
    s = 0
    for k in range(n):
        s += (2 ** (k + 1)) * a[k]
    return s
def taylor_sin(x, eps):
    term = x
    result = 0
    n = 1
    while abs(term) > eps:
        result += term
        term *= -x * x / ((2 * n) * (2 * n + 1))
        n += 1
    return result
def compare_sin(x, eps=1e-6):
    t = taylor_sin(x, eps)
    m = math.sin(x)
    print("Taylor sin:", t)
    print("math.sin  :", m)
    print("Error     :", abs(t - m))

if __name__ == "__main__":
    print("=== 8.3.1 ===")
    # a
    x = float(input("Введіть x для (a): "))
    n = int(input("Введіть n для (a): "))
    print("a)", sequence(x, n))
    # b
    n = int(input("Введіть n для (b): "))
    print("b)", product(n))
    # c
    n = int(input("Введіть n для визначника (c): "))
    print("c)", determinant(n))
    # d
    n = int(input("Введіть n для (d): "))
    print("d)", sum_d(n))
    # e
    x = float(input("Введіть x для sin(x): "))
    eps = float(input("Введіть eps (наприклад 0.0001): "))
    t = taylor_sin(x, eps)
    m = math.sin(x)
    print("e) Taylor sin =", t)
    print("   math.sin   =", m)
    print("   error      =", abs(t - m))

