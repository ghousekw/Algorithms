## How to define Good Code?

* We define good code based on two factors i.e.,
* Hum acha code 2 factors se define kartin
1. Readability
    - code padne layak hy ni phele woh check kartin.
2. Scalability
    - bole tho 2 main sub factors 
    1. Time complexity
        - Amount of time it takes to run an algorithm.
        - ek algorithm ku run hone kitna time lagta use ham time complexity se check kartin.
    2. Space/Memory complexity
        - Amount of extra space our algorithm requires.
        - ek alogirthm me kitna space consume hora ha hy woh check karne space complexity use kartin


## BigO Notation:
- agar hum ek problem dekhe uske multiple solutions rehtin,lekin usme kaunsa acha woh decide karne ke liye hum 2 factors(Readability & Scalability) use kartin.

- yeh sirf performance parameter(execution time yaan Space) ke jaise, joh apko help karega apne code base ko rate karne me.

Iske different rating terms hy code ko define karte jaise,
- Horrible
- Bad
- Fair
- Good 
- Excellent

## Why do we need  Big O?

- idar hum ek udaharan dekhenge, kyun hum calculate nahi karenge **time ko minute yaan seconds me**.

- har system ka alag configurataions rehti usse hamko alag alag execution time milta.

- Iske liye hum execution time/system time par dependent ny rehte, aur yahi karan hy Big O notation use karne ki wajah.

- Kitne **number of steps** me hum apna program run karsakte hy uss par **Big O** adarith rehta hy.

- Sidi si baat, Big O humko ek algorithm run hone me kitne time lagta hy woh answer deta hy.

---
## Big O(n):

![Sample demonstration of BigO](./images/BigOSample.png)

- Manlo ek problem ke do solutions hy aur **Solution A me 10 operations** lage, aur **Solution B ko 5 operations** lage run hone me, tho hum bolsakte hy **Solution B is better than Solution A**. Kyunki number of operations on solution B is less than solution A.

- Isse hum time complexity ko calculate karsaktin, kitne number of operations me hum apna algorithm run sakte hyn.

![Big O Chart](./images/BigOChart.png)

- **O(n)** jab operations me **Loops(for, while, etc.,)** rehtin use hum O(n) se denote kartin.

- **O(1)** , jab operations me constants rehtin use O(1) se denote kartin.

- X-Axis **Elements(Number of inputs)** jaise variable assignments and so.

- Y-Axis **Operations** bole tho number of operations jaise loops,condtions kitne baar run hua ho waise.

```Python

student_list1 = ["Raees", "Irfan", "Naseer"]

student_list2 = ["Irshad", "Sardar", "Rizwan", "Yunus"]

# idar student_list1 se ek input lete hy aur comparison opertion perform karte hyn aur usse **for loop** me rak kar daurate rehte hyn jabtak apna desired output se match nahi hota(isko hum operations bi bolte hyn)

# yeh function totally dependent hy number of input par, jaise 2 input milne par 2 operations, 3 milne par 3 operations waise.,
def checkStudent(student_list1):
    for student in student_list1: #time complexity is 0(n)
        if student == "Naseer":
            print(student)

# isse hum bolsakte hy hum 4 inputs diye hy aur 4 operations perform hua hy

# agar hum pattern dekho tho linear(straight) path bolsakte hyn.

checkStudent(student_list1)

# agar hum yeh problem ka conclusion bole tho, yeh problem follows linear(straight) path, so it is Big0(n)

# Here 'n' is the number of elements we have 
```

* Big0 yeh ek common pattern jo har problem me dekhne ko milega mostly.

### Agar number of inputs = number of operations, tab yeh follow karta hy linear path, so the complexity is Big0(n).
---
## Big0(1):

* Big0(1) sidi baat constant hy

Example code:
```python
student_list1 = ['areeb', 'irfan', 'raees', 'naseer']

def displayStudent(student_list1):
    print(student_list[0]) #time complexity is 0(1)
    print(student_list[1]) #time complexity is 0(1)

# halaki hamare list me 4 inputs hy lekin hum sirf ek baar operation run karenge.
# yahan hum input par dependent ny hy, hum sirf first element ko display kara rahe hy.

displayStudent(student_list)

# Hum ye code se bolsakte hy, yeh run hota hy constant time me, tho yeh Big0(1).

# kyun, the number of operations we are performing aur number of input we are depending is 1.

# Tho number of operations nahi depend hy input par, tho yeh code execute hoga constant amount of time par.

```

## Counting Operations:

* yahan par ek example leh kar analyze karenge Big0(n) aur Big0(1) ko calculate kar sakte hyn.

```python
# agar yeh wai line ke baare me baat kare tho, iska time complexity hoga Big0(1), kyunki idar sirf assigning kar rahe hy
colleagues = ["yaseen", "khaja", "jaseem", "ashraf","saad"] #0(1)

def randomFunction(colleagues):
    first = colleagues[0] #0(1)
    total = 0 #0(1)
    new_list = [] #0(1)

    # agar hum loop me chalegaya tho uska time complexity Big0(n) hoga, kyunki idar hum number of inputs lekar number of operations perform karenge.
    for colleague in colleagues: 
        total+=1 #0(n), kyunki yeh inputs per depend hy
        new_list.append(colleague) #0(n)
    
    print(new_list) #0(1)
    return total #0(1)

print(randomFunction(colleagues))
# agar hum pura time complexity calculate kare tho 0(1+1+1+1+1+1+n+n) => 0(6+2n) => 0(n)

```
---
## Simplifying Big 0:

* Hum upar ke example me dekhe 0(6+2n), waise hi dusre examples me 0(n+2n+5+n^2), 0(n^2+2n+6n) aur wagaira, wagaira...

