# question 1


```python
def b(c):
    global a 
    a=c(a)
def c(a):
    return a+2
a=8
print('b(c)={}'.format(b(c)))
print('a is{}'.format(a))
```

    b(c)=None
    a is10
    

# question 2


```python
class Marsupial: # Defining a class Marsupial
    def _init_ (self):
        self.data = []
        
    def put_in_pouch(self,thing): # defining a function put_in_pouch
        self.data.append(thing) # storing the entered value in thing
        
    def pounch_contents(self):
        return self.data
    
class Kangaroo(Marsupial): #Defining a class Kangaroo
    def _init_(self,x,y):
        self.x = x
        self.y = y
        Marsupial._init_(self)
        
    def _str_ (self):
        return "I am a Kangaroo located at coordinates ({},{})".format(self.x,self.y)
    
    def jump(self,dx,dy):
        self.x += dx
        self.y += dy
        
        

```


```python
m = Marsupial()

m.put_in_pouch('doll')
m.put_in_pouch('firetruck')
m.put_in_pounch('kitten')

m.pouch_contents()

```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-47-f5d8b5588165> in <module>
          1 m = Marsupial()
          2 
    ----> 3 m.put_in_pouch('doll')
          4 m.put_in_pouch('firetruck')
          5 m.put_in_pounch('kitten')
    

    <ipython-input-2-feb088055c1e> in put_in_pouch(self, thing)
          4 
          5     def put_in_pouch(self,thing): # defining a function put_in_pouch
    ----> 6         self.data.append(thing) # storing the entered value in thing
          7 
          8     def pounch_contents(self):
    

    AttributeError: 'Marsupial' object has no attribute 'data'



```python
k = Kangaroo(0,0)
print(k)

k.put_in_pouch('doll')
k.put_in_pouch('firetruck')
k.put_in_pounch('kitten')

k.pouch_contents()

```


```python
k.jump(1,0)
k.jump(1,0)
k.jump(1,0)

print(k)
```

# Question 3


