

**變數**
+ 標示符 => 自定義變量名稱 ，不可以數字開頭
+ 變量 => 儲存數據 => 容器
+ 變量可變 => 可重新賦值 => 每個變量都必須被賦值
+ 常量固定 => 不可被重新賦值 => 在python中沒有嚴格意義
+ 通常會將常量的標示符所有的字母全部大寫，當變量名字全部都大寫，標示符默認是一個常量，且不可修改數值。

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

# if...else
a = 6
b = 5

#如果是true則將if前面的內容進行運算，並將結果賦值或成result
#如果是false則將else後面的內容進行運算，並將結果賦值或成result

result = (a + b) if a > b else (b - a)
print(result) #11

```
**條件判斷**
```mermaid

  flowchart  TD;
      A{要買東西?}-->|是|B[[先輸入密碼]]
      A-->|否|C[不買了沒錢了]
      B-->D{密碼對嗎?}
      D-->|對|E[進入購買頁面];
      D-->|不對|F[密碼錯誤請重新輸入!]
      F-->D
```
    if 搜索商品:
       先輸入密碼
       if 密碼正確:
          進入購買頁面
       else: 密碼錯誤，重新輸入密碼
    else: 不買了

```python=
#code 縮排為一個tab或四個空白鍵
#python規定: 判斷的變量是" "、0、 None默認是False，"meow"有值則認為是True

#登入頁面
username =  " " #默認表示False
if username != " ":
#if username: #username == False
    print("成功登入")
print("下次再來")

#小遊戲登入

print("*0"*10+"歡迎新玩家"+"*"*10)
level = input("請輸入當前級別(lv1、lv2)")
if level == "lv1":
    print("遊戲順利~")
else:
    print("請先充值")
    money = int(input("請充值: "))
    
    #再增加一個判斷:充值金額是否是50的倍數: 是:遊戲繼續 否:重新充值
    if money % 50 == 0:
        print("充值金額是{}元\n祝你遊戲愉快".format(money))
    else:
        print("重新充值，金額有誤")
       
#else: 猜數字
#產生一個隨機數
#鍵盤輸入一個數字
#將系統產生的數字和鍵盤輸入的數字做比較
#猜對了:中獎、猜錯了:掰掰下次再來

import random #亂數產生
run = random.randint(1,10) #產生1~10內的亂數
num = int(input("請輸入一個數字: "))

if num == run:
    print("猜中嘞")
else:
    print("猜錯嘞,再一次")
print("數字是{}".format(run))

#elif 多層條件判斷
考試成績評測
> 成績>=90 : A
> 90>成績>=80 : B
> 80>成績>=70 : C
> 70>成績>=60 : D
> 成績<60 :Ｅ

while True:
    score = input("輸入考試成績(1~100): ")
    test = int(score)
    if score.isdigit():
        if 0 < test <= 100:
            if test >= 90 and test >= 100:
                print("A")
                break
            elif test >= 80:
                print("B")
                break
            elif test >= 70:
                print("C")
                break
            elif test >= 60:
                print("D")
                break
            elif test < 60 and test >= 0:
                print("E")
                break
            else:
                print("請重新輸入正確數值")
                continue
        else:
            print("請輸入1~100內的分數")

```
    if 條件 1:
        #條件1滿足執行的代碼
        if 條件 1 基礎上的條件 2:
            ...#條件 2 滿足執行的代碼
        
        else: #條件 2 不滿足的處理
            條件 2 不滿足時，執行的代碼
    else: #條件 1 不滿足的處理
        條件 1 不滿足時，執行的代碼

**循環語句**
一般情況下，需要錯重複執行的code，都可以用循環的方式完成
(循環不是必要使用的，但是為了提高代碼的重複使用率，而使用)

```python=
for循環作為編程語言最強力的特徵之一
for循環較多用於次數可知情況下
python可以使用for語句循環遍歷整個序列的值

    關鍵字 元素 關鍵字 集合
    for   item  in    iterable:
        do something

range()函數 -> range(起始值 結束值,指定數字間隔)
該函數是python的內置函數，用於生成一系列連續的整數，大多用於for循環語句中
range(8) 起始值可以省略，默認從0開始 -->0,7 包前不包後，間隔可以省略，默認是1

#range(start, end, step= 1)
#range(start, end)
#range(end)

#range(0)是空集合

#打印三次hello

for i in range(3):  # 定義i，用於接收集合中的每一個元素，當接收一個元素時，就會執行一次
    '''
    i是一個變量 
    i = 0
    i = 1
    i = 2
    '''
    print("hello")  # 循環體


#小李超餓，要吃五個饅頭，顯示每次吃饅頭的過程，當小李吃完五個饅頭，顯示小李吃飽了

for i in range(1, 6):
    print("小李很餓，正在吃第{}個饅頭".format(i))
print("小李說:\"終於吃飽了\"")

