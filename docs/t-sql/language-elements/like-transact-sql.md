---
title: "类似 (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ESCAPE
- LIKE
- ESCAPE_TSQL
- LIKE_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ESCAPE keyword
- '% (wildcard - character(s) to match)'
- ASCII pattern matching
- pattern searching [SQL Server]
- wildcard characters [SQL Server]
- literals [SQL Server], using wildcards
- character strings [SQL Server], LIKE
- exact matches [SQL Server]
- Boolean functions
- LIKE comparisons
- matching patterns [SQL Server]
- NOT LIKE keyword
ms.assetid: 581fb289-29f9-412b-869c-18d33a9e93d5
caps.latest.revision: 50
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 643966017caf06959fef24177dd93d7254f30915
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="like-transact-sql"></a>LIKE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  确定特定字符串是否与指定模式相匹配。 模式可以包含常规字符和通配符。 模式匹配过程中，常规字符必须与字符串中指定的字符完全匹配。 但是，通配符可以与字符串的任意部分相匹配。 与使用 = 和 != 字符串比较运算符相比，使用通配符可使 LIKE 运算符更加灵活。 如果任何一个参数不属于字符串数据类型，则 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]会将其转换为字符串数据类型（如果可能）。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
match_expression [ NOT ] LIKE pattern [ ESCAPE escape_character ]  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
match_expression [ NOT ] LIKE pattern  
```  
  
## <a name="arguments"></a>参数  
 *match_expression*  
 是任何有效[表达式](../../t-sql/language-elements/expressions-transact-sql.md)的字符数据类型。  
  
 *模式*  
 是要在中搜索的字符的特定字符串*match_expression*，并且可以包括下列有效的通配符。 *模式*最多为 8000 个字节。  
  
|通配符|Description|示例|  
|------------------------|-----------------|-------------|  
|%|包含零个或多个字符的任意字符串。|WHERE title LIKE '%computer%' 将查找在书名中任意位置包含单词 "computer" 的所有书名。|  
|_（下划线）|任何单个字符。|WHERE au_fname LIKE '_ean' 将查找以 ean 结尾的所有 4 个字母的名字（Dean、Sean 等）。|  
|[ ]|指定范围 ([a-f]) 或集合 ([abcdef]) 中的任何单个字符。|WHERE au_lname LIKE '[C-P]arsen' 将查找以 arsen 结尾并且以介于 C 与 P 之间的任何单个字符开始的作者姓氏，例如 Carsen、Larsen、Karsen 等。 在范围搜索中，范围包含的字符可能因排序规则的排序规则而异。|  
|[^]|不属于指定范围 ([a-f]) 或集合 ([abcdef]) 的任何单个字符。|WHERE au_lname LIKE 'de[^l]%' 将查找以 de 开始并且其后的字母不为 l 的所有作者的姓氏。|  
  
 *escape_character*  
 放在通配符之前用于指示通配符应当解释为常规字符而不是通配符的字符。 *escape_character*没有默认值并计算结果必须只有一个字符为字符表达式。  
  
## <a name="result-types"></a>结果类型  
 **Boolean**  
  
## <a name="result-value"></a>结果值  
 如果，则如返回 TRUE *match_expression*匹配所指定*模式*。  
  
## <a name="remarks"></a>注释  
 如果使用 LIKE 执行字符串比较，则模式字符串中的所有字符都有意义。 这包括前导或尾随空格。 如果查询中的比较要返回包含 "abc "（abc 后有一个空格）的所有行，则不会返回包含 "abc"（abc 后没有空格）的列所在行。 但是可以忽略模式所要匹配的表达式中的尾随空格。 如果查询中的比较要返回包含 "abc"（abc 后没有空格）的所有行，则返回以 "abc" 开始并且具有零个或多个尾随空格的所有行。  
  
 使用包含的模式的字符串比较**char**和**varchar**数据可能无法通过 LIKE 比较由于存储数据的方式。 您应当了解每种数据类型的存储方式以及导致 LIKE 比较失败的原因。 下面的示例传入本地**char**到存储的过程，然后使用模式匹配来找到所有员工具有一组指定的字符其最后一个名称开头的变量。  
  
```tsql
-- Uses AdventureWorks  
  
