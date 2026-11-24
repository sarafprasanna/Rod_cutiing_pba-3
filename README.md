# Rod_cutiing_pba-3
def rod_cutting(price, n):
    dp = [0] * (n + 1)

    for i in range(1, n + 1):
        max_profit = 0

        for j in range(i):
            max_profit = max(max_profit,
                             price[j] + dp[i - j - 1])

        dp[i] = max_profit

    return dp[n]


# Main Program
price = [2, 5, 7, 8, 10, 13, 15, 17]

n = int(input("Enter the length of rod: "))

if n <= 0 or n > len(price):
    print("Invalid rod length")
else:
    result = rod_cutting(price, n)
    print("Maximum Profit:", result)