'''
吃饅頭，在第三個饅頭上加了"砒霜"
當吃到了第三個饅頭的時候，提示:不要吃!有毒
'''
for i in range(1, 6):
    if i == 3:
        print("不要吃!有毒")
        break #結束循環，else內部語句就不會被輸出
    else:
        print("小李很餓，正在吃第{}個饅頭".format(i))
    
'''
用戶帳密登入只能登入三次，三次未成功則帳戶鎖定
輸入正確就進入後台
'''
for i in range(1, 4):
    inputlogin = input("請輸入帳號: ")
    inputpass = input("請輸入密碼: ")
    if inputpass == "admin" and inputlogin == "meow":
        print("成功登入")
        break
    else:
        print("請在輸入一次帳密")
else:
    print("帳號鎖定")
    
#pass空語句
if 10 > 7:
    print("結果正確!")

else:
   #正常來說如果這裡是空的，程序會報錯
    pass #不會做任何事情，相當於代碼的佔位，保證代碼結構的完整性，在語     法上也不會報錯
print("程序判斷成功")

#while較多用於次數未知情況下
while True: #True循環條件
    print("test")

#死循環 當循環條件一直為true，就會一直執行循環:並且沒有一個機制可以打破循環

#打印五遍meow
#1.定義重複次數計數器
i=0
#2.使用while判斷條件
while i < 5:
    #需要執行代碼
    print("meow")
    #處理計數器i
    i += 1
print("循環結束後的i = %d" % i )

# 不斷要求輸入學生姓名，輸入q結束
#以list()函數建立一個空的串列，然後透過append()方法函數把資料項目加到某一個指定的串列中。
allname = list() 
name = input("輸入名字: ")
while name != "q":
    allname.append(name)#append把指定的資料項加到串列的最後端
    name = input("輸入名字: ")
    if name == "q":
        print("程序結束")
print("您輸入的名字有:", allname)

#不斷要求用戶輸入一個數字，然後打印這個數字的兩倍，當用戶輸入q的時候程序退出

while True:
    num = input("輸入一個數字: ")
    if num == "q":
        print("程序結束")
        break
    print("您輸入的數字2倍是: %d" % (int(num)*2))

#打印1-30之間的所有3的倍數    
i = 1
while i <= 30:
    if i % 3 == 0:
        print(i)
    i += 1
    
#for 循環
for i in range(1, 31):
    if i % 3 == 0:
        print(i)
        
#水仙花數 自冪數 100-999 每個位的3次方，加起來還是他本身
# 153 = 1^3 + 5^3 + 3^3。
# 370 = 3^3 + 7^3 + 0^3。
# 371 = 3^3 + 7^3 + 1^3。
# 407 = 4^3 + 0^3 + 7^3。

#abc
#a = abc // 100
#b = (abc % 100) // 10
#c = abc % 10

i = 100
while i <= 999:
    ones = i % 10  # 個位
    tens = (i % 100) // 10  # 十位
    handreds = i // 100  # 百位

    if ones**3 + tens**3 + handreds**3 == i:
        print("水仙花數是: ", i)
    i += 1

#打印1-100的和
i = 1
result = 0  # 用來記錄算術和
while i <= 100:
    result = result + i  # 求和的累加
    i += 1

print("1-100之間的和是{}".format(result))

#不使用自符串拼接，在控制台連續輸出五行 "*",每一行 "*" 的數量一次遞增
'''
*
**
***
****
*****
'''
i = 0
while i < 5:
    i += 1
    print("*"*i)
#循環嵌套 外循環五次 內循環打印多少個 * 還要和外循環的次數相同
i = 1
while i <= 5:
    # 內循環
    j = 1
    while j <= i:
        print("*", end="")
        j += 1
    print("")  # 什麼都不打印，但要換行
    i += 1


#輸出99乘法表
i = 1
while i <= 9:
    # 內循環
    j = 1
    while j <= i:
        print("{}*{}={}".format(j, i, i * j), end="\t")
        j += 1
    print("")  # 什麼都不打印，但要換行
    i += 1

 ```
 ```mermaid
 flowchart LR
    a(i=1)-->b{i<=9}
    b-->|false|c(停止運行)
    b-->|true 進入內迴圈|d(j=1)
    direction BT
    d-->e{j<=1}
    e-->|true|f(輸出i*j且j+1)
    e-->|false|g(i+1)
    g-->|回到外迴圈繼續執行|b
 ```
 **字串**
```python=
string = "meow"
for i in string:  # string 集合
    print(i)
print(string[0])  # 字串第0位的英文
print(string.index("m"))#字串m在第幾位

s1 = 'abc'
s2 = "abc"
s3 = '''abc'''#單行字串 不用使用三對引號表示

#先比較三個字串的值
print(s1 == s2) #true
print(s2 == s3) #true
print(s1 == s3) #true
#比較id是否相同 通過自定義的字串 值相同的字串 他們id也是相同的
print(id(1))
print(id(2))
print(id(3))

