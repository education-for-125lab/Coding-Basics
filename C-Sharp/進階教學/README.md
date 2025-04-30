## C# 進階教學
### 二維陣列
程式碼
```
using System;
// 1個[,]是二維 ,2個[,,]是3維 
int[,] num1 =
{ { 1, 1, 2},
  { 2, 3, 4},
  { 3, 4, 5}
};

int[,,] num2 =
{
    { { 1, 2 }, { 3, 4 } },
    { { 5, 6 }, { 7, 8 } }
};
//int[,,] num2 是一個三維陣列，可以理解為有多個二維陣列組合而成，這裡有 2 個「層」(layer)，每一層又有 2 行（row）和 2 列（column）。這樣構成了一個 2x2x2 的三維陣列

System.Console.WriteLine(num1[1,1]); // row 橫排 , column 直排
System.Console.WriteLine(num2[0, 1, 1]); // 取出4
System.Console.WriteLine(num2[1, 1, 1]); // 取出8
```
結果
```
3
4
8

```

### 物件導向 Class 類別 & object 物件  
1. 基礎 (先創建Person.cs 與 Person )
* Person.cs
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
// class Person 類別
class Person
{
    public double height;
    public string name;
    public int age;

}


```
* Program.cs
```
using System;

// persion1  object 物件
Person person1= new Person();
person1.height = 185;
person1.name = "謝秉棋";
person1.age = 21;
System.Console.WriteLine("姓名: " + person1.name + " 身高: " + person1.height + " 歲數: " + person1.age );


Person person2 = new Person();
person2.height = 180;
person2.name = "小棋";
person2.age = 22;
System.Console.WriteLine("姓名: " + person2.name + " 身高: " + person2.height + " 歲數: " + person2.age);


```
結果
```
姓名: 謝秉棋 身高: 185 歲數: 21
姓名: 小棋 身高: 180 歲數: 22

```
2. 進階
* Program.cs
```
using System;
using QI;  // 'using' 陳述式應該放在最上面
// namespace 就是命名空間可以在裡面創建不同Class 
namespace QI
{
    class Person
    {
        public double height;
        public string name;
        public int age;
    }
    // 另一個類別，也在同一個命名空間下
    public class Car
    {
        public string Model;
        public int Year;

        public void Start()
        {
            Console.WriteLine($"{Model} is starting.");
        }
    }
}

class Program
{
    static void Main()
    {
        // 創建物件 person1
        QI.Person person1 = new QI.Person();
        person1.height = 185;
        person1.name = "謝秉棋";
        person1.age = 21;
        System.Console.WriteLine("姓名: " + person1.name + " 身高: " + person1.height + " 歲數: " + person1.age);

        // 創建物件 person2
        QI.Person person2 = new QI.Person();
        person2.height = 180;
        person2.name = "小棋";
        person2.age = 22;
        System.Console.WriteLine("姓名: " + person2.name + " 身高: " + person2.height + " 歲數: " + person2.age);

        // 創建 Car 類別的物件
        QI.Car car1 = new QI.Car();
        car1.Model = "Toyota";
        car1.Year = 2020;
        Console.WriteLine("車子品牌: " + car1.Model + " 年: " + car1.Year);
    }
}

```
結果
```
姓名: 謝秉棋 身高: 185 歲數: 21
姓名: 小棋 身高: 180 歲數: 22
車子品牌: Toyota 年: 2020

