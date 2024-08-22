# YouTube: 
## [How to connect C# to SQL(thi easy way)](https://youtu.be/Et2khGnrIqc?si=0s5eHFeZ157KCCQQ)
  - 了解如何使用名為 Dapper（由 Stack Overflow 團隊建立）的微型 ORM 以簡單的方式從 C# 連接到 SQL。
  - 了解從 SQL 取得資料並從 SQL 中取出資料是多麼容易，而無需複雜的生成程式碼或混亂的資料表。

## Step
  1. 打開Visual Studio，創建新方案"SQLDataAccessDemo"(.Net Framework 4.8)。
  2. Form1.cs更改檔名為"Dashboard.cs"，text改為"SQL Data Access Demo"，字體改"16"。
  3. 準備好資料庫"Sample"(SQL Server)，製作Dummy Data的網站 [https://www.mockaroo.com/](https://www.mockaroo.com/)
     欄位:
      - id[int]
      - FirstName[nvarchar(50)]
      - LastName[nvarchar(50)]
      - EmailAddress[nvarchar(100)]
      - PhoneNumber[varchar(20)]
  4. 新增class"Person.cs"
```C#
public class Person
{
    public int id { get; set; }
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public string EmailAddress { get; set; }
    public string PhoneNumber { get; set; }
}
```
  5. 新增class"Helper.cs"
```C#
public static class Helper
{
    public static string CnnVal(string name)
    {
        return ConfigurationManager.ConnectionStrings[name].ConnectionString;
    }
}
```
  6. 在方案瀏覽器對"References"點右鍵，"Add Reference..."，搜尋"config"找到"System.Configuration"，打勾後按OK。
```C#
//新增下面代碼到"Helper.cs"最上方
using System.Configuration;
```
