Chapter 6
=========

## Exercise 6.1

> null statement is a single semicolon

```cpp
while(true);
for(;;);
```

## Exercise 6.2

> A `compound statement`, usually referred to as a `blok`, is a (possibly empty) sequence of statements surrounded by a pair of curly braces.

```cpp
if(...) {
	//A block
} else {
	//B block
}
```

## Exercise 6.3

```cpp
// if so, read the transaction records
while(std::cin >> trans)
	total = total.same_isbn(trans) ? total + trans : trans;
```

## Exercise 6.4

> compile error: `if` not found

## Exercise 6.5

```cpp
if (ival1 != ival2)
	ival1 = ival2;
else
	ival1 = ival2 = 0;

if (ival < minval) {
	minval = ival;
	occurs = 1;
}

if (int ival = get_value())
	cout << "ival = " << ival;
else
	cout << "ival = 0\n";

if (ival = 0)
	ival = get_value();
```

## Exercise 6.6

> Matching the `else` with the last occurring unmathed `if`.

## Exercise 6.7

```cpp
switch (ch) {
	case 'a':
	case 'A':
		++aCnt; break;
	case 'e':
	case 'E':
		++eCnt; break;
	case 'i':
	case 'I':
		++iCnt; break;
	case 'o':
	case 'O':
		++oCnt; break;
	case 'u':
	case 'U':
		++uCnt; break;
}
```

## Exercise 6.8

```cpp
switch (ch) {
	case 'a':
	case 'A':
		++aCnt; break;
	case 'e':
	case 'E':
		++eCnt; break;
	case 'i':
	case 'I':
		++iCnt; break;
	case 'o':
	case 'O':
		++oCnt; break;
	case 'u':
	case 'U':
		++uCnt; break;
	case ' ':
		++sCnt; break;
	case '\t':
		++tCnt; break;
	case '\n';
		++nCnt; break;
}
```

## Exercise 6.9

```cpp
switch (ch) {
	case 'a':
	case 'A':
		++aCnt; break;
	case 'e':
	case 'E':
		++eCnt; break;
	case 'i':
	case 'I':
		++iCnt; break;
	case 'o':
	case 'O':
		++oCnt; break;
	case 'u':
	case 'U':
		++uCnt; break;
	case ' ':
		++sCnt; break;
	case '\t':
		++tCnt; break;
	case '\n';
		++nCnt; break;
	case 'f':
		if (prev == 'f')
			++ffCnt;
		break;
	case 'l':
		if (prev == 'f')
			++flCnt;
		break;
	case 'i':
		if (prev == 'f')
			++fiCnt;
		break;
}
prev = ch;
```

## Exercise 6.10

```cpp
switch (ival) {
	case 'a': aCnt++; break;
	case 'e': eCnt++; break;
	default: iouCnt++;
}
```

```cpp
int ix;
switch (ival) {
	case 1:
		ix = get_value();
		ivec[ ix ] = ival;
		break;
	default:
		ix = ivec.size() - 1;
		ivec[ ix ] = ival;
		break;
}
```

```cpp
if(ival % 2)
	++oddCnt;
else
	++evenCnt;
```

```cpp
int ival = 512, jval = 1024, kval = 4096;
int bufSize;
// ...
if(swt == ival || swt = jval || swt = kval)
	bufSize = swt * sizeof(int);
```

## Exercise 6.11

```cpp
vector<int>::iterator iter = ivec.begin();
while (iter != ivec.end()) {
	++iter;
}
```

```cpp
while(!ptr) {
	ptr = find_a_value();
}

```

```cpp
bool status;
char *word = NULL;
while(word && status = find(word)) {
	word = get_next_word();
}
if (!status)
	cout << "Did not find any words\n";
```

## Exercise 6.12

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	int cnt = 0;
	string str, prev;
	while(cin >> str) {
		if (prev == "") prev = str;
		if (str == prev)
			++cnt;
		else if (cnt) {
			cout << prev << "occurred " << cnt << "time(s)" << endl;
			cnt = 0;
			prev = str;
		}
	}
}
```

## Exercise 6.13

```cpp
*dest++ = *source++;
//->
*dest = *source;
++dest; ++source; 
```

## Exercise 6.14

```cpp
for (int *ptr = &ia, ix = 0;
		ix != size && ptr != ia + size;
		++ix, ++ptr) {

}
```

```cpp
for (; ;) {
	if (some_condition) return;
	// ...
}
```

```cpp
int ix;
for (ix = 0; ix != sz; ++ix) {
	// ...
}
if (ix != sz)
	// ...
```

```cpp
int ix;
for (ix = 0; ix != sz; ++ix) {
	// ...
}
```

```cpp
for (int ix = 0; ix != sz; ++ix){
	//...
}
```

## Exercise 6.15

`While` loop, because while loop flexble.

## Exercise 6.16

```cpp
vector<int> vec1 = {0, 1, 1, 2};
vector<int> vec2 = {0, 1, 1, 2, 3, 5, 8};
vector<int>::iterator iter1 = vec1.begin();
vector<int>::iterator iter2 = vec2.begin();
while(iter1 != vec1.end() && iter2 != vec2.end())
	if(*iter1++ != *iter2++) return false;
return true;
```

## Exercise 6.18

```cpp
while(cin >> s1 >> s2) {
	cout << (s1 < s2 ? s1 : s2) << endl;
}
```

## Exercise 6.19

```cpp
vector<int>::iterator iter = vec.begin();
	while (iter != vec.end()) {
		if (value == *iter) {
			// continue processing
			break; // ok: found it!
		}
		else
			++iter; // not found: keep looking
	}// end of while
```

## Exercise 6.20

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string str, prev;
	while(cin >> str) {
		if (str == prev) {
			cout << str << endl;
			return 0;
		} else {
			prev = str;
		}
	}
	cout << "No word was repeated" << endl;
}
```

## Exercise 6.21

```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
	string str, prev;
	while(cin >> str) {
		if (str.front() < 'A' || str.front() > 'Z')
			continue;
		if (str == prev) {
			cout << str << endl;
			return 0;
		} else {
			prev = str;
		}
	}
	cout << "No word was repeated" << endl;
}
```

## Exercise 6.22

```cpp
while(int sz = get_size() <= 0)  {
	// ...
}
```

## Exercise 6.23

```cpp
#include <bitset>
using std::bitset;
int main() {
	bitset<1024> bits;
	bits.set(1023);
	bits.to_ulong();
}
```

## Exercise 6.24

```cpp
#include <bitset>
#include <stdexcept>
using namespace std;
int main() {
	bitset<1024> bits;
	bits.set(1023);
	try {
		unsigned long ul = bits.to_ulong();
	}
	catch (overflow_error err) {
		cout << err.what() << endl;
	}
}
```