```
### Method 
* Person.cs
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
// class Person 類別
namespace ConsoleApp1
{
    // Person 類別
    class Person
    {
        public double height;
        public string name;
        public int age;

        public void SayHi()
        {
            Console.WriteLine("你好我的名字: " + name);

        }

        public void IsAdult()
        {
            if (age >= 18)
            {
                Console.WriteLine("我已經成年了");

            }
            else
            {
                Console.WriteLine("我還未成年");

            }
        }
        public int Add(int num1, int num2)
        {
            return (num1 + num2);
        }
    }
}


```
* Program.cs
```
using System;
using ConsoleApp1;
// persion1  object 物件
Person person1 = new Person();
person1.height = 185;
person1.name = "謝秉棋";
person1.age = 21;
System.Console.WriteLine("姓名: " + person1.name + " 身高: " + person1.height + " 歲數: " + person1.age);
// person1.SayHi();
person1.SayHi();
person1.IsAdult();
Console.WriteLine("我想要相加3跟5, 答案是: " + person1.Add(3, 5));



// persion2  object 物件
Person person2 = new Person();
person2.height = 180;
person2.name = "小棋";
person2.age = 17;
System.Console.WriteLine("姓名: " + person2.name + " 身高: " + person2.height + " 歲數: " + person2.age);
// person2.SayHi();
person2.SayHi();
person2.IsAdult();
Console.WriteLine("我想要相加10跟5, 答案是: " + person1.Add(5, 10));

```
結果
```
姓名: 謝秉棋 身高: 185 歲數: 21
你好我的名字: 謝秉棋
我已經成年了
我想要相加3跟5, 答案是: 8
姓名: 小棋 身高: 180 歲數: 17
你好我的名字: 小棋
我還未成年
我想要相加10跟5, 答案是: 15

```
### static 說明
1. 若是沒有static 
* Person.cs
```
class Person
{
    public void SayHi()
    {
        Console.WriteLine("嗨，我是人！");
    }
}

```
* Program.cs
```
class Program
{
    static void Main()
    {
        // 先創造一個人
        Person p1 = new Person();
        // 再叫他打招呼
        p1.SayHi();
    }
}

```
結果
```
嗨，我是人！
```
2. 若是有static
* Person.cs
```
class Person
{
    public static void SayHi()
    {
        Console.WriteLine("嗨，我是人！");
    }
}
```
* Program.cs
```
class Program
{
    static void Main()
    {

        Person.SayHi();
    }
}


```
結果
```
嗨，我是人！
```
3. static 結論 (重要)
```
沒有 static（一般方法） | 有 static（靜態方法）
要 new 出一個物件才能用 | 直接用，不用 new
和「某個物件」有關      | 和「類別」有關
```
* 自己總結
```
類型                       | 用什麼？            | 例子                     | 說明
每個人都「有自己獨立的資料」 | 用 object（物件）   | 人的名字、身高、年齡       | 每個人都不同，不能共用
大家「共用同一個功能」      | 用 static（靜態）   | 加法、取最大值、現在時間    | 這些功能不屬於某個特定的人，大家都可以直接用
```

### 總結測試題
* 題目 (請先自己想再看答案)
```
請設計一個 Student 類別，包含以下成員：

欄位（Fields）：

string name（學生姓名）

int[] scores（五科成績）

方法（Methods）：

void ShowInfo()：印出學生姓名與每一科成績。

double GetAverage()：計算並回傳五科成績的平均分數。

接著在 Program.cs 中：

使用 迴圈 新增 3位學生（名字自己設定），每位學生的 5 科成績可以隨意設定。

印出每位學生的所有資料及平均成績。


```
* 題目結果
```
請輸入學生姓名:
謝秉棋
請輸入學生成績:
請輸入第1科成績:
100
請輸入第2科成績:
98
請輸入第3科成績:
100
請輸入第4科成績:
97
請輸入第5科成績:
99
學生姓名：謝秉棋
成績：
科目 1: 100
科目 2: 98
科目 3: 100
科目 4: 97
科目 5: 99
平均成績：98.80

請輸入學生姓名:
小棋
請輸入學生成績:
請輸入第1科成績:
87
請輸入第2科成績:
90
請輸入第3科成績:
86
請輸入第4科成績:
96
請輸入第5科成績:
100
學生姓名：小棋
成績：
科目 1: 87
科目 2: 90
科目 3: 86
科目 4: 96
科目 5: 100
平均成績：91.80

請輸入學生姓名:
小秉
請輸入學生成績:
請輸入第1科成績:
100
請輸入第2科成績:
56
請輸入第3科成績:
32
請輸入第4科成績:
32
請輸入第5科成績:
56
學生姓名：小秉
成績：
科目 1: 100
科目 2: 56
科目 3: 32
科目 4: 32
科目 5: 56
平均成績：55.20

```
* 答案
1. Student.cs
```
using System;
using System.Collections.Generic;
using System.IO.Pipes;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp1
{
    class Student
    {
        public string name;
        public int[] scores = new int[5];
        public void ShowInfo()
        {
            Console.WriteLine($"學生姓名：{name}");
            Console.WriteLine("成績：");
            for (int i = 0; i < scores.Length; i++)
            {
                Console.WriteLine($"科目 {i + 1}: {scores[i]}");
            }
        }
        public double GetAverage()
        {
            double sum = 0;
            for (int i = 0; i < scores.Length; i++)
            {
                sum += scores[i];
            }
            return sum / scores.Length;
        }
    }
}

```
2. Program.cs
```
using System.Runtime.Serialization.Formatters;
using ConsoleApp1;

class Program
{
    static void Main()
    {

        Student[] student = new Student[3];
        for (int i = 0; i < student.Length; i++)
        {
            student[i] = new Student();
            Console.WriteLine("請輸入學生姓名:");
            student[i].name = Console.ReadLine();
            Console.WriteLine("請輸入學生成績:");
            for (int j = 0; j < 5; j++)
            {
                Console.WriteLine("請輸入第" + (j + 1) + "科成績:");
                student[i].scores[j] = int.Parse(Console.ReadLine());

            }
            // 顯示學生資料及平均成績
            student[i].ShowInfo();
            Console.WriteLine($"平均成績：{student[i].GetAverage():F2}");
            Console.WriteLine();  // 換行
        }

    }
}

```
