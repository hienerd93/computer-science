# computer-science

## Why Program

* computer want to be helpful  
* programers anticipate needs  
* users and programers  
* why be a programer  
  * to get some task done - we are the user and programer  
  * to product something for others use - a programing job  
* what is code? software? a program?  
  * a sequence of stored instructions  
  * a piece of creative art  
* programs for humans  
* programs for Python

## Hardware Architecture

![Generic Computer](generic_computer.png)

> binary stream ~ programing language

## Python

> it is easier for you to learn Python than for the computer to learn English

![Computer Museum](computer_museum.png)

### Element

* Vocabulary/Words: Variable Operator Constant Reserved-Word  
* Sentence structure -> Interactive  
* Story structure -> Script

![Condition](condition.png)

![loop](loop.png)

![count word file](count_word_file.png)

## variables expressions and statements

> constants fixed values  
> variables name rule, mnemonic  
> operator precedence: parenthesis, power, multi, add, left->right  
> `type()`  
> float + int, division  
> `int()`, `float()`  
> `input()` return string  
> `#` comment

## Comparion

> Comparison < <= > >= == !=  
> Indentation 4 spaces, Begin/end block  
> One-way decision, two-way decisions, multi-way, nested.  

```py
if x < 2:
    print('Below 2')
elif x >= 2:
    print('Two or more')
else:
    print('Something else')
```

> danger code on `try` and `except`

![try-except](try_except.png)

## Function

> Stored (and reused) steps.

```py
def hello():
    print('hello')
hello()
```

> Built-in functions `min()`, `max()`  
> Function that we define ourselves  
> Arguments and Parameters
> Void function

```py
def greet(lang):
    if lang == 'es':
        return 'Hola'
    elif lang == 'vn':
        return 'Xin Chao'
    else:
        return 'Hello'
print(greet('vn'), 'Shine')
```

## Loop

![loop2](loop2.png)

```py
while True:
    line = input('> ')
    if line[0] == '#':
        continue
    if line == 'done':
        break
    print(line)
print('Done!')
```

> definite loops iterate through members of a set

```py
for n in [5,4,3,2,1]:
    print(n)
```

```py
largest_so_far = -1
print('Before', largest_so_far)
for num in [9, 41, 12, 3, 74, 15]:
    if num > largest_so_far:
        largest_so_far = num
    print(largest_so_far, num)
print('After', largest_so_far)
```

> Count, Total, Average, Find  
> `is` and `is not`

## String

> `+` concat
> square brackets
> `len()`

```py
fruit = 'banana'
for letter in fruit:
    print(letter)
```

```py
s = 'Monty Python'
print(s[3:8])
'M' in s
```

> `dir()`: `lower`, `upper`, `find`, `replace`, `lstrip`, `rstrip`, `strip`, `startswith`  
> all string is Unicode

## Reading Files

```py
handle = open(filename, mode)
```

> return a handle(TextIOWrapper) use manipulate the file, mode `r` and `w`
> newline `\n`

```py
fname = input('> Enter the file name: ')
try
    fhand = open(filename)
except
    print('Fine cannot open')
    quit()

content = fhand.read()
for line in fhand:
    line = line.rstrip()
    if line.startswith('From'):
        print(line)    
```

## List

> Programing: Algorithms and Data Structures  
> Strings are immutable, Lists are mutable  
> `range(4)`  
> `+` concat and slice like the strings

```py
stuff = list()
```

![split](split.png)

```py
fhand = open(filename)
for line in fhand:
    line = line.rstrip()
    if not line.startswith('From') : continue
    words = line.split()
    print(works[2])
```

## Dictionary

> Dictionary: label and List: order  

```py
counts = dict()
names = ['csev', 'cwen', 'csev', 'zquian', 'cwen']
for name in names:
    counts[name] = counts.get(name, 0) + 1
print(counts)
```

> `keys()`, `values()`, `items()`

![count](count.png)

## Tuple

