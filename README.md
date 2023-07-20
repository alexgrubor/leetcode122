# Stock Trading Max Profit

This repository contains a JavaScript implementation to find the maximum profit that can be achieved by trading a given stock.

## Problem Description

You are given an integer array `prices` where `prices[i]` represents the price of the stock on the `ith` day. On each day, you have the option to buy and/or sell the stock. However, you can only hold at most one share of the stock at any time, and you can buy it then immediately sell it on the same day.

The task is to find and return the maximum profit that can be achieved.

### Example 1:
Input: `prices = [7, 1, 5, 3, 6, 4]`
Output: `7`
Explanation: 
- Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.
- Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.
- Total profit is 4 + 3 = 7.

### Example 2:
Input: `prices = [1, 2, 3, 4, 5]`
Output: `4`
Explanation: 
- Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.
- Total profit is 4.

### Example 3:
Input: `prices = [7, 6, 4, 3, 1]`
Output: `0`
Explanation: There is no way to make a positive profit, so we never buy the stock, resulting in a maximum profit of 0.

## Solution

The solution to this problem is implemented in JavaScript. The function `maxProfit(prices)` takes an array of stock prices as input and returns the maximum profit that can be achieved by buying and selling the stock optimally.

```javascript
const maxProfit = (prices) => {
  if (prices.length < 2) {
    return 0;
  }
  let profit = 0;
  for (let i = 0; i < prices.length - 1; i++) {
    if (prices[i] < prices[i + 1]) {
      profit += prices[i + 1] - prices[i];
    }
  }
  return profit;
};

console.log(maxProfit([7, 6, 4, 3, 1])); // Output: 0
```

## How to Use

To find the maximum profit for a given array of stock prices, simply call the `maxProfit(prices)` function, passing the `prices` array as the argument. The function will return the maximum profit achieved by trading the stock.

Feel free to use and modify this implementation for your needs.

