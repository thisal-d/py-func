# py-func

## Introduction

`py-func` is a C++ header-only library that provides a comprehensive suite of functions for manipulating strings, vectors, and arrays—mimicking popular Python functionalities. It is designed to enable C++ developers to write more expressive and concise code for data manipulation, similar to Python's standard library.

---

## Features

- **String Manipulation:** Functions for splitting, joining, replacing, counting, and slicing strings.
- **Vector Manipulation:** Python-like utilities for slicing, replacing, joining, and counting elements in vectors.
- **Array Manipulation:** Seamless support for classic arrays and `std::array`, including slicing, replacing, joining, and counting.
- **Range Generation:** Generate integer sequences, similar to Python's `range()`.

---

## Installation

This is a header-only library. Simply copy the required header files or the master header (`py-func.h`) into your project.

---

## Usage

### Including the Entire Library

Include the master header in your C++ source file:

```cpp
#include "py-func.h"
```

### Including Individual Functions

If you only need specific functionalities, include the required headers:

```cpp
#include "count.h"
#include "join.h"
#include "range.h"
#include "replace.h"
#include "slice.h"
#include "split.h"
```

---

## Overview

### 1. Range

- **Generate a sequence of numbers (like Python's `range()`)**

  ```cpp
  auto nums = pyfunc::range<int>(0, 10, 2); // {0, 2, 4, 6, 8}
  ```

### 2. Slice

- **Slice for `std::string`:**
  
  ```cpp
  std::string s = "0123456789";
  auto res = pyfunc::slice(s, 0, 5, 1);  // "01234"
  auto rev = pyfunc::slice(s, -1, -5, -1); // "9876"
  ```

- **Slice for `std::vector`:**

  ```cpp
  std::vector<int> v = {1, 2, 3, 4, 5};
  auto sub = pyfunc::slice(v, 0, 3, 1); // {1, 2, 3}
  ```

- **Slice for arrays:**

  ```cpp
  int arr[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
  auto part = pyfunc::slice(arr, 10, 1, 9, 2); // {1, 3, 5, 7}
  ```

### 3. Replace

- **Replace in `std::string`:**
  
  ```cpp
  std::string str = "hello world";
  auto replaced = pyfunc::replace(str, "world", "C++"); // "hello C++"
  ```

- **Replace in `std::vector`:**

  ```cpp
  std::vector<std::string> words = {"abc", "def", "ghi"};
  auto out = pyfunc::replace(words, "abc", "xyz"); // {"xyz", "def", "ghi"}
  ```

- **Replace in arrays:**

  ```cpp
  int numbers[5] = {1, 2, 2, 3, 2};
  pyfunc::replace(numbers, 5, 2, 9); // {1, 9, 9, 3, 9}
  ```

### 4. Split

- **Split a string:**

  ```cpp
  std::string str = "c:/users/user/appdata";
  auto parts = pyfunc::split(str, "/"); // {"c:", "users", "user", "appdata"}
  ```

- **With custom delimiters:**

  ```cpp
  std::string str = "1>>432>>3>>4213>>5";
  auto out = pyfunc::split(str, ">>"); // {"1", "432", "3", "4213", "5"}
  auto out2 = pyfunc::split(str, '>'); // {"1", "", "432", "", "3", "", "4213", "", "5"}
  ```

### 5. Count

- **Count occurrences in string:**

  ```cpp
  std::string str = "banana";
  int n = pyfunc::count(str, "a"); // 3
  ```

- **Count in vectors or arrays:**

  ```cpp
  std::vector<int> nums = {1, 2, 2, 3};
  int cnt = pyfunc::count(nums, 2); // 2
  ```

### 6. Join

- **Join elements into a string:**

  ```cpp
  std::vector<std::string> words = {"this", "is", "C++"};
  std::string joined = pyfunc::join(words, "-"); // "this-is-C++"
  ```

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## Contributing

Contributions, bug reports, and feature requests are welcome. Please open an issue or submit a pull request.

---

## Author

Thisal Dilmith
