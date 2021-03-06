---
title: "展开的 QName (XQuery) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: xquery
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
dev_langs:
- XML
helpviewer_keywords:
- expanded-QName function
- fn:expanded-QName function
ms.assetid: b8377042-95cc-467b-9ada-fe43cebf4bc3
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a9a00b0b5f6e21f8590c4dee3e1a588d0203f004
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="functions-related-to-qnames---expanded-qname"></a>与 QNames-展开 QName 相关函数
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  返回具有 URI 中指定的命名空间的 xs: qname 类型的一个值*$paramURI*中指定的本地名称和*$paramLocal*。 如果*$paramURI*是空字符串或空序列，它表示不在命名空间。  
  
## <a name="syntax"></a>语法  
  
```  
fn:expanded-QName($paramURI as xs:string?, $paramLocal as xs:string?) as xs:QName?  
```  
  
## <a name="arguments"></a>参数  
 *$paramURI*  
 QName 的命名空间 URI。  
  
 *$paramLocal*  
 QName 的本地名称部分。  
  
## <a name="remarks"></a>注释  
 以下规则适用于**expanded-QName()**函数：  
  
-   如果*$paramLocal*指定值不处于 xs:NCName 类型正确词法窗体时，会返回空序列，并表示动态错误。  
  
-   在 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 中不支持从 xs:QName 类型转换为任何其他类型。 因此， **expanded-QName()**函数不能在 XML 构造。 例如，当构造节点（如 `<e> expanded-QName(…) </e>`）时，其值就必须是非类型化的。 这就要求您将 `expanded-QName()` 返回的 xs:QName 类型值转换为 xdt:untypedAtomic。 但是，不支持此操作。 在本主题的后面的示例中给出了一种解决方案。  
  
-   您可以修改或比较现有的 QName 类型值。 例如，`/root[1]/e[1] eq expanded-QName("http://nsURI" "myNS")`值进行比较的元素，<`e`>，返回的 QName 与**expanded-QName()**函数。  
  
## <a name="examples"></a>示例  
 本主题提供对存储在各种的 XML 实例的 XQuery 示例**xml**类型中的列[!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]数据库。  
  
### <a name="a-replacing-a-qname-type-node-value"></a>A. 替换 QName 类型节点值  
 此示例说明了如何修改 QName 类型的元素节点的值。 该示例执行以下操作：  
  
-   创建定义 QName 类型的元素的 XML 架构集合。  
  
-   使用创建一个表**xml**通过使用 XML 架构集合的类型列。  
  
-   将 XML 实例保存在表中。  
  
-   使用**modify （)**要修改的实例中的 QName 类型元素的值的 xml 数据类型的方法。 **Expanded-QName()**函数用于生成新的 QName 类型值。  
  
```  
-- If XML schema collection (if exists)  
-- drop xml schema collection SC  
-- go  
-- Create XML schema collection  
CREATE XML SCHEMA COLLECTION SC AS N'  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema"   
    targetNamespace="QNameXSD"   
      xmlns:xqo="QNameXSD" elementFormDefault="qualified">  
      <element name="Root" type="xqo:rootType" />  
      <complexType name="rootType">  
            <sequence minOccurs="1" maxOccurs="1">  
                        <element name="ElemQN" type="xs:QName" />  
            </sequence>  
      </complexType>  
</schema>'  
go  
-- Create table.  
CREATE TABLE T( XmlCol xml(SC) )  
-- Insert sample XML instnace  
INSERT INTO T VALUES ('  
<Root xmlns="QNameXSD" xmlns:ns="http://myURI">  
      <ElemQN>ns:someName</ElemQN>  
</Root>')  
go  
-- Verify the insertion  
SELECT * from T  
go  
-- Result  
<Root xmlns="QNameXSD" xmlns:ns="http://myURI">  
  <ElemQN>ns:someName</ElemQN>  
</Root>   
```  
  
 在下面的查询中，<`ElemQN`> 元素值将由使用替换**modify （)** xml 数据类型和 XML DML，如所示的替换值的方法。  
  
```  
-- the value.  
UPDATE T   
SET XmlCol.modify('  
  declare default element namespace "QNameXSD";   
  replace value of /Root[1]/ElemQN   
  with expanded-QName("http://myURI", "myLocalName") ')  
go  
-- Verify the result  
SELECT * from T  
go  
```  
  
 结果如下： 请注意，QName 类型的元素 <`ElemQN`> 现在有了一个新的值：  
  
```  
<Root xmlns="QNameXSD" xmlns:ns="urn">  
  <ElemQN xmlns:p1="http://myURI">p1:myLocalName</ElemQN>  
</Root>  
```  
  
 以下语句删除了用于示例的对象。  
  
```  
-- Cleanup  
DROP TABLE T  
go  
drop xml schema collection SC  
go  
```  
  
### <a name="b-dealing-with-the-limitations-when-using-the-expanded-qname-function"></a>B. 处理使用 expanded-QName() 函数时的限制。  
 **展开 QName**函数不能在 XML 构造。 下面的示例阐释了这一点。 为了消除此限制，该示例首先插入一个节点，然后修改此节点。  
  
```  
-- if exists drop the table T  
--drop table T  
-- go  
-- Create XML schema collection  
-- DROP XML SCHEMA COLLECTION SC  
-- go  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
      <element name="root" type="QName" nillable="true"/>  
</schema>'  
go  
 -- Create table T with a typed xml column (using the XML schema collection)  
CREATE TABLE T (xmlCol XML(SC))  
go  
-- Insert an XML instance.  
insert into T values ('<root xmlns:a="http://someURI">a:b</root>')  
 go  
-- Verify  
SELECT *   
FROM T  
```  
  
 以下示例尝试添加其他 <`root`> 元素，但未成功，因为 XML 构造不支持 expanded-QName() 函数。  
  
```  
update T SET xmlCol.modify('  
insert <root>{expanded-QName("http://ns","someLocalName")}</root> as last into / ')  
go  
```  
  
 解决方案是：首先为 <`root`> 元素插入带有值的实例，然后再修改它。 在此示例中，当插入 <`root`> 元素时初始值为空。 此示例中的 XML 架构集合允许 <`root`> 元素的值为空。  
  
```  
update T SET xmlCol.modify('  
insert <root xsi:nil="true"/> as last into / ')  
go  
-- now replace the nil value with another QName.  
update T SET xmlCol.modify('  
replace value of /root[last()] with expanded-QName("http://ns","someLocalName") ')  
go  
 -- verify   
SELECT * FROM T  
go  
-- result  
<root>b</root>  
```  
  
 `<root xmlns:a="http://someURI">a:b</root>`  
  
 `<root xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:p1="http://ns">p1:someLocalName</root>`  
  
 可以比较 QName 值，如以下查询所示。 查询仅返回 <`root`> 元素，其值与匹配 QName 类型返回值**expanded-QName()**函数。  
  
```  
SELECT xmlCol.query('  
    for $i in /root  
    return  
       if ($i eq expanded-QName("http://ns","someLocalName") ) then  
          $i  
       else  
          ()')  
FROM T  
```  
  
### <a name="implementation-limitations"></a>实现限制  
 一个日期和时间限制： **expanded-QName()**函数接受第二个参数为空序列，并将返回而不是引发运行时错误，第二个参数不正确时为空。  
  
## <a name="see-also"></a>另请参阅  
 [与 QNames &#40; 相关的功能XQuery &#41;](http://msdn.microsoft.com/library/7e07eb26-f551-4b63-ab77-861684faff71)  
  
  
