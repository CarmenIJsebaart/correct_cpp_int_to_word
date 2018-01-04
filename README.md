# correct_cpp_int_to_word

Branch|[Travis CI](https://travis-ci.org)|[Codecov](https://www.codecov.io)
---|---|---
master|[![Build Status](https://travis-ci.org/CarmenIJsebaart/correct_cpp_int_to_word.svg?branch=master)](https://travis-ci.org/CarmenIJsebaart/correct_cpp_int_to_word)|[![codecov.io](https://codecov.io/github/CarmenIJsebaart/correct_cpp_int_to_word/coverage.svg?branch=master)](https://codecov.io/github/CarmenIJsebaart/correct_cpp_int_to_word/branch/master)

[Correct C++](https://github.com/richelbilderbeek/correct_cpp) chapter 'Hello CLI'.

## Goal

 * Write an application with 100% code coverage

## Prerequisites

 * Understand [how this course works](https://github.com/richelbilderbeek/correct_cpp/blob/master/how_this_course_works.md)
 * Have written [a correct 'is_odd' program](https://github.com/richelbilderbeek/correct_cpp_is_odd)

## Exercise

Write a command-line interface (CLI) program that convert the number 1 to (and including 6) to their words, followed by a newline.

Fail if the user supplies no, two or more arguments

Call to `hello_cli`|Output|Exit status
---|---|---
`./int_to_word`|Any|1
`./int_to_word 1`|`one` (with newline)|0
`./int_to_word 2`|`two` (with newline)|0
`./int_to_word 3`|`three` (with newline)|0
`./int_to_word 4`|`four` (with newline)|0
`./int_to_word 5`|`five` (with newline)|0
`./int_to_word 6`|`six` (with newline)|0
`./int_to_word nonsense`|Any|1
`./int_to_word 1 2`|Any|1

This is the code you start with:

```c++
#include <iostream>
#include <string>
#include <vector>

int main(int argc, char* argv[]) 
{
  if (argc != 2)
  {
    return 1;
  }
  try
  {
    const int i{std::stoi(argv[1])};
    switch (i)
    {
      case 1: std::cout << "one\n"; break;
      case 2: std::cout << "two\n"; break;
      case 3: std::cout << "three\n"; break;
      case 4: std::cout << "four\n"; break;
      case 5: std::cout << "five\n"; break;
      case 6: std::cout << "six\n"; break;
      default: throw std::invalid_argument("i must be in range [1, 6]");
    }
  }
  catch (const std::exception&)
  {
    return 1;
  }
}
```

 * Your code needs to have 100% code coverage, regardless how it is called (that is, with zero, one or more arguments), 
   see [how to get 100 percent code coverage](https://github.com/richelbilderbeek/correct_cpp/blob/master/get_100_percent_code_coverage.md)

## External links

 * [Download the Qt Creator file `main.pro`](https://raw.githubusercontent.com/richelbilderbeek/correct_cpp/master/shared/main.pro)
