---
title: "setClob 方法 （int、 java.io.Reader） |Microsoft 文档"
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
ms.assetid: 2b3727da-0480-4cea-b8b1-abda90699b84
caps.latest.revision: "25"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f6d8078947b6daf7a18d35153e5396e16978b151
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="setclob-method-int-javaioreader"></a>setClob 方法 (int, java.io.Reader)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  将指定的参数设置为指定的读取器对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public final void setClob(int parameterIndex,  
                          java.io.Reader reader)  
```  
  
#### <a name="parameters"></a>Parameters  
 *parameterIndex*  
  
 **Int** ，该值指示参数索引。  
  
 *读取器*  
  
 一个读取器对象。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.PreparedStatement 接口中的 setClob 方法指定此 setClob 方法。  
  
## <a name="see-also"></a>另请参阅  
 [setClob 方法 &#40;SQLServerPreparedStatement &#41;](../../../connect/jdbc/reference/setclob-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement 成员](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)  
  
  