str1 = input("請輸入信息: ") #輸入相同內容，比較兩個變量值和id是否相同
str2 = input("請輸入信息: ") #程序每遇到一個input輸入，都會在內存裡開一個空間
print(str1 == str2) #true
print(str1 is str2) #false
#當定義一個字串時 會在內存中開一個空間s1並指向那個空間 不過為了節約內存 會指向同個內存空間

#字串的運算符: in成員運算符
#沒連在一起的話就不是在集合中
#'ste' in name?
#'tv' in name?
name =  "steven"
result = 't' in name #返回值是bool 類型true false
print(result)#true

result = 'tv' not in name
print(result)#true

#切片
'''
         -->從左往右      從右往左<--
正索引   0  1  2  3  4  5  6  7  8  9
負索引 -10 -9 -8 -7 -6 -5 -4 -3 -2 -1
值       0  1  2  3  4  5  6  7  8  9
       起點                        終點 
'''
#語法: str[start:end:方向(+-)/間隔]
#切片使用索引值來限定範圍, 從一個大的字串中切出小的字串
#列表和元組都是有序的集合 能夠通過索引值獲取對應的數據
#字典是一個無序的集合 是使用鍵值對保存數據
#起始值:終止值 默認間隔為1


#取出字串中的文字
filename = 'picture.png'
print(filename[5])#r
#通過[]可以結合位置/(下標或索引)獲取字符,特點:只能獲取一個字母
filename = 'picture.png'
print(filename[0:5])#pictu 0是起始值 5是結束的值,但是不包括[5] 包前不包後
print(filename[3:5])#tu
print(filename[3:]) #ture.png 只要省略後面，表示取值一直取到字串的末尾 
print(filename[:7]) #picture 省略的是前面，從0開始取值，一直取到結束(不包含)

print(filename[:]) #picture.png省略了首尾，相當於取了整個字串

#集合有兩套 索引 起始或結束值出現負數的情況
print(filename[8:-1]) #pn -1是從右往左取
print(filename[:-2]) #picture.p 等價於 print(filename[:9])
print(filename[-8:]) #ture.png

#間隔 +- 1
print(filename[::]) #picture.png
print(filename[::-1])#gnp.erutcip 間隔的負號表示取值的方向

str1 = "abcdefg"
print(str[-1:-5]) #從後往前取值，但是取值的方向和間隔的方向不一致，導致不會輸出結果
print(str[-1:-5:-1]) #gfed


#大小寫切換
massage = "love meow meow"
msg = massage.capitalize()
print(msg)  # 首字大寫 Love meow meow

msg = massage.title()
print(msg)  # 每個單詞字母首位大寫 Love Meow Meow

result = msg.istitle()
print(result)  # 是否是title形式 True

msg = massage.upper()
print(msg)  # 每個字母大寫 LOVE 
msg = massage.lower()
print(msg) #全字母小寫 love meow meow

#根據系統提示輸入驗證碼，不用考慮大小寫
import random
s = 'QERTYUIOPASDFGHJKLZXCVBNMqwertyuiopasdfghjklzxcvbnm1234567890'
# print(len(s))  # 61
# print(s[1])
code = ""  # 來接受隨機生成的字串
for i in range(4):
    # random(0,61) 隨機取0~61中的字串值 len是從1開始所以要減1
    ran = random.randint(0, len(s) - 1)
    code += s[ran]  # code 使用 + 進行字串拼接 + s[隨機數]

print("驗證碼是: {}".format(code))

# 提示用戶輸入驗證碼(輸入時忽略大小寫)
userinput = input("請輸入驗證碼: ")
if userinput.lower() == code.lower():  # .lower忽略大小寫
    print("驗證碼正確")

else:
    print("驗證碼有誤")

#字符串內鍵函數查找,替換
#find() rfind() lfind() #查找
#replace #替換

#find(str, beg=0 ,end=len(string)) #find(要查找字串,start,end)
#檢測str是否包含在字串中，如果指定範圍beg和end，則檢查是否包含在指定範圍內，如果包含返回開始的索引值，否則返回-1
s1 = "lucky meow meow"
position = s1.find("R")  # 返回值是-1,則表示沒找到 -1
print(position)

position = s1.find("l")  # 可以找到，返回字母第一次出現的位置 0
print(position)

p = s1.find("l", position + 1, len(s1) - 5)  # 指定位置查找,position+1,表示再次在字串中尋找第2個"l" -1
print(p)

url = "https://www.meow.com/img/bd_logo1.png"
# 獲取最右邊"/"位置
p = url.rfind('/')
print(p) #24

# 獲取最右邊"/"文件名
filename = url[p + 1:]
print(filename)#bd_logo1.png

# 擷取擴展名
p = url.rfind(".")
kz = url[p+1:]
print(kz)#png

