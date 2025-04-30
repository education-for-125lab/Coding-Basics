# C# 入門教學

## 學習



## 基礎教學
### 常見資料型態 & 變數
1. 常見資料型態
```
// System 是 .NET Framework（或 .NET Core/.NET 5+）中的一個命名空間，裡面包含了許多基本功能的類別，例如處理輸入輸出、字串、日期、數學運算等等
// System 從 .NET 6.0 開始不需要自己寫(會自動添加)，但為了讓程式碼更清楚，還是建議寫上去

// 字串 string 用雙引號"" 代表一串文字
// 字元 char 用單引號 ''  代表一個文字
// 整數 int  40  就是1,2,3,4,5 可以負數但不能有小數點
// 浮點數 double  40.1  就是1.0,2.0,3.0,4.0,5.0 可以負數也可以有小數點
// 布林值 bool  true false  就是 true 或 false
```
程式碼
```
using System; // 引入 System 命名空間

System.Console.WriteLine("Hello World"); // string
System.Console.WriteLine('a');           // char
System.Console.WriteLine(40);            // int
System.Console.WriteLine(40.1);          // double
System.Console.WriteLine(true);          // bool
```
結果
```
Hello World
a
40
40.1
True

```
2. 變數

程式碼
```
using System; // 引入 System 命名空間

string name = "謝秉棋";  
char sex = '男';
int age = 21;
double height = 185.2;
bool is_female = false;
System.Console.WriteLine("有一位人叫"+ name);
System.Console.WriteLine(name+"今年"+ age + "歲" );           
System.Console.WriteLine(name+ "身高"+ height);            
System.Console.WriteLine(name+"他"+ is_female+"女性");   
System.Console.WriteLine(name+ "他是"+sex+"姓");
name = "小棋";// 前面已經定義為字串之後就不能變他 例: name= 30
System.Console.WriteLine("有一位人叫" + name);

```
結果
```
有一位人叫謝秉棋
謝秉棋今年21歲
謝秉棋身高185.2
謝秉棋他False女性
謝秉棋他是男姓
有一位人叫小棋
```

### 常見字串跟數字用法
1. 字串

程式碼
```
using System; // 引入 System 命名空間

// 字串用法
System.Console.WriteLine("Hello \nWorld");// \n 代表換行
System.Console.WriteLine("Hello \tWorld");// \t 代表跳到下一個 tab 的位置
System.Console.WriteLine("Hello\" \"World\"");//  \" 代表雙引號 是我字串的不是結束
string phrase = "Hello world";
System.Console.WriteLine(phrase); // phrase 是變數名稱
System.Console.WriteLine(phrase.Length); // .Length 代表字串的長度
System.Console.WriteLine(phrase.ToUpper()); // .ToUpper() 代表轉成大寫
System.Console.WriteLine(phrase.ToLower()); // .ToLower() 代表轉成小寫
System.Console.WriteLine(phrase.Contains("hello"));// .Contains() 代表是否包含這個字串
System.Console.WriteLine(phrase.IndexOf("H")); // .IndexOf() 代表這個字串的索引位置(要記得電腦世界索引從 0 開始是0,1.2.3 所以第1位就是0)
System.Console.WriteLine(phrase.Substring(6,3)); //.Substring 取的想要字串並由左而右第6位 然後再往左數3位

```
結果
```
Hello
World
Hello   World
Hello" "World"
Hello world
11
HELLO WORLD
hello world
False
0
wor
```

2. 數字

