## Python 小科普

#### 變數
    標示符 => 自定義變量名稱 ，不可以數字開頭
    變量 => 儲存數據 => 容器
    變量可變 => 可重新賦值 => 每個變量都必須被賦值
    常量固定 => 不可被重新賦值 => 在python中沒有嚴格意義
    通常會將常量的標示符所有的字母全部大寫，當變量名字全部都大寫，標示符默認是一個常量，且不可修改數值。
    
    
```python=
#python無須指定變量類型
 price = 68.4 # float
 count = 2 # int 
 name = "meow" #str  '' "" "" """ """ 引號中的內容 都是字符串類型
 on_sale = True # 未知兩種結果 True / False bool
 
#通過type()查看變量類型
print(type(price))

#查看python已定義關鍵字，變數命名不可跟關鍵字重名
import keyword
print(keyword.kwlist) # 輸出關鍵字列表

['False', 'None', 'True', '__peg_parser__', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 
'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']

print(len(keyword.kwlist)) # 36

```

**變量輸出**

```python=
print("meow")
name = "ME"
age = 87
gender = 'boy'
print(name, age, gender) # Me 87 boy
print(name, age, gender,sep="") # Me87boy
print(name, age, gender,sep="*") # Me*87*boy
print(name, age, gender, sep="*", end="\n") #\n是跳行 , end="" 這樣的話不會換行輸出 

print("meow: \" I want eat some food! \"") # meow: " I want eat some food "
print('meow: \" I want eat some food! \"') #單雙引號嵌套使用  meow: " I want eat some food "
``` 
    
**字串拼接**   
```python=
a = "老"
b = "王"
c = 5487
print(a+b)
print(a*5) # 老老老老老
#print(a-b) #字串之間不可用 - 進行操作

# 格式化輸出 %s %d %f 輸出一個% => %%
# 站位符
print("你好! %s %s %s" % (a,b,c)) #你好! 老 王 5487 (這裡會將int強制轉成string)
```
**型態**
```python=
number_1 = 1234 #當我們想要輸出001234時...
print("我的學號是: %06d" % number_1) # %06d 輸出的十進制整數位6位,不足的位補0
score = 59.5
print("我期末英語成績 : %f" % score) # %f表示一個符點數，默認小數後面有6位 59.500000
print("我期末英語成績 : %.2f" % score) #只想小數後留2位 59.50

# 定義一個小數scale = 0.2, 輸出: 數據比例是20.00%
scale = 0.2
print("數據比例是: %.2f%%" % (scale*100))#數據比例是: 20.00% #scale*100 要加括號 否則 會把前面的話 輸出100遍 %%表示輸出一個%

```

**format**
```python=
name = "meow"
gender = '女'
age = 18

print("姓名: %s, 性別: %s:, 年齡: %d" %  (name,gender,age))

#{}不帶編號
print("姓名: {} ,性別: {} ,年齡: {}".format(name,gender,age))

#{1}{2}有數字標號的
print("姓名: {} , 性別:{},年齡: {}, 姓名是啥來著{}".format(name,gender,age,name))
#編號以0開頭 有了數字以後，變量就可以被反覆使用
print("姓名: {0} , 性別:{1},年齡: {2}, 姓名是啥來著{0}".format(name,gender,age,name))#姓名: meow , 性別:女,年齡: 18, 姓名是啥來著meow

#用數字標號表示會出現順序上的問題
#可以使用標示名稱的方式
print("姓名: {meow} , 性別:{xingbie},年齡: {age}, 姓名是啥來著{meow}".format(meow=name,xingbie=gender,age=age)) #姓名: meow , 性別:女,年齡: 18, 姓名是啥來著meow

#定義整數變量 student_no,輸出:我的學號000004
student_no = 4
print("我的學號: %06d" % student_no)
print("我的學號: {:06d}".format(student_no)) #我的學號: 000004

#定義小數price,weight,money, 輸出 : 波羅單價9.00元/斤,購買了5.00斤,需要支付45.00元9.00
price = 9.00
weight = 5.00
money = 45.00

print("波羅單價%.2f元/斤,購買了%.2f斤,需要支付%.2f元" % (price,weight,money))
print("波羅單價{:.2f}元/斤,購買{:.2f}斤,需要支付{:.2f}元".format(price, weight, money)) #波羅單價9.00元/斤,購買5.00斤,需要支付45.00元

# 定義一個小數scale = 0.2, 輸出: 數據比例是20.00%
scale = 0.2
print("數據比例是{:.2f}%".format(scale*100)) #數據比例是20.00%

```

