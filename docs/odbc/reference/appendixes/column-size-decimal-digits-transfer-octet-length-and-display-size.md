---
title: 列大小、 十进制数字，传输八位字节长度显示大小 |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- display size of data types [ODBC]
- data types [ODBC], column size
- transfer octet length of data types [ODBC]
- size of data types [ODBC]
- data types [ODBC], display size
- decimal digits of data types [ODBC]
- data types [ODBC], decimal digits
- SQL data types [ODBC], column characteristics
- column size of data types [ODBC]
- data types [ODBC], transfer octet length
ms.assetid: 723107a1-be08-4ea3-a8c0-b2c45d38d1aa
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2ce63d73b21d7eee16d0b17100ff9c18cde265d6
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="column-size-decimal-digits-transfer-octet-length-and-display-size---odbc"></a>列大小、 十进制数，再传输八位字节长度和显示大小-ODBC
数据类型的特征是其列 （或参数） 的大小、 小数位数、 长度、 和显示大小。 以下的 ODBC 函数返回数据源上的这些属性中的 SQL 语句的参数或 SQL 数据类型。 每个 ODBC 函数返回一组不同的这些属性，如下所示：  
  
-   **SQLDescribeCol**返回它所描述的列的大小和十进制数字的列。  
  
-   **SQLDescribeParam**返回它所描述的参数的大小和十进制数字的参数。 **SQLBindParameter** SQL 语句中设置的参数的参数的大小和十进制数字。  
  
-   目录函数**SQLColumns**， **SQLProcedureColumns**，和**SQLGetTypeInfo**表、 结果集或过程参数中返回的列的属性和数据源中的数据类型目录属性中。 **SQLColumns** （如基础表、 视图或系统表） 的指定表中返回的列大小、 十进制数字和的列长度。 **SQLProcedureColumns**在过程中返回的列大小、 十进制数字和的列长度。 **SQLGetTypeInfo**返回的数据源的最大列大小和 SQL 数据类型的最小和最大十进制数字。  
  
 这些函数的列返回的值或参数大小对应于"精度"作为 ODBC 2 中定义。*x*。 但是，值并不一定对应 SQL_DESC_PRECISION 或任何其他一个描述符字段中返回的值中。 同样适用于十进制数字，它们分别对应于"规模"作为 ODBC 2 中定义。*x*。 它不一定对应中 SQL_DESC_SCALE 或任何其他的一个描述符字段，返回的值，但来自不同描述符字段，具体取决于数据类型。 有关详细信息，请参阅[列大小](../../../odbc/reference/appendixes/column-size.md)和[十进制数字](../../../odbc/reference/appendixes/decimal-digits.md)。  
  
 同样，传输八位字节长度的值不是来自 SQL_DESC_LENGTH。 来自的字段的所有字符和二进制类型属性的描述符 SQL_DESC_OCTET_LENGTH。 保存此信息对于其他类型没有描述符字段。  
  
 所有数据类型的显示大小值对应于单个描述符字段，SQL_DESC_DISPLAY_SIZE 中的值。  
  
 描述符字段描述结果集的特征。 描述符字段不包含有关在语句执行之前的数据的有效值。 列的值的大小，十进制数字，和显示大小由**SQLColumns**， **SQLProcedureColumns**，和**SQLGetTypeInfo**、 一端另一方面，返回在数据源的目录中存在的数据库对象，例如表中的列和数据类型的特征。 同样，其结果集中， **SQLColAttribute**返回的列大小、 十进制数字和传输八位字节长度的列在数据源; 这些值不一定是 SQL_DESC_PRECISION，SQL_ 中的值相同DESC_SCALE 和 SQL_DESC_OCTET_LENGTH 描述符字段。  
  
 有关这些描述符字段的详细信息，请参阅[SQLSetDescField](../../../odbc/reference/syntax/sqlsetdescfield-function.md)。  
  
 相关主题：  
  
-   [列大小](../../../odbc/reference/appendixes/column-size.md)  
-   [十进制数字](../../../odbc/reference/appendixes/decimal-digits.md)  
-   [传输八位字节长度](../../../odbc/reference/appendixes/transfer-octet-length.md)  
-   [显示大小](../../../odbc/reference/appendixes/display-size.md)
