Chapter 2
=========

## Exercise 2.1

占用的存储空间不同, 表示数字的范围也不同.

## Exercise 2.2

`unsigned` 表示无符号数, `signed`  表示有符号数.

## Exercise 2.3

`short` 最大 `2^15 - 1`, `unsigned short` 最大 `2^16 - 1`.

## Exercise 2.4

100000 = 0x186a0, 0x100000 溢出, 0x86a0 = 34464

## Exercise 2.5

> The `float` type is usually not precise enough for real programs `float` is guaranteed to offer only 6 significant digits. The `double` type guarantees at least 10 significant digits, which is sufficient for most calculations.

## Exercise 2.6

 > Determining which floating-point type to use is easier: It is almost always right to use `double`

## Exercise 2.7

1. character string
- single character `a` of type `char`.
- single character `a` of type `wchar_t`.
- the letter `a` and the null character of type `char`.
- the letter `a` and the null chatacter of type `wchar_t`.

2. integer
- int
- unsigned int
- long
- unsigned long
- octal
- hexadecimal

3. floating-point
- double
- float
- double

## Exercise 2.8

- int
- unsigned int
- double
- double

## Exercise 2.9

CF

## Exercise 2.10

	#include <iostream>

	int main() {
		std::cout << "2M" << std::endl;
		std::cout << "2\tM" << std::endl;
	}

## Exercise 2.11

	#include <iostream>
	int main() {
		int base, pow, result = 1;
		std::cout << "Enter base and exponent: ";
		std::cin >> base >> pow;
		for(int i = 0; i < pow; ++)
			result *= base;
		std::cout << base
				<< " raised to the power of "
				<< pow << ": \t"
				<< result << std::endl;
	}


## Exercise 2.12

1. `lvalue`: An expression that is an lvalue may appear as either the left-hand or right-hand side of an assignment.(eg. variables)
2. `rvalue`: An expression that is an rvalue may appear on the right-hand but not left-hand side of an assignment. (eg. literal constant )

## Exercise 2.13

variable allow modification

## Exercise 2.14

1. `int double = 1.14159;` -> `int _double = 3.14159;`
2. `bool catch-22;` -> `bool catch = true;`
3. `char 1_or_2 = '1'` -> `char one_or_two = '1'`;

## Exercise 2.15

- `int month = 9, day = 7` month is digit 9 and day is digit 7
- `int month = 09, day = 07` day is digit 7 but month is invalid
- `int month = 09, day = 07` -> `int month = 011, day = 07`

## Exercise 2.16

1. `int car = 1024, auto = 2048;` -> `int car = 1024, _auto = 2048`
2. `int ival = ival;` -> `int val = ival;`
3. `std::cin >> int input_value` -> `int v; std::cin >> v;`
4. `double salary = wage = 9999.99` -> `double salary, wage; salary = wage = 9999.99;`
5. `double calc = calc()` -> `double _calc = calc();`

## Exercise 2.17

	std::string global_str; //initialized to empty
	int global_int; //initialized to zero
	int main() {
		int local_int; //uninitialized
		//...
		return 0;
	}

## Exercise 2.18

	extern std::string name; //declares but not define
	std::string name("exercise 3.5a"); //definition
	extern std::string name("exercise 3.5a"); //error: redifinition of name

## Exercise 2.19

	int i = 42;
	int main() {
		int i = 100;
		int j = i; //j = 100
		// ...
	}

## Exercise 2.20

	int i = 100, sum = 0;
	for(int i = 0; i != 10; ++i)
		sum += i;
	std::cout << i << " " << sum << std::endl;
	//output: 100 45

## Exercise 2.21

	int sum = 0;
	for(int i = 0; i != 10; ++i)
		sum += i;
	std::cout << "sum from 0 to " << i //error: variable i is undefined
			<< " is " << sum << std::endl;