**輸入**
```python=
# input 默認沒有提示語句
name = input()
print(name)

#給了提示語句會被打印出來，不會自動換行
name = input("輸入名字 :　")　＃把鍵盤輸入的str賦值給name
print(name)

#input語句接收的內容是以字串形式存在的
#類型轉換
int(x) #將x轉換為整數
float(x) #將x轉換為符點數
```

**項目演練**
```python=
#遊戲:被鵝追
#輸入玩家名稱:
#輸入密碼:
#輸入充值帳號:
print("被鵝追")
name = input("輸入玩家名稱: ") # 輸入玩家名稱: meow
passwd = input("輸入密碼: ")

print("%s 請充值才可加入遊戲! " % name) # meow 請充值才可加入遊戲! 
coins = input("輸入充值金額: ") # 輸入充值金額: 1000
coins = int(coins)#類型轉換
print("%s充值成功! 當前儲了:%d,請開始遊戲!" %(name,coins)) #meow充值成功! 當前儲了:1000,請開始遊戲!

#遊戲:英雄聯盟
#輸入角色
#輸入擁有裝備
#輸入想購買裝備
#輸入金額
print("英雄聯盟")
role = input("輸入角色: ")
equiment = input("輸入擁有裝備:　")
print("{}當前擁有{}".format(role,equiment))
upgrade_equiment = input("輸入想購買裝備: ")
pay = input("請輸入金額: ")
equiment = upgrade_equiment

print("{}擁有{},此裝備花了{}".format(role,equiment,pay))
```

**內存地址**
```python=
n = "meow"
s = n
print(n)

#每次運行都是不一樣的內存地址，但n跟s都會一樣的地址值，指向同個內存位置
print(id(n)) #2014419339760
print(id(s)) #2014419339760


n = "meow"
s = n
print(id(n)) #s = "meow" 1923566382832

n = "nomeow"
#n在內存中另外開了一個位址
print(id(n)) #n = "nomeow" 1923566382576
print(id(s)) #s = "meow" 1923566382832

#使地址反覆使用多次
money = 10
money1 = 10
print(id(money)) #1750925470288
print(id(money1)) #1750925470288

#但交互式interpreter時會因為數值過大而內存就會另開空間
meow = 1000000
meow1 = 1000000
print(id(meow))
print(id(meow1))

#使用交互式interpreter 開闢空間的方式 分為小整數和大整數空間
#使用小整數時會使用地址的覆用(-5~257)，大整數會重新開闢空間
```

**運算符**
```python=
# % ->取餘數
# // ->取商整數
#()中的運算符有最高優先權，再來是** > * > / > % > // > + > -

# 使用關係運算符的表達式最終返回一個 bool 型的結果 true False
a = 10000
b = 10000
a == b
>>　true　＃表示ａ、ｂ值相同

ａ is b #判斷a、b地址是否相同 is是身分運算符，用於判斷兩變量id
>> false

n1 = 8
n2 = 5 
n3 = 3
result = n1 >= (n2 + n3) and n1 > n2 #true and true => true

n2 += n3 #n2 = n2+n3 =>8
result = n1 >= n2 and n1 == n3 #true and false => false

n4 = (n1 + n3) - n2 #(8 + 3) - 8 =>3
result = n4 < n1 and (n4 + n3) > n2 #true and false => false


```
