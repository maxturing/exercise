Chapter 4
=========

## Exercise 4.1

```cpp
unsigned buf_size = 1024;
int ia[buf_size]; //ok
int ia[get_size()]; //error: non const expression
char st[11] = "fundamental"; //error: initializer-string for array of chars is too long
```

## Exercise 4.2

```cpp
string sa[10]; //""
int ia[10]; //0
int main() {
	string sa2[10]; //""
	int ia2[10]; //uninitialized
}
```

## Exerciese 4.3

```cpp
int ia[7] = {0, 1, 1, 2, 3, 5, 8}; //ok
vector<int> ivec = {0, 1, 1, 2, 3, 5, 8}; //ok
int ia2[] = ia1; //error: array must initialized with a brace-enclosed initializer
int ia3[] = ivec; //error: array must initialized with a brace-enclosed initializer
```

## Exercise 4.4

```cpp
int ia1[4] = {1, 2};
int ia2[4] = {1, 2, 3, 4};
```

## Exercise 4.5

- Using an array extension is less convenient than vector
- No member function can be used

## Exercise 4.6

```cpp
const size_t array_size = 10;
int ia[array_size];
for(size_t ix = 0; ix < array_size; ++ix)
	ia[ix] = ix;
```

## Exercise 4.7

```cpp
const size_t array_size = 3;
int ia1[array_size] = {0, 3, 2};
int ia2[array_size];
for(size_t ix = 0; ix < array_size; ++ix)
	ia2[ix] = ia1[ix];
```

```cpp
vector<int> vec1 = {0, 3, 2};
vector<int> vec2(vec1);
```

## Exercise 4.8

```cpp
bool array_equal(int *ia1, int *ia2, size_t size) {
	int i;
	for(int i = 0; i < size; ++i)
		if(ia1[i] != ia2[i]) break;
	return i == size;
}

bool vector_equal(const vector<int> &v1, const vector<int> &vv2) {
	return v1 == v2;
}
```

## Exercise 4.9

```cpp
const size_t size_array = 10;
int ia[size_array];
for(size_t i = 0; i < size_array; ++i)
	ia[i] = i;
```

## Exercise 4.10

```cpp
int *ip; //good practice
int* ip; //legal but misleading
//because multiple pointer declarations can be confusing
//e.g., int* ip1, ip2, ip3;
//ip1 is pointer to integer
//ip2 and ip3 is integer
```

## Exercise 4.11

```cpp
int* ip; //legal but misleading
string s, *sp = 0; //legal
int* ip, ip2; //ip is pointer to integer, ip2 is a integer
const int i = 0, *p = i; //illegal: can not convert int to *int
string *p = NULL; //legal
```

## Exercise 4.12

> It is not possible to detect whether a pointer is uninitialized. There is no way to distinguish a valid address from an address formed from the bits that are in the memory in which the pointer was allocated.

## Exercise 4.13

```cpp
int i = 42;
void *p = &i; //`i` can be an object of any type
long lp = &i; //the type of `lp` and `&i` is not the same
```

## Exercise 4.14

```cpp
int *p = NULL;
int v = 1;
p = &v;
*p = 2;
//v == 2
```

## Exercise 4.15

> While both references and pointers are used to indirectly access another value, there are two important differences between reference and pointers. The fist is that a reference always refers to an object: It is an error to define a reference without initializing it. The behavior of assignment is the second important difference: Assigning to a reference changes the object to which the reference is bound; it does not rebind the reference to another object. Once initialized, a reference always refers to the same underlying object.

## Exercise 4.16

```cpp
int i = 42, j = 1024;
int *p = &i, *p2 = &j;
*p2 = *p1 * *p2; //j = i * j;
*p1 *= *p1; //i *= i
```

## Exercise 4.17

```cpp
p1 += p2 - p1;
//equal
p1 = p2;
```

## Exercise 4.18

```cpp
size_t array_size = 10;
int ia[array_size];
for (int *begin = ia, *end = ia + array_size;
		begin != end; ++begin)
	*begin = 0;
```