#replace(old,new[,max])
#將字串中的str1替換成str2,如果max指定,則替換不超過max次

s1 = "meow hacker lucky"
#將s1字串空格的部分替換#
s2 = s1.replace(" ","#")
print(s2)#meow#hacker#lucky

#去除s1中的空格
s2 = s1.replace(" ","")
print(s2)#meowhackerlucky

#字串編碼和判斷開頭結尾
#encode() 編碼
#encode(encoding='UTF-8',errors='strict')
'''
以encoding指定的編碼格式編碼字串
如果出錯默認報一個ValueError的異常，除非error指定的是'ignore'或'replace'
'''
msg = "我只會meow"
result = msg.encode(encoding="UTF-8")
print(result)
#b'\xe6\x88\x91\xe5\x8f\xaa\xe6\x9c\x83meow'

#解碼decode()
m = result.decode("utf-8")
print(m)#我只會meow


#判斷開頭結尾
#startswith()
#endswith()  #返回值都是bool類型true false
#startswith  #判斷是否以xx開頭，endswith判斷是否以xxx結尾

'''
給定一個路徑，上傳文件(記事本txt或是圖片jpg.png)
如果不是對應格式的，允許重新執行上傳文件
如果符合上傳的規定則提示上傳成功
'''
while True:
    path = input("選擇文件上傳: ")
#要上傳的文件路徑 -->文件名 -->通過文件名再判斷是否是圖片類型
    p = path.rfind("\\")
    filename = path[p + 1:] #通過切片，截取出來文件名
#判斷是否是圖片類型
    if filename.endswith("jpg") or filename.endswith("png") or filename.endswith("txt"):
        print("是圖片，上傳成功")
        break
    else:
        print("不是圖片格式和記事本格式，上傳錯誤")
    
# isalpha()是否是字母
# isdigit()是否是數字
s = "abcd"
result = s.isalpha()
print("result=", result)#result= True

s = "6688"
result = s.isdigit()
print(result)#True

#判斷輸入的是否是純數字，並計算出純數字的和
sum = 0
i = 1
while i <= 3:
    num = input("請輸入數字: ")
    if num.isdigit():
        num = int(num)
        sum += num
        print("第{}個數字累加成功! ".format(i))
        i += 1
    else:
        print("不是數字")
print("sum=", sum)

#join split count 字符串作為分隔符號，將seq中所有的元素(的字符串表示)合併為一個新的字串
"""
join(seq)以指定字串作為分隔符號，將seq中所有的元素(字串表示)合併為一個新的字串
"""
#將字串abc用_連接，構成一個新的字串
new_str = "_".join("abc")
print(new_str)#a_b_c

#去除字串的空格 strip lstrip rstrip
#split() 分割字串，將切割後的字串保存到列表中

#split 分割字串，將切割後的字串保存到列表中
"""
split(str="",num=string.count(str))
num=string.count(str) 以str為分隔符截取字串，如果num有指定值，則僅截取num+1個字串
"""
#split()分割字串，將切割後的字串保存到列表中
s = "hello meow no world"
result = s.split(" ")  # 遇到空格就切一刀，最後生成一個列表
print(result) #['hello', 'meow', 'no', 'world']

result = s.split(" ", 2)  # 按照接觸空格作為分割符號，分割字串2次
print(result) #['hello', 'meow', 'no world']

#n = s.count(" ") #count(args) 求字符串中指定args的個數
#print("個數",n)

#求字串's'的個數
s = "sakkytrvbofhplkjhctdtyikjhdfgsaqhfn"
n = s.count('s')
print(n)#2
```

**列表**
+ list 用於儲存一串訊息，同時定義多個同類型的變量
+ 列表用[]定義，數據之間用 , 分隔
+ 列表的索引從0開始
+ 從列表中取值時，如果超出索引範圍，就會報錯
num_list = [1,2,3,4,5,6,7,8,9]
當寫了上面一行代碼之後，就在內存中開了個連續的10塊空間
每一塊空間都稱為這個列表的元素

```python=
#              0       1       2
name_list = ["meow","haha","hacking"]
name_list[1] #haha
name_list[2] #hacking
name_list[3] 
'''
<ipython-input-4-ce8c9d9aa7dd> in <module>
----> 1 name_list[3]

IndexError: list index out of range
'''
'''
name_list = [] #空列表
name_list.insert(索引,數據) #在指定位置插入數據
name_list.append(數據) #在末尾追加數據
name_list.extend(列表2) #將列表2的數據追加到列表
name_list[索引] = 數據 #修改指定索引的數據
name_list.remove[數據] #刪除第一個出現的指定數據
name_list.pop #刪除末尾數據
name_list.pop(索引) #刪除指定索引數據
name_list.clear #清空列表
name_list.count(數據) #數據在列表衝出現的次數
name_list.sort() #升序排列
name_list.sort(reverse=True) #降序排列
name_list.reverse() #逆序、反轉
name_list.index
'''