程式碼
```
using System; // 引入 System 命名空間
// 數字用法
System.Console.WriteLine(5-1);
System.Console.WriteLine(5+5);
System.Console.WriteLine(5*5);
System.Console.WriteLine(5/5);
System.Console.WriteLine(5/2.0);                  // 需有浮點數就改一邊浮點數
System.Console.WriteLine(5+2*3);
System.Console.WriteLine((5+2)*3); 
System.Console.WriteLine(System.Math.Abs(-10));   // System.Math.Abs   絕對值
System.Console.WriteLine(System.Math.Pow(2,4));   // System.Math.Pow   平方
System.Console.WriteLine(System.Math.Sqrt(64));   // System.Math.Sqrt  開根號
System.Console.WriteLine(System.Math.Round(6.4)); // System.Math.Round 四捨五路
System.Console.WriteLine(System.Math.Max(6,4));   // System.Math.Max   比較最大
System.Console.WriteLine(System.Math.Min(6, 4));  // System.Math.Min   比較最小

```
結果
```
4
10
25
1
2.5
11
21
10
16
8
6
6
4
```
## 用戶輸入
程式碼
```
using System; // 引入 System 命名空間
System.Console.Write("Please enter your name: "); // Write 用戶輸入不換行 WriteLine會換行
string name = System.Console.ReadLine();// ReadLine 用戶輸入
System.Console.Write("Please enter your age: "); 
string age = System.Console.ReadLine(); 


System.Console.WriteLine("你的名字是" + name + " 今年是" + age + "歲");

```
結果
```
Please enter your name: 謝秉棋
Please enter your age: 21
你的名字是謝秉棋 今年是21歲

```
1. 小型計算機
程式碼
```
using System; // 引入 System 命名空間
System.Console.Write("請輸入第一個數字: ");
int num1 = Convert.ToInt32(Console.ReadLine()); //Convert.ToInt32 將Console.ReadLine 讀取用戶輸入並轉換為整數 ,Console.ReadLine預設是字串
System.Console.Write("請輸入第二個數字: ");
int num2 = Convert.ToInt32(Console.ReadLine());
System.Console.WriteLine("計算結果是" + (num1 + num2)); 
```
結果
```
請輸入第一個數字: 12
請輸入第二個數字: 21
計算結果是33
```