## Exercise 4.19

```cpp
int i; //ok
const int ic; //error: const must initinized
const int *pic; //ok
int *const cpi; //ok
const int *const cpic; //error: const must initinized
```

## Exercise 4.20

```cpp
int i = -1; //ok
const int ic = i; //ok
const int *pic = &ic; //ok
int *const cpi = &ic; //error: convert `const int *` to `int *`
const int *const cpic = &ic; //ok
```

## Exercise 4.21

```cpp
i = ic; //ok
pic = &ic; //ok
cpi = pic; //error: convert `const int *` to `int *`
ic = *cpic; //error: attempt to writte to const object
```

## Exercise 4.22

```cpp
const char *cp = "hello";
int cnt;
//cp always > 0
while(cp) {++cnt; ++cp;}
//*cp = h e l l o \0;
while(*cp) {++cnt; ++cp;}
```

## Exercise 4.23

```cpp
const char ca[] = {'h', 'e', 'l', 'l', 'o'};
const char *cp = ca;
while(*cp) {
	cout << *cp << endl;
	++cp;
}
```

> the loop is apt to read characters starting at cp until it encounters a null character somewhere in memory.

## Exercise 4.24

- strcpy(s1, s2)
Copies s2 into s1, Return s1

- strncpy(s1, s2, n)
Cpoies n characters from s2 into s1. Return s1

- strcpy more convenient, strncpy more secure

## Exercise 4.25

- string
	- operator>
	- operatlr<
	- operator==

- c-style chatachter
	- strcmp(s1, s2)

## Exercise 4.26

```cpp
string word;
cin >> word;
char buf[20];
cin >> buf;
```

## Exercise 4.27

```cpp
int *pa = new int[10];
delete []pa;
```

## Exercise 4.28

```cpp
#include <iostream>
#include <vector>
using namespace std;
int main() {
	int v;
	vector<int> vec;
	while(cin >> v)
		vec.push_back(v);
	int *arr = new int[vec.size()];
	vector<int>::size_type i;
	for(i = 0; i < vec.size(); ++i)
		arr[i] = vec[i];
}
```

## Exercise 4.29



## Exercise 4.30

```cpp
char *pca = "aabbcc";
char *pcb = "ddeeff";
pca = strcat(pca, pcb);

string s1 = "aabbcc";
string s2 = "ddeeff";
s1 = s1 + s2;
```

## Exercise 4.31



## Exercise 4.32

```cpp
vector<int> vec = {0, 1, 4, 2};
```

## Exercise 4.33

```cpp
vector<int> vec = {0, 1, 4, 2};
int arr = new int[vec.size()];
vector<int>::size_type i;
for(i = 0; i < vec.size(); ++i)
	arr[i] = ve[i];
```

## Exercise 4.34

```cpp
vector<string> vec;
string str;
while(cin >> str)
	vec.push_back(str);
vector<string>::size_type i;
char *string_array[] = new char*[vec.size()];
for(i = 0; i < vec.size(); ++i)
	string_array[i] = vec[i].c_str();
```

## Exercise 4.35

```cpp
vector<string> vec;
string str;
while(cin >> str)
	vec.push_back(str);
vector<string>::size_type i;
char *string_array[] = new char*[vec.size()];
for(i = 0; i < vec.size(); ++i)
	string_array[i] = vec[i].c_str();
for(i = 0; i < vec.size(); ++i) {
	cout << vec[i] << endl;
	cout << string_array[i] << endl;
	delete []string_array[i];
}
```

## Exercise 4.36

```cpp
#include <iostream>
using namespace std;
int main() {
	int ia[3][4] = {
		{0, 1, 2, 3},
		{4, 5, 6, 7},
		{8, 9, 10, 11}
	};
	for(int (*p)[4] = ia; p != ia + 3; ++p)
		for(int *q = *p; q != *p + 4; ++q)
			cout << *q << endl;
}
```