name_list = ["meow", "haha", "hacking"]
print(name_list[0]) #meow
print(name_list.index("haha")) #1


#修改元素
name_list = ["meow", "haha", "hacking"]
name_list[1] = "hackmeow"
print(name_list) #['meow', 'hackmeow', 'hacking']

#增加數據 append(數據)/+ 會被追加到列表的末尾
name_list = ["meow", "haha", "hacking"]
name_list.append("lucky")
name_list.append("haha")#列表允許重複元素存在
result = name_list + ["NO"]
print(name_list) #['meow', 'haha', 'hacking', 'lucky']
print(result) #['meow', 'haha', 'hacking', 'lucky', 'NO']

#insert(索引,數據)
name_list = ["meow", "haha", "hacking"]
name_list.append("lucky")
name_list.append("haha") 
name_list.insert(2, "meowmeowQAQ")
print(name_list)#['meow', 'haha', 'meowmeowQAQ', 'hacking', 'lucky', 'haha']

#extend() 擴展 + 
name_list = ["meow", "haha", "hacking"]

name_list1 = ["小紅", "小白", "小黑"]
name_list.extend(name_list1)#['meow', 'haha', 'hacking', '小紅', '小白', '小黑']
result = name_list1 + name_list
print(name_list)  # ['meow', 'haha', 'hacking', '小紅', '小白', '小黑']
print(result)

# 移除列表中元素
print(name_list)  # ['meow', 'haha', 'hacking', '小紅', '小白', '小黑']
name_list.remove("meow")
print(name_list)  # ['haha', 'hacking', '小紅', '小白', '小黑']

# pop() 默認移除列表最後一個元素，()裡面加上元素的索引,來移除這個元素
name_list.pop()
print(name_list)  # ['haha', 'hacking', '小紅', '小白']
name_list.pop(0)
print(name_list)  # ['hacking', '小紅', '小白']

#len() 用來表示集合的長度/裡面有多少個元素 length
print(len(name_list)) #3

# del + 列表[索引值]
del name_list[0]
print(name_list) #['小紅', '小白']

# clear() 清除列表
name_list.clear()
print(name_list)  # []

#count() 統計元素出現的次數
num_list = [1, 0, 2, 3, 2, 4, 7, 5, 6, 3, 1, 7, 8, 9]
num_list = num_list.count(1)
print(num_list) # 2

#sort() 升序 由小而大排列
num_list = [1, 0, 2, 3, 2, 4, 7, 5, 6, 3, 1, 7, 8, 9]
num_list.sort()
print(num_list)  # [0, 1, 1, 2, 2, 3, 3, 4, 5, 6, 7, 7, 8, 9]

num_list.sort(reverse=False)
print(num_list)  # [0, 1, 1, 2, 2, 3, 3, 4, 5, 6, 7, 7, 8, 9]
num_list.sort(reverse=True)
#在升序的基礎上倒序
print(num_list) # [9, 8, 7, 7, 6, 5, 4, 3, 3, 2, 2, 1, 1, 0]

#reverse直接逆序輸出
num_list1 = [1, 6, 4, 8, 3, 2, 9, 2]
num_list1.reverse()
print(num_list1) # [2, 9, 2, 3, 8, 4, 6, 1]
```

**循環遍歷**
+ 從頭到尾一次從列表中獲取數據
+ 使用for就能實現迭代遍歷
```python=
#for 循環內部使用的變量 in 列表
name_list = ["meow", "haha", "hacking"]

for name in name_list:
    #循環內部針對使用的變量in列表
    print(name)
'''
meow
haha
hacking
'''
```

**Tuple(元組)**
+ 與列表類似，不同之處在於元組的元素不可修改
+ 表示多個元素組成的序列
+ 用於儲存一串信息，數據間使用 , 分離
+ 元組用()定義
+ 元組的索引從0開始
```python=
t1 = ()  # 定義空元組
print(type(t1))  # 查看元組類型 <class 'tuple'>

t1 = ("hello")
print(type(t1))  # <class 'str'>

#只有一個元素也要加 ,
t2 = ("hello", )  # 第一個元素的元組定義方式
print(type(t2))

t3 = ("aa", "bb")  # 多個元素的元組定義方式
t4 = (5, 6, 2, 7, 8, 3, 5, 2, 1, 0, 3, 5, 7)  # 元組的元素數據類型


#類型轉換
list_1 = []
tuple1 = tuple(list_1)#把列表轉換成元組

list_1 = list(tuple1)#把元組轉換列表

#tuple ，用小括號表示 。
#例如 (‘a’, ‘b’)。

score = ('A+',)
print(score) #('A+',)
print(type(score))  #<class 'tuple'>

