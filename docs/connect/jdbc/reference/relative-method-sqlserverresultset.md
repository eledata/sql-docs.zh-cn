---
title: "相对方法 (SQLServerResultSet) |Microsoft 文档"
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
apiname: SQLServerResultSet.relative
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 2bcdbb69-95fd-4ae8-8488-1a75a91fe2e0
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 8c6d936c5e44996a56ac6d9c653cc25ba7176aa4
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="relative-method-sqlserverresultset"></a>相对方法 (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  将游标沿正向或反向移动相对于当前行的指定行数。  
  
## <a name="syntax"></a>语法  
  
```  
  
public boolean relative(int nRows)  
```  
  
#### <a name="parameters"></a>Parameters  
 *nRows*  
  
 **Int** ，该值指示要移动的行数。  
  
## <a name="return-value"></a>返回值  
 **true**如果光标位于行上。 否则为 **false**。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.ResultSet 接口中的相对方法指定此相对方法。  
  
 如果尝试移到结果集中的第一行之前或最后一行之后，将使游标移到第一行之前或最后一行之后。 调用`relative(0)`有效，但不会更改光标位置。  
  
 调用方法`relative(1)`等同于调用[下一步](../../../connect/jdbc/reference/next-method-sqlserverresultset.md)方法。 调用方法`relative(-1)`等同于调用[以前](../../../connect/jdbc/reference/previous-method-sqlserverresultset.md)方法。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
