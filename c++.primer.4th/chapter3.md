Chapter 3
=========

## Exercise 3.1
	
	#include <iostream>

	using std::cin;
	using std::cout;
	using std::endl;

	int main() {
		int value, pow, result = 1;
		cout << "Enter base and exponent: ";
		cin >> value >> pow;
		for(int i = 0; i < pow; ++i)
			result *= value;
		cout << base
				<< "raised to the power of"
				<< pow << " is:\t"
				<< result << endl;
	}

## Exercise 3.2

> Special constructor, if the class has a default constructor, then we can define variables of that class without explicitly initializing them.

## Exercise 3.3

- `string s1;`
Default constructor; s1 is the empty string

- `string s2(s1);`
Initialize s2 as a copy of s1

- `string s3("value");`
Initialize s3 as a copy of the string literal

- `string s4(n, 'c');`
Initialize s4 with n copies of the character 'c'

## Exercise 3.4
	
	string s; //empty string
	int main() {
		string s2; //empty string
	}

## Exercise 3.5

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string line;
	while(getline(cin, line))
		cout << line << endl;
}
```

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string word;
	while(cin >> word)
		cout << word;
}
```

## Exercise 3.6

1. string input operator
	- Read and discards any leading whitespace (e.g., spaces, newlines, tabs)
	- It then reads characters until the next whitespace character is encountered

2. getline function
	- Read characters until the next character is newline character
	- Stop rading the input and returns
	- Skip newline character

## Exercise 3.7

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string s1, s2;
	cout << "Enter two words: ";
	cin >> s1 >> s2;
	if(s1 == s2)
		cout << "strings are equal" << endl;
	else if(s1.length() != s2.length())
		cout << (s1.length() > s2.length() ? s1 : s2) << " is longer" << endl;
}
```

## Exercise 3.8

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string strings, str;
	while(cin >> str)
		strings += str;
	cout << string << endl;
}
```

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string strings, str;
	while(cin >> str) {
		if(!strings.empty())
			strings += " ";
		strings += str;
	}
	cout << string << endl;
}
```

## Exercise 3.9

Invalid, because `s` is empty and `s[0]` is undefined.

## Exercise 3.10

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string line;
	while(getline(cin, line)) {
		for(string::size_type i = 0; i < line.length(); ++i)
			if(!ispunct(line[i]))
				cout << line[i];
		cout << endl;
	}
}
```

## Exercise 3.11

```cpp
vector< vector<int> > ivec; //valide
vector<string> svec = ivec; //invalide
vector<string> svec(10, "null"); //valide
```

## Exercise 3.12

```cpp
vector<int> ivec1; //empty
vector<int> ivec2(10); //10 elements 0
vector<int> ivec3(10, 42); //10 elements 42
vector<string> svec1; //empty
vector<string> svec2(10); //10 elements ""
vector<string> svec3(10, "hello"); //10 elements "hello" 
```

## Exercise 3.13

```cpp
#include <iostream>
#include <vector>
using namespace std;
int main() {
	int v;
	vector<int> vec;
	while(cin >> v)
		vec.push_back(v);
	bool odd = vec.size() % 2;
	vector<int>::size_type i;
	for(i = 0; i <= vec.size() - odd; i += 2)
		cout << "Sum of " << vec[i] << " and " << vec[i+1] << " is" << vec[i] + vec[i+1] << " ";
	if(odd)
		cout << vec.back() << " last element without summing it";
	cout << endl;
}
```

## Exercise 3.14

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <cctype>
using namespace std;
int main() {
	string s;
	vector<string> vec;
	while(cin >> s)
		vec.push_back(s);
	vector<string>::size_type i;
	for(i = 0; i < vec.size(); ++i) {
		string::size_type j;
		for(j = 0; i < vec[i].length(); ++j)
			cout << toupper(vec[i][j]);
		if((i+1) % 8)
			cout << " ";
		else
			cout << "\n";
	}
}
```

## Exercise 3.15

```cpp
vector<int> ivec(1, 42);
```

## Exercise 3.16

```cpp
vector<int> ivec(10, 42);
```

## Exercise 3.17

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string line;
	while(getline(cin, line)) {
		string::iterator iter;
		for(iter = line.begin(); iter != line.end(); ++iter)
			if(!ispunct(*iter))
				cout << *iter;
		cout << endl;
	}
}
```

## Exercise 3.18

```cpp
#include <vector>
using namespace std;
int main() {
	vector<int> vec(10, 41);
	vector<int>::iterator iter;
	for(iter = vec.begin(); iter != vec.end(); ++iter)
		*iter *= 2;
}
```

## Exercise 3.19

```cpp
#include <iostream>
#include <vector>
using namespace std;
int main() {
	vector<int> vec(10, 41);
	vector<int>::iterator iter;
	for(iter = vec.begin(); iter != vec.end(); ++iter) {
		*iter *= 2;
		cout << *iter << " ";
	}
	cout << endl;
}
```

## Exercise 3.20

Used vector::iterator to change the values in the vector, `const_iterator` which should be used when reading, but not writing

## Exercise 3.21

- Dereference a `const_iterator`, the value returned is `const`
- When we declare an `iterator` as `const` we must initialize the iterator, Once it is initialized, we may not change its value;

## Exercise 3.22

> [Error] no match for 'operator+' in 'vec.std::vector<_Tp, _Alloc>::end<int, std::allocator<int> >() + vec.std::vector<_Tp, _Alloc>::begin<int, std::allocator<int> >()'

## Exercise 3.23

1. bitset<64> bitvec(32);
2. bitset<32> bv(1010101);
3. string bstr; cin >> bstr; sitset<8>bv(bstr);

## Exercise 3.24

```cpp
bitset<32> v1(1 << 1 | 1 << 2 | 1 << 3 | 1 << 5 | 1 << 8 | 1 << 13 | 1 << 21);

bitset<32> v2;
v2.set(1);
v2.set(2);
v2.set(3);
v2.set(5);
v2.set(8);
v2.set(13);
v2.set(21);
```
