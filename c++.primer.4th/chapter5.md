Chapter 5
=========

## Exercise 5.1

```cpp
#include <iostream>
int main() {
	int v1 = 12 / 3 * 4 + 5 * 15 + 24 % 4 / 2;
	int v2 = (12 / 3 * 4) + (5 * 15) + (24 % (4 / 2));
	std::cout << v1 << " " << v2 << std::endl;
}
```

## Exercise 5.2

```cpp
-30 * 3 + 21 / 5 //ok
-30 + 3 * 21 / 5 //ok
30 / 3 * 21 % 5 //ok
-30 / 3 * 21 % 4  //machine-dependent
```

## Exercise 5.3

```cpp
int x;
// ...
bool odd = x % 2;
```

## Exercise 5.4

> Others are undefined due to the nature of computerssuch as overflow, in which a value is computed that is too large for its type.

```cpp
unsigned char a = 256;
unsigned short b = 4000000;
int c = 1000000000;
```

## Exercise 5.5

> The logical AND and OR operators always evaluate their left operand before the right. The right operand is evaluated only if the left operand does not determine the result.

## Exercise 5.6

process characters in array, until incounter null character.

## Exercise 5.7

```cpp
#include <iostream>
using namespace std;
int main() {
	int v;
	while(cin >> v && v != 42);
}
```

## Exercise 5.8

```cpp
bool result = a > b && b > c && c > d;
```

## Exercise 5.9

```cpp
unsigned long ul1 = 3, ul2 = 7;
ul1 & ul2 // 11 & 111 = 3
ul1 && ul2 // true
ul1 | ul2 // 11 | 111 = 7
ul1 || ul2 // true
```

## Exercise 5.10

```cpp
snsigned int bit_set(unsigned long quizl, size_t pos) {
	return quizl | 1 << pos;
}

ussigned int bot_reset(unsigned long quizl, size_t pos) {
	return quizl & ~(1 << pos);
}
```

## Exercise 5.11

```cpp
int i; double d;
d = i = 3.5; // d: 3.0, i: 3
i = d = 3.5; // d: 3.5, i: 3
```

## Exercise 5.12

```cpp
if (42 = i) //error: lvalue required as left operand assignment
if (i = 42) //ok: equal if(42)
```

## Exercise 5.13

```cpp
double dval; int ival; int *pi;
dval = ival = pi = 0;

//->

double dval = .0; int ival = 0; int *pi = NULL;
```

## Exercise 5.14

```cpp
if (ptr = retrieve_pointer() != 0) //ok
if (ival = 1024) //if(ival == 1024)
ival += ival + 1 //ok
```

## Exercise 5.15

> The postfix versions of these operators increment(or decrement) the operand but yield a copy of the original, unchanged value as its result

> The prefix version returns the incremented value, it returns the object itself as an lvalue. The postfix versions return an rvalue.

## Exercise 5.16


## Exercise 5.17

Will cause the first element to be ignored.

## Exercise 5.18

```cpp
vector<string> vec;
//...
vector<string>::ieterator iter;
for(iter = vec.begin(); iter != vec.end(); ++iter) {
	cout << *iter << endl;
	cout << iter->length() << endl;
}
```

## Exercise 5.19

```cpp
*iter++; //yield *iter && iter++
(*iter)++ //illegal
*iter.empty() //illegal
iter->empty() //string::empty()
++*iter //illegal
iter++->empty() //string::empty()
```

## Exercise 5.20

```cpp
#include <iostream>
using namespace std;
int main() {
	int v1, v2;
	cout << "Enter two numbers: ";
	cin >> v1 >> v2;
	if(v1 < v2) cout << v1 << " is smaller";
	if(v2 < v1) cout << v2 << " is smaller";
}
```

## Exercise 5.21

```cpp
#include <vector>
using std::vector;
int main() {
	vector<int> vec = {1 ,2, 3, 4};
	vector<int>::iterator iter;
	for(iter = vec.begin(); iter != vec.end(); ++iter)
		if(*iter && *iter % 2)
			*iter *= 2;
}
```

## Exercise 5.22

```cpp
#include <iostream>
using namespace std;
int main() {
	cout << "sizeof(char):\t" << sizeof(char) << endl;
	cout << "sizeof(short):\t" << sizeof(short) << endl;
	cout << "sizeof(int):\t" << sizeof(int) << endl;
	cout << "sizeof(long):\t" << sizeof(long) << endl;
	cout << "sizeof(float):\t" << sizeof(float) << endl;
	cout << "sizeof(double):\t" << sizeof(double) << endl;
}
```

## Exercise 5.23

```cpp
#include <iostream>
using namespace std;
int main() {
	int x[10]; int *p = x;
	cout << sizeof(x)/sizeof(*x) << endl;
	cout << sizeof(p)/sizeof(*p) << endl;
}
```

## Exercise 5.25

```cpp
! ptr == ptr->next
//(! ptr) == (ptr->next)
ch = buf[ bp++ ] != '\n'
//ch = (buf[ bp++ ] != '\n')
```

## Exercise 5.26

```cpp
!(ptr == ptr->next)
(ch = buf[ bp++ ]) != '\n'
```

## Exercise 5.27

```cpp
string s = "word";
string p1 = s + ((s[s.size() - 1] == 's') ? "" : "s");
```

## Exercise 5.29

```cpp
ptr->ival != 0 //ok
ival != jval < kval //ok
ptr != 0 && *ptr++ //ok
ival++ && ival //ok
vec[ival++] <= vec[ival] //ok
```

## Exercise 5.30

```cpp
vector<string> svec(10); //ok
vector<string> *pvece1 = new vector<string>(10); //ok
vector<string> *pv1 = &sevc; //ok
vector<string> *pv2 = pvec1; //ok

delete svec; //error: svec is not a dynamic object
delete pvec1; //ok
delete [] pvec2; //ok
delete pv1; //error: pv1 refers to a local
delete pv2; //error: pv2 refers to a local
```

## Exercise 5.31

```cpp
if(fval)
dval = fval + ival; //ival converted to float, (fval + ival) converted to double
dval + ival + cval; //cval converted to double, ival converted to double
```

## Exercise 5.32

```cpp
char cval; int ival; unsigned int ui;
float fval; double dval;
cval = 'a' + 3;
fval = ui - ival * 1.0;
dval = ui * fval; //float converted to double
cval = ival + fval + dval; //double converted to char
```

## Exercise 5.33

```cpp
int ival; double dval;
const string *ps; char *pc; void *pv;
pv = (void *)ps; //pv = static_cast<void *>(ps);
ival = int(*pc); //ival = static_cast<int>(*pc);
pv = static_cast<void *>(&dval);
pc = (char *)pv; //pc = static_cast<char *>(pv);
```