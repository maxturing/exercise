Chapter 8
=========

## Exercise 8.1

> output "Goodbye!" to `os`

## Exercise 8.2

```cpp
ostream print(ostream os);
//->
ostream& print(ostream &os);
```

## Exercise 8.3

```cpp
istream& readAll(istream &is) {
	char ch;
	while(is >> ch)
		cout << ch;
	is.clear();
	return is;
}
```

## Exercise 8.4

```cpp
#include <iostream>
using namecpace std;
istream& readAll(istream &is) {
	char ch;
	while(is >> ch)
		cout << ch;
	is.clear();
	return is;
}

int main() {
	readAll(cin);
}
```cpp

## Exercise 8.5

```cpp
badbit || failbit || eofbit
```

## Exercise 8.6

```cpp
#include <iostream>
#include <fstream>
using namespace std;
istream &readAll(istream &is) {
	char ch;
	while(is >> ch)
		cout << ch;
	is.clear();
	return is;
}
int main() {
	ifstream infile("in");
	readAll(infile);
}
```

## Exercise 8.7

```cpp
isfream input;
vector<string>::const_iterator it = files.begin();
while (it != files.end()) {
	input.open(it->c_str());
	if(input)
		while(input >> s)
			process(s);
	input.close();
	input.clear();
	++it;
}
```

## Exercise 8.8

```cpp
ifstream input;
vector<string>::const_iterator it = files.begin();
while(it != files.end()) {
	input.open(it->c_str());
	if (!input)
		continue;
	process(s);
	input.clear();
	input.close();
	++it;
}
```

## Exercise 8.9

```cpp
vector<string> readlines(istream &is) {
	sting line;
	vector<string> result;
	while(getline(is, line))
		result.push_back(line);
	return result;
}
```

## Exercise 8.10

```cpp
vecetor<string> readwords(istream &is) {
	string word;
	vector<string> result;
	while(is >> word)
		result.push_back(word);
	return result;
}
```


## Exercise 8.15

```cpp
istringstream is("aabbcc");
readAll(is);
```

## Exerecise 8.16

```cpp
#include <fstream>
#include <stringstream>
#include <iostream>
using namespace std;
int main() {
	ifstream input("file.in");
	string line;
	vector<string> vec;
	while(readline(input, line))
		vec.push_back(line);
	vector<string>::const_iterator iter;
	while(iter != vec.end()) {
		istringstream is(*iter);
		string word;
		while(is >> word)
			cout << word << endl;
		++iter;
	}
}
```