CREATE PROCEDURE FindEmployee @EmpLName char(20)  
AS  
SELECT @EmpLName = RTRIM(@EmpLName) + '%';  
SELECT p.FirstName, p.LastName, a.City  
FROM Person.Person p JOIN Person.Address a ON p.BusinessEntityID = a.AddressID  
WHERE p.LastName LIKE @EmpLName;  
GO  
EXEC FindEmployee @EmpLName = 'Barb';  
GO  
```  
  
 在`FindEmployee`过程中，会返回任何行因为**char**变量 (`@EmpLName`) 包含尾随空格，只要名称包含少于 20 个字符。 因为`LastName`列为**varchar**，没有任何尾随空格。 因为尾随空格是有意义的，所以此过程失败。  
  
 但是，下面的示例会成功，因为尾随空格不会添加到**varchar**变量。  
  
```tsql
-- Uses AdventureWorks  
  
CREATE PROCEDURE FindEmployee @EmpLName varchar(20)  
AS  
SELECT @EmpLName = RTRIM(@EmpLName) + '%';  
SELECT p.FirstName, p.LastName, a.City  
FROM Person.Person p JOIN Person.Address a ON p.BusinessEntityID = a.AddressID  
WHERE p.LastName LIKE @EmpLName;  
GO  
EXEC FindEmployee @EmpLName = 'Barb';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
 FirstName      LastName            City
 ----------     -------------------- --------------- 
 Angela         Barbariol            Snohomish
 David          Barber               Snohomish
 (2 row(s) affected)  
 ``` 
 
## <a name="pattern-matching-by-using-like"></a>使用 LIKE 的模式匹配  
 LIKE 支持 ASCII 模式匹配和 Unicode 模式匹配。 当所有自变量 (*match_expression*，*模式*，和*escape_character*，如果存在) 是 ASCII 字符数据类型，将执行 ASCII 模式匹配。 如果任何一个参数为 Unicode 数据类型，则所有参数都将转换为 Unicode，并执行 Unicode 模式匹配。 当你使用 Unicode 数据 (**nchar**或**nvarchar**数据类型) 具有类似的内容，尾随空格有意义; 但是，非 Unicode 数据，尾随空格则没有意义。 Unicode LIKE 与 ISO 标准兼容。 ASCII LIKE 与 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的早期版本兼容。  
  
 下面的一系列示例显示 ASCII LIKE 模式匹配与 Unicode LIKE 模式匹配所返回的行之间的差异。  
  
```tsql  
-- ASCII pattern matching with char column  
CREATE TABLE t (col1 char(30));  
INSERT INTO t VALUES ('Robert King');  
SELECT *   
FROM t   
WHERE col1 LIKE '% King';   -- returns 1 row  
  
-- Unicode pattern matching with nchar column  
CREATE TABLE t (col1 nchar(30));  
INSERT INTO t VALUES ('Robert King');  
SELECT *   
FROM t   
WHERE col1 LIKE '% King';   -- no rows returned  
  
-- Unicode pattern matching with nchar column and RTRIM  
CREATE TABLE t (col1 nchar (30));  
INSERT INTO t VALUES ('Robert King');  
SELECT *   
FROM t   
WHERE RTRIM(col1) LIKE '% King';   -- returns 1 row  
```  
  
> [!NOTE]  
>  LIKE 比较受排序规则影响。 有关详细信息，请参阅[排序规则 (Transact-SQL)](~/t-sql/statements/collations.md)。  
  
## <a name="using-the--wildcard-character"></a>使用 % 通配符  
 如果指定 LIKE '5%' 符号，则[!INCLUDE[ssDE](../../includes/ssde-md.md)]将搜索后跟零个或多个任意字符的数字 5。  
  
 例如，以下查询显示 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 数据库中的所有动态管理视图，因为它们全部以字母 `dm` 开始。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT Name  
FROM sys.system_views  
WHERE Name LIKE 'dm%';  
GO  
```  
  
 若要查看所有非动态管理视图的对象，请使用 `NOT LIKE 'dm%'`。 如果共有 32 个对象且 LIKE 找到 13 个与模式匹配的名称，则 NOT LIKE 将找到 19 个与 LIKE 模式不匹配的对象。  
  
 使用 `LIKE '[^d][^m]%'` 之类的模式不一定每次找到的名称都相同。 可能仅找到 14 名称（而不是 19 个），除了动态管理视图名称外，所有以 `d` 开始或第二个字母为 `m` 的名称也都将从结果中消除。 这是因为用反向通配符匹配字符串是分步骤进行计算的，一次一个通配符。 如果在计算过程中任一环节匹配失败，那么就会将其消除。  
  
