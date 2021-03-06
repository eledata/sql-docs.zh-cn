---
title: "不使用任何参数的存储的过程 |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9470a6d-a758-4c56-96ec-7b37139e36a7
caps.latest.revision: "18"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 19e9377f7ac42f7999ecc507a3a8aae7cbda8fc4
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="using-a-stored-procedure-with-no-parameters"></a>使用不带参数的存储过程
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  最简单一种的[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]可以调用的存储的过程是指不包含任何参数并返回单个结果集。 [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]提供[SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md)类，该类可用于调用这种类型的存储过程以及如何处理，它返回的数据。  
  
 当使用 JDBC 驱动程序来调用不带参数的存储的过程时，必须使用`call`SQL 转义序列。 语法`call`不带任何参数的转义序列包含，如下所示：  
  
 `{call procedure-name}`  
  
> [!NOTE]  
>  有关 SQL 转义序列的详细信息，请参阅[使用 SQL 转义序列](../../connect/jdbc/using-sql-escape-sequences.md)。  
  
 例如，创建中的以下存储的过程[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]示例数据库：  
  
```  
CREATE PROCEDURE GetContactFormalNames   
AS  
BEGIN  
   SELECT TOP 10 Title + ' ' + FirstName + ' ' + LastName AS FormalName   
   FROM Person.Contact  
END  
```  
  
 此存储过程返回单个结果集，其中包含一列数据（由 Person.Contact 表中前十个联系人的称呼、名称和姓氏组成）。  
  
 在下面的示例中，与的开放连接[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]示例数据库中传递给函数，与[executeQuery](../../connect/jdbc/reference/executequery-method-sqlserverstatement.md)方法用于调用 GetContactFormalNames 存储过程。  
  
```  
public static void executeSprocNoParams(Connection con) {  
   try {  
      Statement stmt = con.createStatement();  
      ResultSet rs = stmt.executeQuery("{call dbo.GetContactFormalNames}");  
  
      while (rs.next()) {  
         System.out.println(rs.getString("FormalName"));  
      }  
      rs.close();  
      stmt.close();  
   }  
   catch (Exception e) {  
      e.printStackTrace();  
   }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [在存储过程中使用语句](../../connect/jdbc/using-statements-with-stored-procedures.md)  
  
  
