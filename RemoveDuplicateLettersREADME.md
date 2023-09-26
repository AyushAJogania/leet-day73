# leet-day73

# Remove Duplicate Letters - LeetCode Problem

## Problem Description

Given a string `s`, remove duplicate letters so that every letter appears once and only once. The goal is to ensure that the resulting string is the smallest in lexicographical order among all possible results.

## Example

**Input:**
```
s = "bcabc"
```
**Output:**
```
"abc"
```

**Input:**
```
s = "cbacdcbc"
```
**Output:**
```
"acdb"
```

## Approach

The provided solution uses a stack-based approach to solve the problem efficiently. Here's how it works:

1. Initialize a `lastIndex` vector to store the last index where each character appears in the string `s`. This helps determine if a character can be removed later.

2. Create a `seen` vector of boolean values to keep track of whether a character has been encountered before.

3. Iterate through the characters of the input string `s`.

4. For each character `s[i]`, if it has been seen before, skip it to avoid duplication.

5. If the character hasn't been seen before, check the stack. While the stack is not empty, the top character is greater than the current character (`s[i]`), and there are more occurrences of the top character later in the string (`i < lastIndex[st.top() - 'a']`), pop the top character from the stack and mark it as unseen.

6. Push the current character `s[i]` onto the stack and mark it as seen.

7. After processing all characters, construct the result string `ans` by popping characters from the stack.

8. Reverse `ans` to obtain the correct lexicographical order since characters were added to the stack in reverse order.

## Complexity Analysis

The provided solution has a time complexity of O(n), where n is the length of the input string `s`. This makes it an optimal solution for the problem in terms of time complexity.

## Usage

You can use this solution by creating an instance of the `Solution` class and calling the `removeDuplicateLetters` method with the input string `s`. It will return the smallest lexicographical string with duplicate letters removed.

```cpp
Solution solution;
string result = solution.removeDuplicateLetters(s);
```

