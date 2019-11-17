# 基礎語法

## 本地環境安裝

### Python版本

根據工具選擇，如果都行就選最新版本。另外請選擇64位元版本

[Python 3.7.4](https://www.python.org/downloads/release/python-374/)

### IDE

推薦 PyCharm，使用 Python 標準環境

[PyCharm全版本](https://www.jetbrains.com/pycharm/download/other.html)

建議安裝 2018.2 版本，支援 jupyter notebook 的使用

## 線上環境

[Repl.it](https://repl.it)

## 變數的創造

我們列出和傳統語言的不同點

### 不需要強制型別

```python
a = 3
```

### 隨時可以更換背後的資料型態

```python
a = 3
a = "hello"
```

## 數字操作

### 基本操作


重要運算 | 效果 | 例子 | 注意事項
-----|-----|-----|--------
 //  | 取商 | 5 // 2 | 結果必定為整數
 %   | 取餘數 | 5 % 2  | 結果一定是小於除數的正數
 `**`   | 次方 | 5 \*\* 2 | 
 ==  | 相等 | 2 == 2 | 記得是兩個=符號
int(小數/字串) | 換成整數 |  int(5.2) |
ord(字串) | 將字母換成十進位編碼 | ord("A") | A(65)-Z(90) a(97)-z(122)
chr(整數) | 將十進位編碼換成字母 | chr(66) |
bin(十進位數) | 將數字換成二進位 | bin(4) |
oct(十進位數) | 將數字換成八進位 | oct(10) |
hex(十進位數) | 將數字換成十六進位 | hex(25) |
int(字串, 進位) | 將指定的進位換成十進位 |  int("100", 2) |
abs(數字) | 絕對值 | abs(-2.4) |


```python
print("取商:", 5 // 2)
print("取餘:", 5 % 2)
print("次方:", 5 ** 2)
print("相等:", 2 == 2)
print("取整數:", int(5.2))
print("換成編碼:", ord("A"))
print("換成字母:", chr(66))
print("二進位:", bin(4))
print("八進位:", oct(10))
print("十六進位:", hex(25))
print("轉換十進位:", int("100", 2))
print("絕對值:", abs(-2.4))
```

    取商: 2
    取餘: 1
    次方: 25
    相等: True
    取整數: 5
    換成編碼: 65
    換成字母: B
    二進位: 0b100
    八進位: 0o12
    十六進位: 0x19
    轉換十進位: 4
    絕對值: 2.4


### math函式庫

記得要import math

重要運算 | 效果 | 例子 | 注意事項
-----|-----|-----|--------
math.ceil(數字) | 取大於數字的最小整數 | math.ceil(2.4) |  
math.floor(數字) | 取小於數字的最大整數 | math.floor(2.4) |
math.factorial(整數) | 取階乘 3! = 3 x 2 x 1 | math.factorial(3) |
math.gcd(整數, 整數) | 取最大公因數 | math.gcd(6, 8) |


```python
import math
print("取天花板:", math.ceil(2.4))
print("取地板:", math.floor(2.4))
print("取階乘:", math.factorial(3))
print("最大公因數:", math.gcd(6, 8))
```

    取天花板: 3
    取地板: 2
    取階乘: 6
    最大公因數: 2


## 字串操作

### 基本操作

假設我們有個字串 

```python
a = "hello"
```
> 正向座號: h(0) e(1) l(2) l(3) o(4)

> 負向座號: o(-1) l(-2) l(-3) e(-4) h(-5)

重要運算 | 效果 | 例子 | 注意事項
-----|-----|-----|--------
\[座號\] | 取對應座號 | a\[2\]  |  
\[起始座號\:結束座號+1\] | 取一段子字串 | a\[2\:5\] | 第二個數字要記得多+1
\[起始座號:結束座號+1:幾個一跳\] | 跳號的方式取 | a\[2\:5\:2\]
\[::-1\] | 將整個字串反過來 | a\[\:\:-1\] | 
len(字串) | 算長度 | len(a) |
== | 相等 | a == "hello" |
in | 前面的字串是否是後面的部分 | "hel" in a |
`*` | 重複多次的新字串 | a \* 3 |


```python
a = "hellopython"
print("取第三個:", a[2])
print("取第三到第五個:", a[2:5])
print("跳號:", a[2:5:2])
print("反向:", a[::-1])
print("算長度:", len(a))
print("相等:", a == "hello")
print("一部分:", "hel" in a)
print("重複:", a * 3)
```

    取第三個: l
    取第三到第五個: llo
    跳號: lo
    反向: nohtypolleh
    算長度: 11
    相等: False
    一部分: True
    重複: hellopythonhellopythonhellopython


### 專屬功能


假設我們有個字串 a

重要運算 | 效果 | 例子 | 注意事項
-----|-----|-----|--------
.replace(舊, 新) | 全部取代 | a.replace("l", "o") |
.replace(舊, 新, 幾個) | 從左邊開始取代數個 | a.replace("l", "o", 1) |
.lower() | 轉換成小寫 | a.lower() |
.upper() | 轉換成大寫 | a.upper() |
.join(群集) | 將群集的東西用前面的字串組合 | "-".join(\["2019", "10", "16\] |
.split(字串) | 利用字串將前面的字串分割 | "2019-10-16".split("-") | 得到的結果是一個List
.startswith(字串) | 是不是由某個字串開頭 | a.startswith("hel") |
.endswith(字串) | 是不是由某個字串結尾 | a.endswith("lo") | 


```python
a = "Hello" * 3
print("完全取代:", a.replace("Hello", "bye"))
print("部分取代:", a.replace("Hello", "bye", 1))
print("轉換小寫:", a.lower())
print("轉換大寫:", a.upper())
print("組合:", "-".join(["2019", "10", "16"]))
print("分割:", "2019-10-16".split("-"))
print("是否是我要的開頭:", a.startswith("Hel"))
print("是否是我要的結尾:", a.endswith("lo"))
```

    完全取代: byebyebye
    部分取代: byeHelloHello
    轉換小寫: hellohellohello
    轉換大寫: HELLOHELLOHELLO
    組合: 2019-10-16
    分割: ['2019', '10', '16']
    是否是我要的開頭: True
    是否是我要的結尾: True




## List操作

List 拿來存放同類型的資料，基本上就是 Array，但差別在於 list 的長度是可變的

### 基本操作

重要運算 | 效果 | 例子 | 注意事項
-----|-----|-----|--------
 \+ | 合併兩個List | a + b | 兩個都必須是List 
`*`  | 把一個List重複多次 | a * 3 |
 == | 兩個List是否每個元素都相等 | a == b |
 in | 檢查元素是否有出現在List裡 | 3 in a | 
 len(群集) | 算長度 | len(a) |
 sorted(群集, reverse=True/False) | 排序 | sorted(a) | 會返回一個新的List, reverse可以控制升序(預設值)或者降序
 \[座號\] | 座號相關操作皆可使用 | list\[0\] |
 del | 刪除某個座號的東西 | del list\[0\] |


```python
a = [3, 1, 2]
b = [3, 1, 2]
print("合併:", a + b)
print("重複:", a * 3)
print("相等:", a == b)
print("是否在裡面:", 3 in a)
print("長度:", len(a))
print("排序:", sorted(a))
print("排序(反):", sorted(a, reverse=True))
print("反向:", a[::-1])
del b[0]
print("刪除後:", b)
```

    合併: [3, 1, 2, 3, 1, 2]
    重複: [3, 1, 2, 3, 1, 2, 3, 1, 2]
    相等: True
    是否在裡面: True
    長度: 3
    排序: [1, 2, 3]
    排序(反): [3, 2, 1]
    反向: [2, 1, 3]
    刪除後: [1, 2]


### 專屬功能

List的專屬功能都屬於沒有回傳答案的，直接修改 List

重要運算 | 效果 | 例子 | 注意事項
-----|-----|-----|--------
.append(元素) | 把東西加入最後 | list.append(3) | 
.pop() | 丟出最後的東西 | b = list.pop() | 有回傳值
.insert(位置, 元素) | 把東西插入在某個位置 | list.insert(0, "hello")
.remove(元素) | 刪除第一個遇到的元素 | list.remove("hello")
.reverse() | 反轉 | list.reverse() | 沒有回傳值
.sort() | 排序 | list.sort() | 沒有回傳值


```python
a = ["cat", "dog", "elephant"]
a.append("lion")
print("加到最後:", a)
b = a.pop()
print("丟掉最後:", a)
print("丟出東西:", b)
a.insert(1, "tiger")
print("加入到固定位置:", a)
a.remove("cat")
print("移除:", a)
a.reverse()
print("相反:", a)
a.sort()
print("排序:", a)
```

    加到最後: ['cat', 'dog', 'elephant', 'lion']
    丟掉最後: ['cat', 'dog', 'elephant']
    丟出東西: lion
    加入到固定位置: ['cat', 'tiger', 'dog', 'elephant']
    移除: ['tiger', 'dog', 'elephant']
    相反: ['elephant', 'dog', 'tiger']
    排序: ['dog', 'elephant', 'tiger']


### List 迴圈

使用 for 名字 in 群集

重要運算 | 效果 
-----|-----
enumerate(群集) | 會組合 (座號, 元素) tuple回傳 
zip(群集1, 群集2) | 會組合 (群集1元素, 群集2元素) tuple回傳



```python
a = ["cat", "lion", "dog"]
for e in a:
    print("標準迴圈:", e)

for i, e in enumerate(a):
    print("座號:", i, "物品:", e)
    
b = [20, 30 ,50]
for e1, e2 in zip(a, b):
    print("物品1:", e1, "物品2:", e2)
```

    標準迴圈: cat
    標準迴圈: lion
    標準迴圈: dog
    座號: 0 物品: cat
    座號: 1 物品: lion
    座號: 2 物品: dog
    物品1: cat 物品2: 20
    物品1: lion 物品2: 30
    物品1: dog 物品2: 50


## range 使用

使用 range 來達成固定次數的迴圈

使用方式1：range(5)會做出類似 \[0, 1, 2, 3, 4\]

使用方式2：range(2, 5)會做出類似 \[2, 3, 4\]



```python
result = 0
for i in range(10):
    result = result + (i + 1)
    print("目前累積:", result)
```

    目前累積: 1
    目前累積: 3
    目前累積: 6
    目前累積: 10
    目前累積: 15
    目前累積: 21
    目前累積: 28
    目前累積: 36
    目前累積: 45
    目前累積: 55


## Set 操作

Set是不重複的集合

重要運算 | 效果 | 例子 | 注意事項
-----|-----|-----|--------
 &   |  交集 | set1 & set2 |
 \|  | 聯集 | set1 \| set2 |   
 \-  | 差集 | set1 \- set2 |
 len(群集) | 算長度 | len(set1) |


```python
set1 = {3, 1, 2 ,5}
set2 = {6, 2, 1, 4}
print("交集:", set1 & set2)
print("聯集:", set1 | set2)
print("差集:", set1 - set2)
```

    交集: {1, 2}
    聯集: {1, 2, 3, 4, 5, 6}
    差集: {3, 5}


### 專屬功能


重要運算 | 效果 | 例子 | 注意事項
-----|-----|-----|--------
.add(元素) | 加入東西 | set1.add(3) 
.discard(元素) | 丟掉東西 | set1.discard(5)


```python
set1 = {3, 1, 2, 5}
set1.add(6)
print("加入東西後:", set1)
set1.discard(5)
print("丟掉東西後:", set1)
```

    加入東西後: {1, 2, 3, 5, 6}
    丟掉東西後: {1, 2, 3, 6}


## Dictionary 操作

字典拿來存放一個複雜資料

### 基本操作

字典是一個 {名字:值, 名字:值} 的集合

所有基本操作就是 字典名\[名字\]


```python
dict1 = {"name":"Elwing", 
         "height":175, 
         "weight":75}
dict1["height"] = dict1["height"] + 5
print("字典:", dict1)
```

    字典: {'name': 'Elwing', 'height': 180, 'weight': 75}


### 迴圈操作

字典的迴圈操作要特別說明一下，如果什麼都不寫是回傳 key

重要運算 | 效果 
-----|-----
.keys() | 只迴圈key
.values() | 只迴圈值 
.items() | 組合 (key, value) 的tuple




```python
dict1 = {"name":"Elwing", 
         "height":175, 
         "weight":75}

for k in dict1.keys():
    print("名字:", k)

for v in dict1.values():
    print("值:", v)
    
for k, v in dict1.items():
    print("名字:", k, "值:", v)
```

    名字: name
    名字: height
    名字: weight
    值: Elwing
    值: 175
    值: 75
    名字: name 值: Elwing
    名字: height 值: 175
    名字: weight 值: 75

## Tuple 操作

Tuple 是簡化版本的字典，不使用欄位名稱，直接使用位置，盡量別當成 List 使用

### 基本操作

Tuple 的語法 (第一個資料, 第二個資料)

```python
# 創造一個 tuple
person = ("Elwing", 175, 75)
# 兩個tuple相加, 注意tuple裡如果只有一個東西, 必須在最後放一個,
person = person + ("Taipei", )
# tuple支援所有的位置操作
print(person[-1])
# tuple內建不支援刪除操作, 因為python假定你只是在短暫的時間使用
# 但要做還是可以改用加法做(建議不要)
print(person[:2] + person[3:])
```
