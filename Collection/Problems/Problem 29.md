## Problem 29
***Asked by Amazon.***
### Task
**[Run-length Encoding](https://stackabuse.com/run-length-encoding/) is a fast and simple method of encoding strings. The basic idea is to represent repeated successive characters as a single count and character. For example, the string "AAAABBBCCDAA" would be encoded as "4A3B2C1D2A".**

**Implement run-length encoding and decoding. You can assume the string to be encoded have no digits and consists solely of alphabetic characters. You can assume the string to be decoded is valid.**
>**First and only line of Input contains a string, which is to be Encoded.**
### Sample input
**AAAABBBCCDAA**
### Sample Output
**Encoded: 4A3B2C1D2A**   
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

```cpp
#include <iostream>
#include <string>
using namespace std;

string Decoding(const string &s) {
    int count = 0;
    string result;
    for (const char &c: s) {
        if (isdigit(c)) {
            count = c - '0';
        }
        else {
            result.append(count, c); 
            /* appends count copies of c to result */
            count = 0;
        }
    }
    return result;
}

string Encoding(const string &s) {
    string result;
    int count = 0;
    for (int i=0; i <= s.size(); ++i) {
        if (i == s.size() || (s[i] != s[i-1] && i > 0)) {
            /* new character found, write count of previous character to result */
            result += to_string(count) + s[i-1];
            count = 1;
        }
        else {
            /* current character is same as its previous */
            ++count;
        }
    }
    return result;
}

int main() {
    string s;
    cin>>s;
    cout<<"Encoded: "<<Encoding(s)<<endl;
    cout<<"Decoded: "<<Decoding(s)<<endl;
    return 0;
}
```

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
