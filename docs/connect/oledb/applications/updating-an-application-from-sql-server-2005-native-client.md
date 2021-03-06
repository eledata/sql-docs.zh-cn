---
title: 更新应用程序从 SQL Server 2005 的本机客户端 |Microsoft 文档
description: 更新应用程序从 SQL Server 2005 Native Client
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: oledb|applications
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB Driver for SQL Server, updating applications
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e583abd0a5d84d4842a441fcb8093bbfcf6b9b26
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="updating-an-application-from-sql-server-2005-native-client"></a>从 SQL Server 2005 Native Client 更新应用程序
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  本主题讨论为以来的 SQL Server 的 OLE DB 驱动程序中的重大更改[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]中本机客户端[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]。  

 当你升级到 OLE DB 驱动程序的 SQL Server 从 Microsoft 数据访问组件 (MDAC) 时，你可能还会看到某些的行为差异。 有关详细信息，请参阅[更新为 OLE DB 驱动程序的应用程序适用于 SQL Server 从 MDAC](../../oledb/applications/updating-an-application-to-oledb-driver-for-sql-server-from-mdac.md)。  

 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 本机客户端 9.0 附带[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]。 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0 附带[!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]。  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.5 随 [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] 附带。 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 11.0 随 [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] 和 [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] 附带。  

|SQL Server 相比更改在 OLE DB 驱动程序中的行为[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]本机客户端|Description|  
|------------------------------------------------------------------------------------|-----------------|  
|OLE DB 仅填充到定义的小数位数。|转换后的数据发送到服务器的位置的转换，OLE DB 驱动程序的 SQL Server 来填充仅之前的最大长度的数据中的尾随零**datetime**值。 SQL Server Native Client 9.0 则填充到 9 位数。|  
|验证 ICommandWithParameter::SetParameterInfo DBTYPE_DBTIMESTAMP。|OLE DB 驱动程序的 SQL Server 实现的 OLE DB 要求*bScale*中 ICommandWithParameter::SetParameterInfo 以设 DBTYPE_DBTIMESTAMP 秒的小数部分的精度。|  
|**Sp_columns**存储过程现在返回**"否"**而不是**"否"** IS_NULLABLE 列。|OLE DB 驱动程序中的 SQL Server， **sp_columns**存储过程现在返回**"否"**而不是**"否"** IS_NULLABLE 列。|  
|SQLSetDescRec、 SQLBindParameter 和 SQLBindCol 现在执行一致性检查。|之前[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client 10.0，设置 SQL_DESC_DATA_PTR 不会在 SQLSetDescRec、 SQLBindParameter 或 SQLBindCol 导致任何描述符类型的一致性检查。|  
|SQLCopyDesc 现在执行描述符一致性检查。|之前[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client 10.0，SQLCopyDesc 未执行操作一致性检查特定的记录上设置 SQL_DESC_DATA_PTR 字段时。|  
|SQLGetDescRec 不再不描述符一致性检查。|之前[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client 10.0，当设置了 SQL_DESC_DATA_PTR 字段 SQLGetDescRec 执行描述符一致性检查。 这不是 ODBC 规范和 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0 ([!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]) 以及更高版本所要求的，该一致性检查不再执行。|  
|日期超出范围时返回其他错误。|有关**datetime** ，不同的错误号将返回类型的 OLE DB 驱动程序适用于 SQL Server 超出范围日期比在早期版本中返回。<br /><br /> 具体而言，[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]本机客户端 9.0 所有超出范围中的字符串转换到的年份值返回 22007 **datetime**，并当日期在支持的范围内时，OLEDB驱动程序的SQLServer返回22008**datetime2**但在支持范围之内**datetime**或**smalldatetime**。|  
|**datetime**值将截断秒的小数部分，并且不 round 如果舍入将会更改在一天。|之前[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client 10.0，供客户端行为**datetime**发送到服务器的值是四舍五入为最接近的 1/300 秒。 在 OLE DB 驱动程序的 SQL Server，这种情况下会导致秒的小数部分被截断，如果舍入更改一天。|  
|可能的秒 trunction **datetime**值。|生成的 SQL Server 的连接到 OLE DB 驱动程序的应用程序[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]2005年服务器将会截断秒和小数秒的时间部分的数据发送到服务器，如果将绑定到 datetime 列，但 DBTYPE_DBTIMESTAMP （类型标识符OLE DB) 或 SQL_TIMESTAMP (ODBC) 和小数位数为 0。<br /><br /> 例如：<br /><br /> 输入数据：1994-08-21 21:21:36.000<br /><br /> 插入的数据：1994-08-21 21:21:00.000|  
|从 DBTYPE_DBTIME 到 DBTYPE_DATE 的 OLE DB 数据转换不会再导致日期发生更改。|在 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0 之前，如果 DBTYPE_DATE 的时间部分是在距离午夜的半秒内，则 OLE DB 转换代码将导致日期发生更改。 OLE DB 驱动程序中的 SQL Server，天将不更改 （截断秒的小数部分并且不进行舍入）。|  
|IBCPSession::BCColFmt 转换更改。|在 OLE DB 驱动程序的 SQL Server，当你使用 IBCPSession::BCOColFmt 将 SQLDATETIME 或 SQLDATETIME 转换为字符串类型，被导出小数部分值。 例如，当转换键入 SQLDATETIME 类型 SQLNVARCHARMAX，之前的版本[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]返回的 Native Client 10.0<br /> 1989-02-01 00:00:00.<br />OLE DB 驱动程序的 SQL Server 返回 <br />1989-02-01 00:00:00.0000000.|  
|使用 BCP API 的自定义应用程序现在可以看到警告。|对于所有类型，如果数据长度超过某字段的指定长度，则 BCP API 将生成警告消息。 以前，该警告仅针对字符类型，而不会针对所有类型发出。|  
|插入到空字符串**sql_variant**绑定是日期/时间类型生成错误。|在[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]本机客户端 9.0，插入到空字符串**sql_variant**绑定日期/时间类型未生成错误。 OLE DB 驱动程序的 SQL Server 将在此情况下正确生成错误。|  
|当有触发器运行时，[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 可能会返回不同的结果。|在中引入的更改[!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]可能会导致应用程序具有不同的结果从导致触发器时要运行的语句返回**NOCOUNT OFF**已起作用。 在这种情况下，您的应用程序可能会生成错误。 若要解决此错误，将设置**NOCOUNT ON**触发器或调用 SQLMoreResults 以转到下一个结果中。|  

## <a name="see-also"></a>另请参阅   
 [适用于 SQL Server 的 OLE DB 驱动程序编程](../../oledb/oledb-driver-for-sql-server-programming.md)