## <a name="using-wildcard-characters-as-literals"></a>将通配符作为文字使用  
 可以将通配符模式匹配字符作为文字字符使用。 若要将通配符作为文字字符使用，请将通配符放在方括号中。 下表显示了几个使用 LIKE 关键字和 [ ] 通配符的示例。  
  
|符号|含义|  
|------------|-------------|  
|LIKE '5[%]'|5%|  
|LIKE '[_]n'|_n|  
|LIKE '[a-cdf]'|a、b、c、d 或 f|  
|LIKE '[-acdf]'|-、a、c、d 或 f|  
|LIKE '[ [ ]'|[|  
|LIKE ']'|]|  
|LIKE 'abc[_]d%'|abc_d 和 abc_de|  
|LIKE 'abc[def]'|abcd、abce 和 abcf|  
  
## <a name="pattern-matching-with-the-escape-clause"></a>使用 ESCAPE 子句的模式匹配  
 可搜索包含一个或多个特殊通配符的字符串。 例如，customers 数据库中的 discounts 表可能存储含百分号 (%) 的折扣值。 若要搜索作为字符而不是通配符的百分号，必须提供 ESCAPE 关键字和转义符。 例如，一个样本数据库包含名为 comment 的列，该列含文本 30%。 若要搜索在 comment 列中的任何位置包含字符串 30% 的任何行，请指定 `WHERE comment LIKE '%30!%%' ESCAPE '!'` 之类的 WHERE 子句。 如果未指定 ESCAPE 和转义符，则[!INCLUDE[ssDE](../../includes/ssde-md.md)]将返回包含字符串 30 的所有行。  
  
 如果 LIKE 模式中的转义符后面没有字符，则该模式无效并且 LIKE 返回 FALSE。 如果转义符后面的字符不是通配符，则将放弃转义符并将该转义符后面的字符作为该模式中的常规字符处理。 这包括百分号 (%)、下划线 (_) 和左括号 ([) 通配符（如果它们包含在双括号 ([ ]) 中）。 另外，在双括号字符 ([]) 内，可以使用转义符并将插入符号 (^)、连字符 () 和右括号 (]) 转义。  
  
 0x0000 (**char(0)**) 是 Windows 排序规则中未定义的字符，不能包含在类似。  
  
## <a name="examples"></a>示例  
  
### <a name="a-using-like-with-the--wildcard-character"></a>A. 使用带 % 通配符的 LIKE  
 以下示例在 `415` 表中查找区号为 `PersonPhone` 的所有电话号码。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT p.FirstName, p.LastName, ph.PhoneNumber  
FROM Person.PersonPhone AS ph  
INNER JOIN Person.Person AS p  
ON ph.BusinessEntityID = p.BusinessEntityID  
WHERE ph.PhoneNumber LIKE '415%'  
ORDER by p.LastName;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
 
 ```
 FirstName             LastName             Phone
 -----------------     -------------------  ------------
 Ruben                 Alonso               415-555-124  
 Shelby                Cook                 415-555-0121  
 Karen                 Hu                   415-555-0114  
 John                  Long                 415-555-0147  
 David                 Long                 415-555-0123  
 Gilbert               Ma                   415-555-0138  
 Meredith              Moreno               415-555-0131  
 Alexandra             Nelson               415-555-0174  
 Taylor                Patterson            415-555-0170  
 Gabrielle              Russell             415-555-0197  
 Dalton                 Simmons             415-555-0115  
 (11 row(s) affected)  
 ``` 
 
### <a name="b-using-not-like-with-the--wildcard-character"></a>B. 使用带 % 通配符的 NOT LIKE  
 以下示例在 `PersonPhone` 表中查找区号不是 `415` 的所有电话号码。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT p.FirstName, p.LastName, ph.PhoneNumber  
