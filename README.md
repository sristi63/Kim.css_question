Trapping Rain Water (LeetCode 42)
📌 Problem Summary

You are given an array height[] where each element represents the height of a bar. When it rains, water gets trapped between taller bars. Your task is to compute the total amount of trapped rainwater.

Example:

Input:  [4,2,0,3,2,5]
Output: 9
🚀 Solution Approach: Monotonic Decreasing Stack

A monotonic decreasing stack helps detect valleys between bars that can hold water. Whenever we find a bar taller than the top of the stack, we check if a water trap is formed.

✔️ How It Works

Maintain a stack of indices.

Stack stores heights in descending order.

When a new bar is taller than stack top:

Pop the top → this becomes the "bottom" of the valley.

The bar at the new top of the stack is the left boundary.

The current bar is the right boundary.

Calculate trapped water using:

width = right - left - 1

height = min(leftHeight, rightHeight) - bottomHeight

Water added = width * height

🧠 Why Monotonic Stack?

Identifies valleys accurately.

Efficient: only one pass through the array.

Ideal for problems where boundaries matter.

📊 Complexity

Time: O(n) – Each element pushed and popped once.

Space: O(n) – Stack usage.

📘 Example Visualization

For 4,2,0,3,2,5:

Stack finds valleys between:

4 & 3

3 & 5

4 & 5

Total trapped water = 9 units
