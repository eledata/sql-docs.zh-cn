---
title: 生成行集的多个结果的命令 |Microsoft 文档
description: 生成行集的多个结果的命令
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: ole-db-commands
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- OLE DB Driver for SQL Server, commands
- OLE DB Driver for SQL Server, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e056aefaf23fc046d8b6760b1c9ba1c7ace52848
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="commands-generating-multiple-rowset-results"></a>生成多个行集结果的命令
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  SQL Server 的 OLE DB 驱动程序可以将从多个行集返回[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]语句。 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 语句在以下条件下返回具有多个行集的结果：  
  
-   以单个命令的形式提交成批的 SQL 语句。  
  
-   存储过程实现一批 SQL 语句。  
  
## <a name="batches"></a>批处理  
 SQL Server 的 OLE DB 驱动程序会将分号字符识别为 SQL 语句的批处理分隔符：  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 通过一个批处理发送多个 SQL 语句比单独执行每个 SQL 语句更有效。 发送一个批处理减少了客户端和服务器之间的网络往返。  
  
## <a name="stored-procedures"></a>存储过程  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 为存储过程中的每个语句返回一个结果集，因此大多数 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 存储过程返回多个结果集。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 IMultipleResults 处理多个结果集](../../oledb/ole-db-commands/using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a>另请参阅  
 [命令](../../oledb/ole-db-commands/commands.md)  
  
  