FROM Person.PersonPhone AS ph  
INNER JOIN Person.Person AS p  
ON ph.BusinessEntityID = p.BusinessEntityID  
WHERE ph.PhoneNumber NOT LIKE '415%' AND p.FirstName = 'Gail'  
ORDER BY p.LastName;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
 
 ```
FirstName              LastName            Phone
---------------------- -------------------- -------------------
Gail                  Alexander            1 (11) 500 555-0120  
Gail                  Butler               1 (11) 500 555-0191  
Gail                  Erickson             834-555-0132  
Gail                  Erickson             849-555-0139  
Gail                  Griffin              450-555-0171  
Gail                  Moore                155-555-0169  
Gail                  Russell              334-555-0170  
Gail                  Westover             305-555-0100  
(8 row(s) affected)  
```  

### <a name="c-using-the-escape-clause"></a>C. 使用 ESCAPE 子句  
 以下示例使用 `ESCAPE` 子句和转义符在 `10-15%` 表的列 `c1` 中查找精确字符串 `mytbl2`。  
  
```tsql
USE tempdb;  
GO  
IF EXISTS(SELECT TABLE_NAME FROM INFORMATION_SCHEMA.TABLES  
      WHERE TABLE_NAME = 'mytbl2')  
   DROP TABLE mytbl2;  
GO  
USE tempdb;  
GO  
CREATE TABLE mytbl2  
(  
 c1 sysname  
);  
GO  
INSERT mytbl2 VALUES ('Discount is 10-15% off'), ('Discount is .10-.15 off');  
GO  
SELECT c1   
FROM mytbl2  
WHERE c1 LIKE '%10-15!% off%' ESCAPE '!';  
GO  
```  
  
### <a name="d-using-the---wildcard-characters"></a>D. 使用 [ ] 通配符  
 下面的示例查找员工上`Person`的第一个同名的表`Cheryl`或`Sheryl`。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT BusinessEntityID, FirstName, LastName   
FROM Person.Person   
WHERE FirstName LIKE '[CS]heryl';  
GO  
```  
  
 以下示例查找 `Person` 表中姓氏为 `Zheng` 或 `Zhang` 的员工所对应的行。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT LastName, FirstName  
FROM Person.Person  
WHERE LastName LIKE 'Zh[ae]ng'  
ORDER BY LastName ASC, FirstName ASC;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="e-using-like-with-the--wildcard-character"></a>E. 使用带 % 通配符的 LIKE  
 下面的示例查找中的所有员工`DimEmployee`开头的电话号码具有表`612`。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, Phone  
FROM DimEmployee  
WHERE phone LIKE '612%'  
ORDER by LastName;  
```  
  
### <a name="f-using-not-like-with-the--wildcard-character"></a>F. 使用带 % 通配符的 NOT LIKE  
 下面的示例查找中的所有电话号码`DimEmployee`表不会启动与`612`。  实例时都提供 SQL Server 登录名。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, Phone  
FROM DimEmployee  
WHERE phone NOT LIKE '612%'  
ORDER by LastName;  
```  
  
### <a name="g-using-like-with-the--wildcard-character"></a>G. 使用如 _ 通配符字符  
 下面的示例查找所有具有区域代码开头的电话号码`6`和以`2`中`DimEmployee`表。 请注意，%通配符字符也包括在搜索模式的末尾由于区号是电话号码的第一部分，其他字符中的列值后存在。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, Phone  
FROM DimEmployee  
WHERE phone LIKE '6_2%'  
ORDER by LastName;   
```  
  
### <a name="h-using-the---wildcard-characters"></a>H. 使用 [ ] 通配符  
 下面的示例查找`DimEmployee`行的第一个名称与`Rob`或`Bob`。  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, Phone  
FROM DimEmployee  
WHERE FirstName LIKE '[RB]ob'  
ORDER by LastName;  
```  
  
## <a name="see-also"></a>另请参阅  
 [表达式 &#40;Transact SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [内置函数 (Transact-SQL)](~/t-sql/functions/functions.md)   
 [SELECT (Transact-SQL)](../../t-sql/queries/select-transact-sql.md)   
 [其中 &#40;Transact SQL &#41;](../../t-sql/queries/where-transact-sql.md)  
 
