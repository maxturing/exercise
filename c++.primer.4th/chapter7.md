Chapter 7
=========

## Exercise 7.1

> Like local variables, the parameters of a function proide named, local storage for use by the function. The difference is that parameters and difined inside the function's parameter list and are  initialized by arguments passed to the function when the function is called.

> An argument is an expression. It might be a variable, a literal constant or an expression involving one or more operators. We must pass exactly the same nuber of arguments as the function has parameter in the same way that the type of an initializer must match the type of object it initializes: The argument must have the same type of have type that can be implicitly converted to the parameter type.

## Exercise 7.2

```cpp
int f() {
	string s;
	// ...
	return s;
}

int f2() {
	// ...
}

int calc(int v1, int v2) {
	// ...
}

double square(double x) {
	return x * x;
}
```

## Exercise 7.3

```cpp
#include <iostream>
using namespace std;
int pow(int base, int exponent) {
	int result = 1;
	while(int i = 0; i < exponent; ++i)
		result *= base;
	return result;
}
int main() {
	cout << pow(2, 3) << endl;
}
```

## Exercise 7.4

```cpp
int abs(int x) {
	return x < 0 ? -x : x;
}
```

## Exercise 7.5

```cpp
int foo(int x, int *p) {
	return x > *p ? x : *p;
}
```

## Exercise 7.6

```cpp
void swap(int *&p1, int *&p2) {
	int *p = p1;
	p1 = p2;
	p2 = p;
}
```

## Exercise 7.7

> Like all references, reference parameters refer idrectly to the objects to which they are bound rather than to copies of those objects. When we define a reference, we must initialize it with the object to which the reference whill bound. Reference parameters work exactly the same way. Each time the function is called, the reference parameters is created and bound to its corresponding argument.


## Exercise 7.10

```cpp
bool test(const string& s) {
	return s.empty();
}
```

## Exercise 7.13

```cpp
int arr[] = {0, 1, 2, 3, 4};
size_t size = 5;
for(int *p = arr; p < arr+size; ++p)
	sum += *p;

for(size_t i = 0; i < size; ++i)
	sum += arr[i];
```

## Exercise 7.14

```cpp
double sum = 0.0;
vector<double>::iterator iter;
for(iter = vec.begin(); iter != vec.end(); iter++ )
	sum += *iter;
```

## Exercise 7.15

```cpp
#include <iostream>
#include <cstdlib>
using namespace std;
int main(int argc, char **argv) {
	cout << atoi(argv[1]) + atoi(argv[2]) << endl;
}
```

## Exercise 7.16

```cpp
#include <iostream>
using namespace std;
int main(int argc, char **argv) {
	for(int i = 0; i < argc; ++i)
		cout << argv[i] << endl;
}
```

## Exercise 7.18

> Never Return a Reference to a Local Object

## Exercise 7.19

> Legal, set each element to zero;

## Exercise 7.20

```cpp
int factorial(int val) {
	int result = 1;
	for(int i = 1; i <= val; ++i)
		result *= i;
	return result;
}
```

## Exercise 7.21

> When `val` less than zero, endless loop appears.

## Exercise 7.22

```cpp
bool compare(const &matrix, const &matrix);

vector<int>::iterator iter change_val(int, vector<int>::iterator);
```

## Exercise 7.23

```cpp
double calc(double);
int count(const string&, char);
int sum(vector<int>::iterator, vector<int>::iterator, int);
calc(23.4, 55.1); //require `double calc(double, double);`
count("abcda", 'a'); //ok
calc(66); //ok
sum(vec.begin(), vec.end(), 3.8); //ok
```

## Exercise 7.24
```cpp
int ff(int a, int b = 0, int c = 0); //ok

char *init(int ht = 24, int wd, char bckgrnd);

//->

char *init(int wd, char bckgrnd, int ht = 24);
```

## Exercise 7.25

```cpp
//declarations
char *init(int ht, int wd = 80, char bckgrnd = ' ');

init(); //error: undefined function `::init()`
init(24, 10); //ok
init(14, '*'); //warning: init(ht = 14, wd = '*');
```

## Exercise 7.26

```cpp
string make_plural(const string& s) {
	if (s == "success")
		return "successes";
	else if( s = "failure")
		return "failures";
}
```


## Exercise 7.27

> Automatic objects, including parameters, are destoryed at the end of the block in which they where defined. Parameters are defined in the function's block and so are destoryed when the function terminates. When a function exits, its local storage is deallocated. After the function exits, the values of its automatic objects and parameters are not longer accessible.

> A static local object is guaranteed to be initialized no later than the first time that program execution passes throuth the object's definition. Once it is created, it is not destoryed until the program terminates; local statics are not destoryed when the function ends. Local statices continue to exist and hold their value across calls to the function.

```cpp
void test(int p) {
	static int s = 0;
	int a = 0;
	++s;
	++a;
	++p;
	cout << p << s << a << endl;
}
```

## Exercise 7.28

```cpp
int foo() {
	static int cnt = 0;
	return cnt++;
}
```

## Exercise 7.29

```cpp
//header file
inline bool eq(const BitInt&, const BitInt&) { ... }

//program text file
void putValues(int *arr, int size);
```

> Unlike other function definitions, inlines should be defined in header files. To expand the code of an inline function at the point of call, the compiler must have access to the function defintion. The function prototype is insufficient.

## Exercise 7.30

inline bool isShorter(const string& s1, const string& s2) {
	return s1.length() < s2.length();
}

## Exercise 7.31

```cpp
#include <iostream>
using namespace std;
class Sales_item {
	
public:
	void input(istream &is) {
		is >> isbn >> count >> price;
	}
	void output(ostream &os) {
		os << isbn << count << total_price() << price;
	}
	double total_price() {
		return price * count;
	}
}

int main() {
	Sale_item book;
	book.input(cin);
	book.output(cout);
}
```

## Exercise 7.34

```cpp
int index, upperBound;
char selectVal;
//...
error("Subscript out of bounds: ", index, upperBound);
//void error(const string&, int, int);
error("Division by zero");
//void error(const string&);
error("Invalid selection", selectVal);
//void error(const string&, int);
```

## Exercise 7.35

```cpp
int calc(int, int);
int calc(const int, const int);

int get();
double get();

int *reset(int *);
double *reset(double *);
```

## Exercise 7.36

> `Candidate Fuctions`: The set of overloaded functions considered for the call.

> `Viable Functions`: Functions from the set of candidate functions that can be called with the arguments specified in the call.

## Exercise 7.37

```cpp
	void f();
	void f(int);
	void f(int, int);
	void f(double, double = 3.14);

	f(2.56, 42) //error: call is ambiguous
	f(42); //void f(int);
	f(42, 0); //void f(int, int);
	f(2.56, 3.14); //void f(double, double);
```
