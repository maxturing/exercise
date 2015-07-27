Chapter 1
=========

## Exercise 1.1

	$ g++ main.cpp -o main

## Exercise 1.2

```cpp
int main() {
	return -1;
}
```

## Exercise 1.3

```cpp
#include <iostream>
int main() {
	std::cout << "Hello, World" << std::endl;
}
```

## Exercise 1.4

```cpp
#include <iostream>
int main() {
	int v1, v2;
	cout << "Enter two numbers: ";
	cin >> v1 >> v2;
	cout << "The product of " << v1 << " and " << v2;
	cout << " is " << v1 * v2 << endl;
}
```

## Exercise 1.5

```cpp
#include <iostream>
int main() {
	int v1, v2;
	cout << "Enter two numbers: ";
	cin >> v1 >> v2;
	cout << "The product of ";
	cout << v1;
	cout << " and ";
	cout << v2;
	cout << " is ";
	cout << v1 * v2;
	cout << endl;
}
```

## Exercise 1.6

	非法, 因为在分号之后使用输入操作符.