#tuple屬於不可變的資料型態，不可變（Immutable）意思就是你不可以修改、增減tuple的值。也因為 tuple 不可變的特性，所以沒有append()、remove()、pop()等會更動值的操作。
#只含有一個項目時，要加上逗點當你要建立只有一個項目的 tuple，千萬要記得加上逗號，否則不會建立 tuple。
number = 1,
print(number) #(1,)




#取值 元組也是一個有序的集合
#查詢下標index來取值 切片的取值[::]
#關於元組的函數和方法
#函數: max() min() sum() len() 

#sorted() 元組能排序?
t5 = (6, 2, 3, 5, 8)
sorted(t5)
print(t5)#(6, 2, 3, 5, 8)
print(sorted(t5))#[2, 3, 5, 6, 8] 直接輸出排序操作，返回一個經過排序的
#res = sorted(t5) ==> res是一個元組元素經過排序的列表

#方法: .index() .count()

#元組數據類型轉換 ->列表轉元組
import random

list1 = []
for i in range(10):
    ran = random.randint(1, 20)
    list1.append(ran)  # 每次都在末尾追加數據
print(list1)  # [13, 18, 2, 6, 17, 20, 12, 15, 3, 14]

t5 = tuple(list1)
print(t5)  # (13, 18, 2, 6, 17, 20, 12, 15, 3, 14)

print(t5[0])  # 通過下標查看元組中元素的值 13
print(t5[-1])  # 14
print(t5[2:-3])  # (2, 6, 17, 20, 12) 通過切片取元組元素的值
print(t5[::-1])  # (14, 3, 15, 12, 20, 17, 6, 2, 18, 13) 倒序輸出
print(max(t5))  # 20
print(min(t5))  # 2

print(sum(t5))  # 求和 120
print(len(t5))  # 求元素個數 10

print(t5.count(4))  # 找出 4元素的個數 沒有不會報錯 0
print(t5.index(3))  # 找出元素中3的下標位置 沒有就報錯 8


# = 前面變量的個數和元組個數不一致的時候 可以進行拆包和裝包
#拆包與裝包-整形元素
#變量個數與元組個數不一致時
t1 = (2, 5, 7, 3, 1)
a, *_, c = t1  # 先讓固定變量接收元素, *_來接收剩下的元素，以列表的形式存在
print(a)  # 2 接收最前面的值
print(_)  # [5, 7, 3] 多值接收 去掉* 是一個裝包的過程
print(c)  # 1 接收最後值
print(*_)  # 5 7 3
print(a, _, c)  # 2 [5, 7, 3] 1
print(a, c, _)  # 2 1 [5, 7, 3]

a, c, *b = t1
print(a, b, c)  # 2 [7, 3, 1] 5

t1 = (9, )
a, *b = t1
print(a, b)#9 []
# *b表示未知個數 0~n , 0 -- [] 多個元素 -- [1,2,3,4,...]

#拆包與裝包-字串類型
x,y,*z = "hello"
print(x,y,z)#h e ['l', 'l', 'o']
print(*z)#l l o

#拆包與裝包-列表類型
x, y, *z = ['aa', 87, 'meme', 'haha', 4]
print(*z)#meme haha 4

#拆包適用於元組 字串 列表
#元組運算符: + * is in
t2 = (4, 5) + (1, 2)

t3 = (3, 4) * 2
print(t2)  # (4, 5, 1, 2)
print(t2 * 2) # (4, 5, 1, 2, 4, 5, 1, 2)

print(t3)  # (3, 4, 3, 4)

print(t2 is t3)#False兩個的地址不同
print(3 not in t3) #False

```
**字典**
+ 除列表之外python之中最靈活的數據類型
+ 可存儲多個數據
+ 列表是有序的對象集合
+ 字典是無序的對象集合
+ 字典用{}定義

```python=
dict1 = {} #定義一個空字典
dict2 = dict() #定義一個空字典
'''
字典使用鍵值對存儲數據 鍵值對之間使用 , 分隔
鍵 key 是索引
值 value 是數據
鍵 和 值之間使用 : 分隔
鍵必須是唯一
值 可以取任何數據類型，但鍵只能使用 字串 數字 或是 元組
'''

tom = {
    "name": "tom",
    "age": 18,
    "height": 1.75,
    "weight": 75}
print(tom)  # {'name': 'tom', 'age': 18, 'height': 1.75, 'weight': 75}

#將列表硬轉成字典，這個列表的每個元素都是元組，每個元組有兩個元素
#只有符合固定格式的寫法才能轉換成字典

dict4 = dict([("name", "lucy"), ("age", 18)])
# dict5 = dict([(1, 2, 3), (4, 5), (6, 7)])  # 不符合字典格式是錯誤的定義
print(dict4)  # {'name': 'lucy', 'age': 18}

dict4 = dict((["name", "lucy"], ["age", 18]))
print(dict4)  # {'name': 'lucy', 'age': 18}