```py
l = list()
t = tuple()
(x, y) = (7, 'fred')
for (k,v) in d.items():
    print(k, v)
t = d.items()
```

> Compare Tuple

```py
t = sorted(d.items())

temp = list()
for (k,v) in d.items():
    temp.append((v, k))
temp = sorted(temp)
```

![top10word](top10word.png)

```py
print(sorted([(v, k) in for k, v in d.items()]))
```

## Regular Expression

![regex](regex.png)

```py
import re
```

> `re.search()`, `re.findall()`

![x-spam](x-spam.png)

## Network

![tcp](tcp.png)

> TCP: Transport Control Protocol
> HTTP: HyperText Transper Protocol

> Protocol: A set of rules that all parties follow so we can predict each other's behavior  
> And not bump into each other

![telnet](telnet.png)

```py
import socket

mysock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
mysock.connect(('data.pr4e.org', 80))
cmd = 'GET http://data.pr4e.org/romeo.txt HTTP/1.0\n\n'.encode()
mysock.send(cmd)

while True:
    data = mysock.recv(512)
    if (len(data) < 1):
        break
    print(data.decode())
mysock.close()
```

## Text Process

> ASCII: 1 character, 8 bits, 1 byte; `ord()`, total 256  
> Unicode: > 10^9 character  
> UTF-8 1-4 byte recommended, UTF-16 Fixed length, UTF-32 Fixed length  
> string.encode and bytes.decode

## Urllib

```py
import urllib.request, urllib.parse, urllib.error

counts = dict()
fhand = urllib.request.urlopen('http://data.pr4e.org/romeo.txt')
for line in fhand:
    words = line.decode().split()
    for word in words:
        counts[word] = counts.get(word, 0) + 1
print(counts)
```

## Web scraping

> Support to pull data from web  
> Beautiful Soup `http://www.py4e.com/code3/bs4.zip`

```py
import urllib.request, urllib.parse, urllib.error
from bs4 import BeautifulSoup

url = input('Enter - ')
html = urllib.request.urlopen(url).read()
soup = BeautifulSoup(html, 'html.parser')

tags = soup('a')
for tag in tags:
    print(tag.get('href', None))
```

## XML and JSON

> Python Dictionary -> Serialize -> JSON, XML -> De-Serialize -> JavaHashMap  
> XML: Start-End Tag, Text Content, Attribute, Self Closing Tag  
> XML as Tree like DOM

> XML Document + XML Schema Contract = XML Validator

> XSD Structure

```xml
<xs:complexType name="person">
    <xs:sequence>
        <xs:element name="lastname" type="xs:string" />
        <xs:element name="age" type="xs:integer" />
        <xs:element name="dateborn" type="xs:date" />
        <xs:element name="country">
            <xs:simpleType>
                <xs:restriction base="xs:string">
                    <xs:enumeration value="FR" />
                    <xs:enumeration value="US" />
                </xs:restriction>
            </xs:simpleType>
        </xs:element>
    </xs:sequence>
</xs:complexType>
```

```py
import xml.etree.ElementTree as ET
data = '''<person>
    <name>Chuck</name>
    <phone type="intl">
        +1 734 303 4456
    </phone>
    <email hide="yes"/>
</person>'''

input = '''<stuff>
    <users>
        <user x="2">
            <id>001</id>
            <name>Chunk</name>
        </user>
        <user x="7">
            <id>009</id>
            <name>Shine</name>
        </user>
    </users>
</stuff>'''

tree = ET.fromstring(data)
print('Name:', tree.find('name').text)
print('Attr:', tree.find('email').get('hide'))
stuff = ET.fromstring(input)
lst = stuff.findall('users/user')
print('User count:', len(lst))
```

```py
import json
data = '''{
    "name": "Chuck",
    "phone": {
        "type": "intl"
        "number": "+1 734 303 4456"
    },
    "email": {
        "hide": "yes"
    }
}'''

info = json.loads(data)
```

> Json represents data as nested lists and dictionaries

## API

> Service Orient Approach(API)  
> Multi Systems