```python
def fileLength(str):
    try:
        def file_length(str):
             with open ('/Users/16476/Desktop/New Text Document.txt') as f: 
        
      
    # this line will help us to suto close the file
                file = open(str) # using try.method , we will try to open the file
                contents = file.read()
                file.close()
                print(len(contents))
    except:
        print('file ' + file_name + 'not found')
        
fileLength('/users/16476/Desktop/New Text Document.txt')
#or we can also use that variable f to use open, close functions of file outside the context manager
print(f.closed)  # return true cox outside the context manager the file will get closed automatically
# we have to reopen the file using the f variable
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-46-9d55068c268b> in <module>
         15 fileLength('/users/16476/Desktop/New Text Document.txt')
         16 #or we can also use that variable f to use open, close functions of file outside the context manager
    ---> 17 print(f.closed)  # return true cox outside the context manager the file will get closed automatically
         18 # we have to reopen the file using the f variable
    

    NameError: name 'f' is not defined


# Question 4



```python
def collatz(num):
    while num > 1:
        if num % 2 ==0:
            print(num//2)
            num = num //2
        elif num % 2 ==1:
            print(3*num+1)
            num = 3*num+1
        else:
            print(num)
def getNum():
    global num
    num = (input("> "))
    try:
        num = int(num)
    except valueError:
        print('please enter a number')
        getNum()
getNum()
collatz(num)
        
```

    > 10
    5
    16
    8
    4
    2
    1
    

# Question 5


```python
def binary(n):
    if n > 1 :
        binary(n//2)
    print(n % 2,end = '')
    
dec=int(input("Enter an integer: "))

binary(dec)
```

    Enter an integer: 9
    1001

# Question 6


```python
from html.parser import HTMLParser

class MyHTMLParser(HTMLParser):
    def handle_starttag(self, tag, attrs):
        print("infile= open ('w3c.html'):", tag)

    def handle_endtag(self, tag):
        print("hp.feed(content) :", tag)

    def handle_data(self, data):
        print("content= infile.read() :", data)
        print("hp = HeadingParser()")
        print("infile.close()")

parser = MyHTMLParser()
parser.feed('<hp>W3C Mission</hp>'
            '<h1>Principles</h1>')

```

    infile= open ('w3c.html'): hp
    content= infile.read() : W3C Mission
    hp = HeadingParser()
    infile.close()
    hp.feed(content) : hp
    infile= open ('w3c.html'): h1
    content= infile.read() : Principles
    hp = HeadingParser()
    infile.close()
    hp.feed(content) : h1
    

# question 7


```python
# import requests module 
import requests 
  
# Making a get request 
response = requests.get('http://reed.cs.depaul.edu/lperkovic/csc242/test1.html') 

  
# print response 
print(response) 
print('http://reed.cs.depaul.edu/lperkovic/csc242/test2.html')
print('http://reed.cs.depaul.edu/lperkovic/csc242/test3.html')

  
# print url 
print(response.url) 

```

    <Response [404]>
    http://reed.cs.depaul.edu/lperkovic/csc242/test2.html
    http://reed.cs.depaul.edu/lperkovic/csc242/test3.html
    http://reed.cs.depaul.edu/lperkovic/csc242/test1.html
    

# Question 8 



```python

import pandas as pd

data = {'City': ['Mumbai','Mumbai','Mumbai','Mumbai','London','London','London','London','Cairo','Cairo','Cairo','Cairo'],
        'Country': ['India','India','India','India','United Kingdom','United Kingdom','United Kingdom','United Kingdom','Egypt','Egypt','Egypt','Egypt'],
        'Season': ['Winter','Spring','Summer','Fall','Winter','Spring','Summer','Fall','Winter','Spring','Summer','Fall'],
        'Temperature': [24.8,28.4,27.9,27.6,4.2,8.3,15.7,10.4,13.6,20.7,27.7,22.2],
        'Rainfall': [5.9,16.2,1549.4,346.0,207.7,169.6,157.0,218.5,16.5,6.5,0.1,4.5]
        }

df = pd.DataFrame(data, columns = ['City','Country','Season','Temperature','Rainfall'], index = [1,2,3,4,5,6,7,8,9,10,11,12])

print(df)

```

          City         Country  Season  Temperature  Rainfall
    1   Mumbai           India  Winter         24.8       5.9
    2   Mumbai           India  Spring         28.4      16.2
    3   Mumbai           India  Summer         27.9    1549.4
    4   Mumbai           India    Fall         27.6     346.0
    5   London  United Kingdom  Winter          4.2     207.7
    6   London  United Kingdom  Spring          8.3     169.6
    7   London  United Kingdom  Summer         15.7     157.0
    8   London  United Kingdom    Fall         10.4     218.5
    9    Cairo           Egypt  Winter         13.6      16.5
    10   Cairo           Egypt  Spring         20.7       6.5
    11   Cairo           Egypt  Summer         27.7       0.1
    12   Cairo           Egypt    Fall         22.2       4.5
    


```python
import pandas as pd
data = {'Temperature': [24.8,28.4,27.9,27.6,4.2,8.3,15.7,10.4,13.6,20.7,27.7,22.2]
       }
df = pd.DataFrame(data,columns = ['Temperature'],index=[1,2,3,4,5,6,7,8,9,10,11,12])
print(df)
```

        Temperature
    1          24.8
    2          28.4
    3          27.9
    4          27.6
    5           4.2
    6           8.3
    7          15.7
    8          10.4
    9          13.6
    10         20.7
    11         27.7
    12         22.2
    


```python
import pandas as pd
data = {'City': ['Mumbai','London','Cairo']
       }
df = pd.DataFrame(data,columns = ['City'],index=[1,2,3])

print(df)
```

         City
    1  Mumbai
    2  London
    3   Cairo
    


```python
import pandas as pd 
data = {'City': ['Mumbai','Mumbai','Mumbai','Mumbai'],
        'Country': ['India','India','India','India'],
        'Season': ['Winter','Spring','Summer','Fall'],
        'Temperature': [24.8,28.4,27.9,27.6],
        'Rainfall': [5.9,16.2,1549.4,346.0]
       }

df = pd.DataFrame(data, columns = ['City','Country','Season','Temperature','Rainfall'], index = [1,2,3,4])

print(df)

```

         City Country  Season  Temperature  Rainfall
    1  Mumbai   India  Winter         24.8       5.9
    2  Mumbai   India  Spring         28.4      16.2
    3  Mumbai   India  Summer         27.9    1549.4
    4  Mumbai   India    Fall         27.6     346.0
    


```python
import pandas as pd 
data = { 'Rainfall': [5.9,16.2,1549.4,346.0,207.7,169.6,157.0,218.5,16.5,6.5,0.1,4.5]
       }
df = pd.DataFrame(data, columns = ['Rainfall'], index = [1,2,3,4,5,6,7,8,9,10,11,12])
print(df)
```

        Rainfall
    1        5.9
    2       16.2
    3     1549.4
    4      346.0
    5      207.7
    6      169.6
    7      157.0
    8      218.5
    9       16.5
    10       6.5
    11       0.1
    12       4.5
    


```python
import pandas as pd
data = {'City':['Mumbai','London','London'],
        'Country':['India','United Kingdom','United Kingdom'],
        'Season':['Fall','Winter','Fall'],
        'Rainfall':[346,207.7,218.5]
       }
df = pd.DataFrame(data, columns = ['City','Country','Season','Rainfall'], index = [1,2,3])
print(df)
```

         City         Country  Season  Rainfall
    1  Mumbai           India    Fall     346.0
    2  London  United Kingdom  Winter     207.7
    3  London  United Kingdom    Fall     218.5
    


```python
import pandas as pd
data = {'City': ['Mumbai','Mumbai','Mumbai','Mumbai','Cairo','Cairo','Cairo'],
        'Country': ['India','India','India','India','Egypt','Egypt','Egypt'],
        'Tempareture':[24.8,28.4,27.9,27.6,20.7,27.7,22.2]
       }
df = pd.DataFrame(data,columns = ['City','Country','Tempareture'],index = [1,2,3,4,5,6,7])
print(df)

```

         City Country  Tempareture
    1  Mumbai   India         24.8
    2  Mumbai   India         28.4
    3  Mumbai   India         27.9
    4  Mumbai   India         27.6
    5   Cairo   Egypt         20.7
    6   Cairo   Egypt         27.7
    7   Cairo   Egypt         22.2
    


```python
import pandas as pd 
data = {'Season':['Winter','Spring','Summer','Fall'],
        'Rainfall':[230.1,192.3,1706.5,569]
       }
df = pd.DataFrame(data,columns = ['Season','Rainfall'],index = [1,2,3,4])
print(df)
```

       Season  Rainfall
    1  Winter     230.1
    2  Spring     192.3
    3  Summer    1706.5
    4    Fall     569.0
    


```python
import pandas as pd 
data = {'City':['Cairo'],
        'Rainfall':[27.6]
       }
df = pd.DataFrame(data,columns = ['City','Rainfall'],index = [1])
print(df)
```

        City  Rainfall
    1  Cairo      27.6
    

# Question 9


```python
# python code of implementation
string = 'The quick brown fox jumps over the lazy dog'
print(string.upper())
```

    THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG
    


```python
# python code of implementation
string = 'The quick brown fox jumps over the lazy dog '
print(string.lower())
```

    the quick brown fox jumps over the lazy dog 
    


```python
st='the quick brown fox jumps over the lazy dog '.split()
c=[len(i) for i in st]
for i in range(len(c)):
    print(c)          
```

    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    [3, 5, 5, 3, 5, 4, 3, 4, 3]
    


```python
def long_words(n, str):
    word_len = []
    txt = str.split(" ")
    for x in txt:
        if len(x) > n:
            word_len.append(x)
    return word_len	
print(long_words(4, "The quick brown fox jumps over the lazy dog"))



```

    ['quick', 'brown', 'jumps']
    


```python

```