tuples1 = ("name", "meow")
# dict3 = dict(tuples1) #報錯
dict4 = dict([("name", "meow")])  # 每隔元素要成對出現
print(dict4)  # {'name': 'meow'}

# 要想把列表、元組都轉換成一個字典
# dict() 內部以一個集合的形式出現，這個集合的元素要成對出現 ==> 成對 這兩個元素也要組成一個列表或元組

# dict4 = dict(((1, 2, 6), (3, 4))) #不成對出現 會報錯
dict4 = dict(((1, 2), (3, 4)))
print(dict4)#{1: 2, 3: 4}

#字典的增刪改查-增加
dict6 = {}
dict6 = {"meow": "hacking"}
print(dict6)  #{'meow': 'hacking'}

#格式: dict6[key] = value
# 特點: 按照上面的格式，如果在字典中存在同名的key，則發生值的覆蓋(後面的值覆蓋原來的值)
# KEY是唯一的 value可以是不唯一的
dict6['meow'] = 'hacker'
dict6['meow'] = "haha"

# 增加
dict6["type"] = "meowmeow book"
dict6["price"] = 1000
dict6["color"] = "black"
print(dict6) #{'meow': 'haha', 'type': 'meowmeow book', 'price': 1000, 'color': 'black'}


#用戶註冊功能，用戶填寫如下信息，完成用戶註冊
#username
#password
#email
#phone

import sys

print("*"*10+"歡迎使用meowmeow用戶註冊功能"+"*"*10)
database = []  # 定義列表用來存儲多個用戶生成的字典

while True:
    username = input("請輸入使用者名稱: ")
    password = input("請輸入密碼: ")
    repasswd = input("請再次輸入密碼: ")
    email = input("請輸入email: ")
    phone = input("請輸入手機號碼: ")

    user = {}
    # 將信息保存到字典
    user["username"] = username

    while phone.isdigit() == False or len(phone) != 9:
        print("手機號碼格式有錯(EX:123456789)，請重新輸入")
        phone = input("請輸入手機號碼: ")

    while '@' not in email or '.com' not in email == False:
        print("Email格式有誤，請重新輸入")
        email = input("請輸入email: ")

    i = 0
    while i < 3:
        if password == repasswd:
            user["password"] = password
            break
        else:
            print("兩次密碼不一致!請重輸入")
            repasswd = input("請再次輸入密碼: ")
            i += 1
        if i >= 3:
            sys.exit("帳號鎖定，請等幾分鐘後重新註冊")

    user["email"] = email
    user["phone"] = phone
    # 將信息保存到資料庫
    database.append(user)

    ans = input("資料無誤，是否繼續註冊? (y/n)")
    if ans != "y":
        break

print(database)

#字典的增刪改查-查詢字典內元素
# 字典中根據KEY查找
dict1 = {"1": "老六", "2": "老李", "3": "老王"}
print(dict1)  # {'1': '老六', '2': '老李', '3': '老王'}

dict1 = {"老李": 100, "老王": 33, "老六": 83}
print(dict1["老六"])  # 取值 83

# items() #把字典轉換成列表的形式，元素是元組
print(dict1.items())  #dict_items([('老李', 100), ('老王', 33), ('老六', 83)])

# print(dict1.items())
# #dict_items([('老李', 100), ('老王', 33), ('老六', 83)])

for key, value in dict1.items():
    if value > 90:
        print(key, value)  # 老李 100


result = dict1.values()
print(result)  # dict_values([100, 33, 83])

# 求所有考生平均分
for score in dict1.values():
    print(score)  # 100 33 83
score = dict1.values()
total = sum(score)  # 216
avg = total / len(score)  # 216 / 3
print(avg)#72.0

# Keys() 取出字典中所有的鍵 生成一個列表
names = dict1.keys()
print(names)  # dict_keys(['老李', '老王', '老六'])
print(type(names))  # <class 'dict_keys'>
for name in names:
    print(name)
'''
老李
老王
老六
'''

#字典的增刪改查-刪除
#del 關鍵字
#若刪除不存在的元素會報錯

list1 = [3, 5, 6, 8]
del list1[1]
print(list1)#[3, 6, 8]

dict1 = {"老李": 100, "老王": 33, "老六": 83, "老皮": 45, "李四": 66}
del dict1["老王"]
print(dict1)#{'老李': 100, '老六': 83, '老皮': 45, '李四': 66}

#字典內置函數: 刪除
# pop(key[,default])
dict1.pop("老六")
print(dict1)#{'老李': 100, '老皮': 45, '李四': 66}
#根據KEY刪除字典中的鍵值對，返回的只要刪除成果，則返回鍵值對的值value
#pop的默認值往往實際刪除的時候沒有找到對應的key，則返回默認

