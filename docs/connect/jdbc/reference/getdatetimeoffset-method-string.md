---
title: "getDateTimeOffset 方法 (String) |Microsoft 文档"
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
ms.assetid: fedb1d75-0c3d-4eb3-ae65-da0e153265cc
caps.latest.revision: "14"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 0b06f3ccc622a7939458d7c478b718dafe2c5f6d
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="getdatetimeoffset-method-string"></a>getDateTimeOffset 方法 (String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  此方法已添加到中[!INCLUDE[msCoName](../../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] JDBC Driver 3.0。  
  
 检索与指定参数的值[DateTimeOffset 类](../../../connect/jdbc/reference/datetimeoffset-class.md)Java 编程语言提供的参数索引中的对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public microsoft.sql.DateTimeOffset getDateTimeOffset(String sCol)  
```  
  
#### <a name="parameters"></a>Parameters  
 *sCol*  
  
 参数的名称。  
  
## <a name="return-value"></a>返回值  
 A [DateTimeOffset 类](../../../connect/jdbc/reference/datetimeoffset-class.md)对象。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 你可以设置[DateTimeOffset 类](../../../connect/jdbc/reference/datetimeoffset-class.md)参数值与[SQLServerCallableStatement.setDateTimeOffset](../../../connect/jdbc/reference/setdatetimeoffset-method-sqlservercallablestatement.md)。  
  
## <a name="see-also"></a>另请参阅  
 [getDateTimeOffset 方法 &#40;SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getdatetimeoffset-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement 成员](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement 类](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
