## Problem 29
***Asked by Amazon.***
### Task
**[Run-length Encoding](https://stackabuse.com/run-length-encoding/) is a fast and simple method of encoding strings. The basic idea is to represent repeated successive characters as a single count and character. For example, the string "AAAABBBCCDAA" would be encoded as "4A3B2C1D2A".**

**Implement run-length encoding and decoding. You can assume the string to be encoded have no digits and consists solely of alphabetic characters. You can assume the string to be decoded is valid.**
>**First and only line of Input contains a string, which is to be Encoded.**
### Sample input
**AAAABBBCCDAA**
### Sample Output
**Encoded:  4A3B2C1D2A**   
**Decoded: AAAABBBCCDAA**

### Solution | Python
```python
string = input()
encode = ''
i = 0

while i < len(string):
  count = 1
  while (i < len(string) - 1) and string[i] == string[i+1]:
    count += 1
    i += 1
  encode += str(count)
  encode += string[i]
  i += 1

print(f"Encoded: {encode}")

decode = "".join([int(encode[i])*encode[i+1] for i in range(0, len(encode), 2)])
print(f"Decoded: {decode}")
```
### Solution | C++

>***Note: C++ solution is only for ENCODING a string.***
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
  string message, encoded, decoded;
  int count, i = 0;
  cin>>message;
  while (i < message.size()) {
    count = 1;
    while (i < (message.size()-1) && message[i] == message[i+1]) {
      count += 1;
      i += 1;
    }
    encoded += to_string(count);
    encoded += message[i];
    i += 1;
  }
  cout<<"Encoded: "<<encoded;
  return 0;
}
```

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
