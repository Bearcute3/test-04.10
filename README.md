n = int(input())
arr = [[0] * n for i in range(n)]
number = 1
k = 0
for i in range(n // 2):
    for j in range(n - k):
        arr[i][j + i] = number
        number += 1
    for j in range(i + 1, n - i):
        arr[j][-i - 1] = number
        number += 1
    for j in range(i + 1, n - i):
        arr[-i - 1][-j - 1] = number
        number += 1
    for j in range(i + 1, n - (i + 1)):
        arr[-j - 1][i] = number
        number += 1
    if n % 2 == 1:
        arr[n // 2][n // 2] = n * n
    k += 2
for i in arr:
    print(*i)