### Array 陣列 
程式碼
```
using System; // 引入 System 命名空間
int [] scores = { 100, 90, 80, 70, 60, 50, 40, 30, 20, 10 }; // 宣告一個整數陣列 scores，並初始化為一組分數 
System.Console.WriteLine(scores[0]); // 輸出 scores 陣列的第一個元素
System.Console.WriteLine(scores[5]); // 輸出 scores 陣列的第六個元素

string[] phone = new string[15];  // 代表一字串陣列 phone，大小為 15
phone[0] = "0129919111111";
phone[1] = "02002020202020202";
phone[2] = "0101012";
System.Console.WriteLine(phone[2]);
System.Console.WriteLine(phone[1]);
System.Console.WriteLine(phone[0]);
```
結果
```
100
50
0101012
02002020202020202
0129919111111
```
### if 用法
1. 基礎
程式碼
```
using System; // 引入 System 命名空間
System.Console.Write("請輸入Yes或No: ");
string rainy = System.Console.ReadLine();
if (rainy == "Yes") // 如果輸入的字串是 Yes
{
    System.Console.WriteLine("今天下雨了"); // 就顯示今天下雨了
}
else if (rainy == "No") // 如果輸入的字串是 NO
{
    System.Console.WriteLine("今天沒有下雨"); // 就顯示今天沒有下雨
}
else
{
    System.Console.WriteLine("請輸入正確的字串"); // 否則就顯示請輸入正確的字串
}
```
結果
```
請輸入Yes或No: Yes
今天下雨了
```
2. 進階
程式碼
```
using System; // 引入 System 命名空間
System.Console.Write("請輸入分數: ");
int score = Convert.ToInt32(Console.ReadLine());
System.Console.Write("請輸入 True 或 False: ");
bool rainy_1 = bool.Parse(Console.ReadLine());
if (score == 0 && rainy_1)
{
    System.Console.WriteLine("分數是0並且True");
}
else if (score == 100 || rainy_1==false) 
{
    System.Console.WriteLine("分數是100或false"); 
}
else
{
    System.Console.WriteLine("分數不是0與false"); 
}
```
結果
```
請輸入分數: 0
請輸入 True 或 False: true
分數是0並且True
```
3. 計算機難度版
程式碼
```
using System; // 引入 System 命名空間
System.Console.Write("Please enter first number: "); // 請輸入一個數字
double num1= Convert.ToDouble(Console.ReadLine()); 
System.Console.Write("Please enter second number: "); // 請輸入第二個數字
double num2 = Convert.ToDouble(Console.ReadLine());
System.Console.Write("Please enter operator (+,-.*,/): "); // 請輸入運算子
string op = Console.ReadLine(); // 讀取運算子
double result = 0;
if (op == "+") // 如果運算子是 +
{
    result = num1 + num2; // 就把 num1 和 num2 相加
}
else if (op == "-") // 如果運算子是 -
{
    result = num1 - num2; // 就把 num1 和 num2 相減
}
else if (op == "*") // 如果運算子是 *
{
    result = num1 * num2; // 就把 num1 和 num2 相乘
}
else if (op == "/") // 如果運算子是 /
{
    if (num2 != 0)
    {
        result = num1 / num2;
        double remainder = num1 % num2; // 加這行來取得餘數
        System.Console.WriteLine($"{num1} {op} {num2} = {result}");
        System.Console.WriteLine($"餘數 (Remainder) = {remainder}");
        return;
    }
    else
    {
        System.Console.WriteLine("Cannot divide by zero");
        return;
    }
}
else
{
    System.Console.WriteLine("Invalid operator"); // 如果運算子不正確就顯示錯誤訊息
}  
```
結果
```
Please enter first number: 22
Please enter second number: 21
Please enter operator (+,-.*,/): /
22 / 21 = 1.0476190476190477
餘數 (Remainder) = 1

```
## while 迴圈
1. 寫法1 (通常用這個)
程式碼
```
using System;

int num1 = 1;
while (num1<=10)
{
    System.Console.WriteLine(num1);
    num1 = num1 + 1;

}
```
結果
```
1
2
3
4
5
6
7
8
9
10
```
2. 寫法2
程式碼
```
int num2 = 1;
do
{
    System.Console.WriteLine(num2);
    num2 = num2 + 1;
}
while (num2 <= 10);
```
結果
```
1
2
3
4
5
6
7
8
9
10
```
3. while 進階題 猜數字遊戲
程式碼
```
using System;

int number = 50;    // 正確數字
int num1 = 0;       // 使用者答案
int num2 = 0;       // 使用者猜的次數
int num3 = 10;      // 10次機會
while (num2< num3 && num1 != number)
{
    System.Console.Write("請輸入猜數字: ");
    num1 = Convert.ToInt32(Console.ReadLine());
    if (num1 < number)
    {
        Console.WriteLine("猜的數字小了");
    }
    else if (num1 > number)
    {
        Console.WriteLine("猜的數字大了");
    }
    num2++;
}
if (num1 == number)
{
    System.Console.WriteLine("恭喜你猜對答案是" + num1 +"共猜了"+ num2 +"次");
}
else
{
    System.Console.WriteLine("你已經猜了"+num2 + "次,遊戲結束");
}
```
結果
```
請輸入猜數字: 11
猜的數字小了
請輸入猜數字: 109
猜的數字大了
請輸入猜數字: 33
猜的數字小了
請輸入猜數字: 22
猜的數字小了
請輸入猜數字: 44
猜的數字小了
請輸入猜數字: 66
猜的數字大了
請輸入猜數字: 77
猜的數字大了
請輸入猜數字: 33
猜的數字小了
請輸入猜數字: 11
猜的數字小了
請輸入猜數字: 50
恭喜你猜對答案是50共猜了10次

```
### for 迴圈
1.基礎
程式碼
```
using System;
for (int i =1; i<=10; i++)
{
    System.Console.WriteLine(i);
}
```
結果
```
1
2
3
4
5
6
7
8
9
10

```
2. 進階
程式碼
```

using System;
int[] num1 = { 15, 22, 215, 313, 444, 5678, 9872, 11 };


for (int i =0; i< num1.Length; i++)  // i為0 跑陣列相當與i<8
{
    System.Console.WriteLine(num1[i]); // 打印i 跑過的陣列01234567 
}

```
結果
```
15
22
215
313
444
5678
9872
11

```
