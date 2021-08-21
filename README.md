
# Big-O Notation Practice

In this exercise, you’ll analyze expressions and code to figure out the time complexity.

## Step One: Simplifying Expressions

Simplify the following big O expressions as much as possible:
| ORIGINAL | SIMPLIFIED | Explanation |
|----------|:----------:|:-----------:|
|  O(n + 10)     |   O(n)   | 
|  O(100 * n)    |   O(n)   |
|  O(25)         |   O(1)  |
|  O(n^2 + n^3)  |   O(n^3)  |
|  O(n + n + n + n)  |   O(n)  |
|  O(1000 * log(n) + n)  |  O(n)   | O(n) because n is much larger at oo than log(n) |
|  O(1000 * n * log(n) + n)  |   O(n log(n))  | 
|  O(2^n + n^2)  |  O(2^n)   |
|  O(5 + 3 + 1)  |  O(1)   |
|  O(n + n^(1/2) + n^2 + n * log(n)^10)  |  O(n * log(n)^10)   |

They all involved just putting in a small 'n' and a much larger 'n' and seeing which part had a greater impact on the total.


## Step Two: Calculating Time Complexity

Determine the time complexities for each of the following functions. If you’re not sure what these functions do, copy and paste them into the console and experiment with different inputs!
```
function logUpTo(n) {
  for (let i = 1; i <= n; i++) {
    console.log(i);
  }
}

// Time Complexity: O(n)  -- n drives the loop
```


```
function logAtLeast10(n) {
  for (let i = 1; i <= Math.max(n, 10); i++) {
    console.log(i);
  }
}

// Time Complexity: O(n)  -- n drives the loop
```

```
function logAtMost10(n) {
  for (let i = 1; i <= Math.min(n, 10); i++) {
    console.log(i);
  }
}

// Time Complexity:  O(1)  -- loop stops at 10, no matter how big n becomes.
```

```
function onlyElementsAtEvenIndex(array) {
  let newArray = [];
  for (let i = 0; i < array.length; i++) {
    if (i % 2 === 0) {
      newArray.push(array[i]);
    }
  }
  return newArray;
}

// Time Complexity: O(n)  -- for loop takes longer as n, number of elements, increases
```

```
function subtotals(array) {
  let subtotalArray = [];
  for (let i = 0; i < array.length; i++) {
    let subtotal = 0;
    for (let j = 0; j <= i; j++) {
      subtotal += array[j];
    }
    subtotalArray.push(subtotal);
  }
  return subtotalArray;
}

// Time Complexity: O(n^2)  -- array length, n, is the bounds for both 
```

```
function vowelCount(str) {
  let vowelCount = {};
  const vowels = "aeiouAEIOU";

  for (let char of str) {
    if(vowels.includes(char)) {
      if(char in vowelCount) {
        vowelCount[char] += 1;
      } else {
        vowelCount[char] = 1;
      }
    }
  }

  return vowelCount;
}

// Time Complexity: O(n)  -- length of string, n, drives the time.
```

## Part 3 - short answer

Answer the following questions

**1. True or false: `n^2 + n` is `O(n^2)`.**  True, '+n' effect at infinity is nominal. 

**2. True or false: `n^2 * n` is `O(n^3)`.**  True

**3. True or false: `n^2 + n` is `O(n)`.**  False, O(n^2), same as #1

**4. What’s the time complexity of the `.indexOf` array method?**  O(n)

**5. What’s the time complexity of the `.includes` array method?**  O(n)

**6. What’s the time complexity of the `.forEach` array method?**  O(n)

**7. XX What’s the time complexity of the `.sort` array method?**  Taking a stab and saying probably the O(n^2).  Nope. I guess they did a halfway decent implentation in JavaScript. It is `n log(n)`

**8. What’s the time complexity of the `.unshift` array method?**  O(n), worst case is everything in the array shifts.

**9. What’s the time complexity of the `.push` array method?**  O(1)

**10. What’s the time complexity of the `.splice` array method?**  O(n), as with `unshift`, worst case is everything in the array has to shift because of the splice, which can happen anywhere in the array.

**11. What’s the time complexity of the `.pop` array method?**  O(1)

**12. What’s the time complexity of the `Object.keys()` function?**  O(n)

**13. BONUS: What’s the space complexity of the `Object.keys()` function?**  O(n) because space is needed for each key in the object.

Solution

View our solutions
