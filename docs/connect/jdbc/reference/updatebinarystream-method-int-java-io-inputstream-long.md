---
title: "updateBinaryStream 方法 （int、 java.io.InputStream，长） |Microsoft 文档"
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
ms.assetid: f84cfbe6-ebab-4357-8770-f1db34ecb04f
caps.latest.revision: "20"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 425b6b9c364de4b5a69330c968663a5d532952f3
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="updatebinarystream-method-int-javaioinputstream-long"></a>updateBinaryStream 方法 (int, java.io.InputStream, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  使用将具有指定字节数的二进制流值更新指定列。  
  
## <a name="syntax"></a>语法  
  
```  
  
public void updateBinaryStream(int columnIndex,  
                               java.io.InputStream x,  
                               long length)  
```  
  
#### <a name="parameters"></a>Parameters  
 *列索引*  
  
 **Int** ，该值指示的列索引。  
  
 *x*  
  
 一个 InputStream 对象中。  
  
 *length*  
  
 A**长**，该值指示流的长度。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.ResultSet 接口中的 updateBinaryStream 方法指定此 updateBinaryStream 方法。  
  
 此方法将从 InputStream 对象选择传递字节[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]如二进制、 varbinary、 varbinary （max）、 图像、 xml 和 udt 的二进制列。 此方法不支持更新字符列。 若要更新使用 InputStream 字符列，请使用[updateAsciiStream](../../../connect/jdbc/reference/updateasciistream-method-sqlserverresultset.md)方法。  
  
 流的长度是否不同于中指定了什么*长度*参数，在更新或插入行时的 JDBC 驱动程序引发异常。  
  
 如果流的长度为未知，*长度*参数可能设置为-1，以指示该驱动程序应接受而不考虑其长度流。 与 sqljdbc4.jar，我们建议你使用 JDBC 4.0 方法[updateBinaryStream 方法 &#40; int、 java.io.InputStream &#41;](../../../connect/jdbc/reference/updatebinarystream-method-int-java-io-inputstream.md)当应用程序希望更新的列从一个流，其长度为未知。  
  
## <a name="see-also"></a>另请参阅  
 [updateBinaryStream 方法 &#40;SQLServerResultSet &#41;](../../../connect/jdbc/reference/updatebinarystream-method-sqlserverresultset.md)   
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