* Tho humko samaj na hoga ise kaise simplify kare. Aur isse simplify karne ke liye 5 rules hy.

## Simplifying Big0(n^2):

* 0(n^2) isko quadratic equation kehte hyn.
* Jaise hamare pass 2 elements(input) hy 4 operations, 3 elements 9 operations wagaira, wagaira... isko hum 0(n^2) se denote karte hyn.

```python

num_list = [1,2,3,4,5,6,7,8,9] #0(1)

def randomFunction(num_list):

    totalCount = 0; #time complexity is 0(1)

    for num1 in num_list: #time complexity is 0(n^2)
        for num2 in num_list: #time complexity is 0(n^2)
            print(num1, num2)
            totalCount+=1
    return totalCount

print("Total number of operations performed is", randomFunction(num_list))

# Time complexity is 0(1+1+n^2+n^2) => 0(2+2n^2) => 0(n)
# As we have 9 elements here, so it will 81 operations.
# output: Total number of operations performed is 81

```
## 1. Rule: Focus on Scalabilty:
    * yahan per hamare inputs millions yaan infinity ke aur rahna chahiye. Manlo hum kaam kar rahe jaise ek big application yaan website me, tho usme millions of input rehtin.
    * Tho yahan dhyan yeh rakhna chahiye number of inputs jiyada ho aur number of operations kam ho.
 
## 2. Rule: Considering worst case scenario:

```python
students = ["raees","rafi","irfan","zain"]

def checkStudent(student_list):
    for student in students:
        if student == 'rafi':
# yahan par hala ki humko pata hy ki yeh 2nd position me hy, phir bi hum worst case scenario samaj te hy, jaise hamara input phele bi hosakta hy yaan phir aakhir bi hosakta hy.
# isliye isko Big0(n) kehte hyn.
            print('available')

checkStudent(students)
```
## 3. Rule 3: Remove all possible constants
    * (6+2n) => 0(n), isme hum constant 6 nikal denge kyunki hum inputs(n) millions me consider kare rahe hy, isliye small number millions ke samne chota hy.
    * Even app 0(2n) raha tho bi 0(n) hi consider karenge,
    usme kuch constant raha simple nikal denge.

## 4. Consider different variable for different inputs:
    
```python

# yahan par hamare pass different variable hy aur usme different inputs store karta hyn.

num_list = [1,2,3,4,5,6,7,8,9] #0(1)
char_list = [a,b,c,d,e,f,g] #0(1)

def randomFunction(num_list, char_list):
    for num in num_list: #time complexity is 0(n)
        print(num)
    
    for char in char_list: #time complexity is 0(m)
        print(char)

randomFunction(num_list, char_list) 
#time complexity is 0(n + m)

```
## 5. Remove all non-dominants:

* Agar apko time complexity calculate karne ke baad apko isa output mila 0(n+n^2), tho yahan 'n' remove kardiya jayega, kyunki n^2 is bigger than n. 


```python

num_list = [1,2,3,4,5,6,7,8,9] #0(1)

def randomFunction(num_list):

    totalCount = 0; #time complexity is 0(1)
    
    for num in num_list: #time complexity is 0(n)
        print(num)
    
    for num1 in num_list: #time complexity is 0(n^2)
        for num2 in num_list: #time complexity is 0(n^2)
            print(num1, num2)
            totalCount+=1
    return totalCount

print("Total number of operations performed is", randomFunction(num_list))

# Time Complexity is 
# 0(1+1+n+n^2+n^2) => 0(2+n+2n^2) => 0(n+ 2n^2) => 0(n^2)
```
---
## Big0(n!):

* matlab har ek input element ko nested loop add karna, joh ki na mumkin ke jaisa hy
* Aur isye cases apko rare or impossible, dekhne ko milega.

---
 
## Space Complexity:

* mane amount of space/memory ki jarurat hy ek algorithm ke life cycle me.

* isme 2 rakam ke space complexity rehte hyn
    1. jo input ko store karte hyn.
    2. extra space joh chahiye apne program to execute hone ke liye.

* in short, kitna additional memory hamko dena chahiye apne code ko run karne ke liye.

```python
# example 1:

items = [1,2,3,4,5,6]
# yeh ek input hy joh store karta hy apne items ko

def display_cube(items):
    result = pow(items[0],3) 
    # space complexity is 0(1), kyunki idar number of operations doesnt depend on number of inputs

# yeh ek additional memory space hy joh store karta hy temporary result variable ko, joh sirf execution time pe use hota hy apne result ko store karne me.
    return result

display_cube(items)

```


```python
# example 2:

items = [1,2,3,4,5,6]
# yeh ek input hy joh store karta hy apne items ko

result = []
# empty list to joh akhir me apne result to store karta hy

def all_cubes(items):
    for item in items:
        result.append(pow(item,3))
    # space complexity is 0(n), kyunki yahan number of operations depend on number of inputs.
    # Agar mere pass 6 elements(inputs) hy tho, mere pass 6 six different result hy, jo ki store karne ke liye.
    
    print(result)

all_cubes(items)

```

```python
# example 3:

items = [1,2,3,4,5,6]
# yeh ek input hy joh store karta hy apne items ko

def all_cubes(items):
    for item in items:
        result = pow(item,3) # 0(1)
    # space complexity is 0(1), kyunki yahan sirf ek variable(extra space) ko use karte hyn result ko store karne ke liye
    # Har ek iteration me, result variable override karta rehta hy, isse hamko sirf ek extra space chahiye joh ki store karne ke liye.

    print(result)

all_cubes(items)

# example 2 me hum empty list le kar har bar append karte hyn, joh ki har baar extra space use hota hyn.

```

## Summary:

![Big0 Summary](./images/Big0Summary1.png)

![Big0 Summary](./images/Big0Summary2.png)