#默認值 用於在找時 如果沒找到 用來提示結果
result = dict1.pop("喵喵?", "為何沒喵喵")
print(result)  # 為何沒喵喵
print(dict1)#{'老李': 100, '老皮': 45, '李四': 66}

#popitem():隨機刪除字典中鍵值對(一般是末尾刪除)

dict1 = {"老李": 100, "老王": 33, "老六": 83, "老皮": 45, "李四": 66}
result = dict1.popitem()
print(result)  # ('李四', 66)
print(dict1)  # {'老李': 100, '老王': 33, '老六': 83, '老皮': 45}

# clear() 同列表的clear
dict1.clear()
print(dict1)#{}

#update() 合併操作 相當於列表中的extend()
dict1 = {0: "tom", 1: "jack", 2: "lucy"}
dict2 = {0: "meme", "4": "meow"}
dict1.update(dict2)
print(dict1)#{0: 'meme', 1: 'jack', 2: 'lucy', '4': 'meow'}

#fromkeys(seq, [])
#將seq轉成字典的形式，如果沒有指定默認的value,則用none
list1 = ['aa', 'bb', 'cc']
newdict = dict.fromkeys(list1, 100)
newdict2 = dict.fromkeys(list1)

print(newdict)  # {'aa': 100, 'bb': 100, 'cc': 100}
print(newdict2) # {'aa': None, 'bb': None, 'cc': None}

```

**集合**
某些指定的對象集在一起就成為一個集合，其中每一個對象叫元素

格式: 集合名 = {元素1, 元素2, ...}

關鍵字 : set()

例: my_set = {1,3,5}

+ 集合是無序的 -> 不支持下標索引
+ 集合是可辨的數據類型
+ 集合中的元素是唯一的

`集合一般用於元組或是列表中的元素去重複`

定義一個空的集合 my_set = set()

`my_set = {}這寫法是一個空字典`

`集合輸出結果是不會按照順序輸出，是隨機的`

```python=
#定義一個集合
s1 = set() #空集合
s2 = {1,2,4,5} #有元素的集合表示方法
print(type(s1,s2)) # <class 'set'> <class 'set'>

#增加元素 .add 增加一個元素:元素的類型 可以是一個單個的元素，也可以把元組作為一個元素
s1.add('hi')
s1.add('meow')
print(s1)  #{'hi', 'meow'}

#update()可以添加多個元素 把其他集合增加進來

t1 = ('老王', '老李')
s1.update(t1)
print(s1)  #{'老李', 'hi', '老王', 'meow'}


s1.add(t1)#t1為一個元素被添加進集合
t1 = ("老王","meow","老李")
l1 = ["阿甘","丹丹"]
s1.update(t1)
s1.add(t1)  #.add可以增加一個元組 作為集合的一個元素
print(s1)  #{'老李', '老王', 'hi', 'meow', ('老王', 'meow', '老李')}

# 刪除元素 remove pop clear del
s1.remove("老王")  # 使用remove刪除一個集合裡面的元素
# s1.remove("hack")  # 刪除集合中不存在元素...會報錯
print(s1)  # {'老李', 'meow', 'hi', ('老王', 'meow', '老李')}


# pop 隨機刪除集合中元素
s1.pop()
print(s1)  # {'meow', 'hi', '老李'}

# del
# del s1 #不能刪除集合裡面的單個元素 能刪除整個集合

# discard 丟棄 能夠移除 集合中不存在的元素 也能移除不存在元素 並且不會報錯
s1.discard("meow")
print(s1)


# clear 清除所有元素
s1.clear()
print(s1)


"""
1.產生10個 1-20的隨機數 去除裡面的重複項
2.鍵盤輸入一個元素，將這個元素從不重複的集合中刪除
"""

import random

from numpy import setxor1d

list1 = []

# 產生10個隨機數，就是列表的10個元素
for i in range(10):
    ran = random.randint(1, 20)
    list1.append(ran)

# 通過集合去重
print(list1)  # [1, 12, 11, 8, 19, 15, 14, 2, 2, 4]
set1 = set(list1)
print(set1)  # {1, 2, 4, 8, 11, 12, 14, 15, 19}

# 鍵盤輸入一個元素，將這個元素從不重複的集合裡面刪除
num1 = int(input(" 輸入一個數字: "))  # 輸入一個數字: 1
set1.discard(num1)
print(set1)  # {2, 4, 8, 11, 12, 14, 15, 19}


print("*"*20+"方法2"+"*"*20)
# 方法2
set2 = set()
for i in range(10):
    ran = random.randint(1, 20)
    set2.add(ran)
print(set2)  # {2, 3, 6, 7, 10, 13, 14, 15, 17, 19}

# 鍵盤輸入一個元素，將這個元素從不重複的集合裡面刪除
num1 = int(input(" 輸入一個數字: "))  # 輸入一個數字: 3
set2.discard(num1)
print(set2)  # {2, 6, 7, 10, 13, 14, 15, 17, 19}



```


