---
title: SQLReadFileDSN 函数 |Microsoft 文档
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
apiname:
- SQLReadFileDSN
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLReadFileDSN
helpviewer_keywords:
- SQLReadFileDSN function [ODBC]
ms.assetid: ead464aa-cdc3-47dd-a0c0-997711205d31
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1db13b239a2cf9e1f121336e792333b70f042ed8
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sqlreadfiledsn-function"></a>SQLReadFileDSN 函数
**一致性**  
 版本引入了： ODBC 3.0  
  
 **摘要**  
 **SQLReadFileDSN**从文件 DSN 读取信息。  
  
## <a name="syntax"></a>语法  
  
```  
  
BOOL SQLReadFileDSN(  
     LPCSTR   lpszFileName,  
     LPCSTR   lpszAppName,  
     LPCSTR   lpszKeyName,  
     LPSTR    lpszString,  
     WORD     cbString,  
     WORD *   pcbString);  
```  
  
## <a name="arguments"></a>参数  
 *lpszFileName*  
 [输入]指向包含.dsn 文件的名称的数据缓冲区的指针。 .Dsn 扩展追加到还没有.dsn 扩展的所有文件名。 中的值 *\*lpszFileName*必须是以 null 结尾的字符串。  
  
 *lpszAppName*  
 [输入]指向包含应用程序的名称的数据缓冲区的指针。 ODBC 部分为"ODBC"。 中的值 *\*lpszAppName*必须是以 null 结尾的字符串。  
  
 *lpszKeyName*  
 [输入]指向包含要读取的密钥名称的数据缓冲区的指针。 有关保留关键字，请参见"注释"。 中的值 *\*lpszAppName*必须是以 null 结尾的字符串。  
  
 *lpszString*  
 [输出]指向包含与要读取的键关联的字符串的数据缓冲区的指针。  
  
 如果 *\*lpszFileName*是有效的.dsn 文件名称但*lpszAppName*参数为 null 指针和*lpszKeyName*参数是 null 指针，则 *\*lpszString*包含有效的应用程序的列表。 如果 *\*lpszFileName*有效.dsn 文件的文件名和 *\*lpszAppName*是有效的应用程序名称，但*lpszKeyName*自变量为 null指针，然后 *\*lpszString*包含有效的 DSN 文件，以分号分隔的相应部分中的保留关键字的列表。 如果 *\*lpszFileName*是有效的.dsn 文件名称，但 *\*lpszAppName*是 null 指针和*lpszKeyName*参数为 null 指针，然后 *\*lpszString*包含文件的部分内容 DSN，以分号分隔的列表。  
  
 *cbString*  
 [输入]长度 *\*lpszString*缓冲区。  
  
 *pcbString*  
 [输出]可用于在中返回的字节总数 *\*lpszString*。 可用于返回的字节数是否大于或等于*cbString*中的输出字符串 *\*lpszString*截断为*cbString*减null 终止字符中。 *PcbString*参数可以是 null 指针。  
  
## <a name="returns"></a>返回  
 如果它成功，则返回 FALSE 如果失败，则函数将返回 TRUE。  
  
## <a name="diagnostics"></a>诊断  
 当**SQLReadFileDSN**返回 FALSE，一个关联 *\*pfErrorCode*可通过调用获取值**SQLInstallerError**。 下表列出 *\*pfErrorCode*可以返回的值**SQLInstallerError**并解释此函数的每个上下文中。  
  
|*\*pfErrorCode*|错误|Description|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_GENERAL_ERR|常规安装程序错误|对于发生了错误其中没有任何特定的安装程序错误。|  
|ODBC_ERROR_INVALID_BUFF_LEN|无效的缓冲区长度|*LpszString*自变量为 NULL。<br /><br /> *CbString*自变量为小于或等于 0。|  
|ODBC_ERROR_INVALID_PATH|无效的安装路径|中指定的文件名称的路径*lpszFileName*自变量无效。|  
|ODBC_ERROR_INVALID_REQUEST_TYPE|请求的类型无效|*LpszAppName*自变量为 NULL，而*lpszKeyName*自变量无效。|  
|ODBC_ERROR_OUT_OF_MEM|内存不足|由于内存不足，安装程序无法执行该函数。|  
|ODBC_ERROR_OUTPUT_STRING_TRUNCATED|输出字符串截断|在返回的字符串 *\*lpszString*被截断，因为中的值*cbString*小于或等于中的值 *\*pcbString*.|  
|ODBC_ERROR_REQUEST_FAILED|请求失败|关键字文件 DSN 中不存在。|  
  
## <a name="comments"></a>注释  
 ODBC 保留的节名称 [ODBC] 要在其中存储的连接信息。 本部分的保留的关键字是相同的连接字符串中的保留**SQLDriverConnect**。 (有关详细信息，请参阅[SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md)函数说明。)  
  
 应用程序可以使用这些保留的关键字读取文件 DSN 中的信息。 如果应用程序想要找出文件 DSN，与关联的 dsn 连接字符串可以调用**SQLReadFileDSN**任何 [ODBC] 部分中的保留的连接字符串关键字。 传入的 dsn 连接的完整连接字符串是所有 [ODBC] 部分中的关键字 （保留和特定于驱动程序） 的组合。  
  
## <a name="related-functions"></a>相关函数  
  
|有关信息|请参阅|  
|---------------------------|---------|  
|将信息写入到文件 DSN|[SQLWriteFileDSN](../../../odbc/reference/syntax/sqlwritefiledsn-function.md)|
