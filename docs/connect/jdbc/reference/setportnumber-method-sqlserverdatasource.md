---
title: "setPortNumber 方法 (SQLServerDataSource) |Microsoft 文档"
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
apiname: SQLServerDataSource.setPortNumber
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 59c5fa23-bc1a-4142-af17-70e275f0b833
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6043aa18dd884c593c12cb4badbd78a9dda637f8
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="setportnumber-method-sqlserverdatasource"></a>setPortNumber 方法 (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  设置要用于与通信的端口号[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
  
public void setPortNumber(int portNumber)  
```  
  
#### <a name="parameters"></a>Parameters  
 *端口号*  
  
 **Int**包含端口号的值。  
  
## <a name="remarks"></a>注释  
 端口号是打开到套接字连接时使用的 TCP/IP 端口号[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]。 如果未设置 portNumber 属性， [getPortNumber](../../../connect/jdbc/reference/getportnumber-method-sqlserverdatasource.md)方法返回默认值为 1433年。  
  
> [!NOTE]  
>  该 setPortNumber 方法不执行任何检查传入的端口值的范围。 你可以将传递不是有效的如 99999，而不会触发错误的端口号。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerDataSource 成员](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 类](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
