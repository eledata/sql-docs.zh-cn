---
title: 处理结果 |Microsoft 文档
description: 处理结果
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: oledb-driver-for-sql-server
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB Driver for SQL Server, results processing
- OLE DB, processing results
- rowsets [SQL Server], results processing
- results [OLE DB Driver for SQL Server]
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6b564e696b28ca751179376f66458f7b11652ad9
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="processing-results"></a>处理结果
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  如果行集对象是由执行命令或直接从访问接口生成的，则使用者需要检索和访问行集中的数据。  
  
 行集是启用 SQL Server 以公开表格格式的数据用于 OLE DB 驱动程序的中央对象。 从概念上说，行集是指其中的每行都拥有列数据的行的集合。 行集对象公开的接口，如**IRowset** （包含用于按顺序在行集中提取行的方法）， **IAccessor** （允许的一组描述表格数据绑定到使用者程序变量的方法的列绑定的定义）， **IColumnsInfo** （提供在行集中的列的信息），和**IRowsetInfo** （提供有关行集的信息）。  
  
 使用者可以调用**irowset:: Getdata**方法来从行集中的数据行检索到的缓冲区。 之前**GetData**是调用，使用者描述使用一组 DBBINDING 结构的缓冲区。 每个绑定都说明了行集中的列在使用者缓冲区中的存储方式并包含以下内容：  
  
-   应用绑定的列（或参数）的序号。  
  
-   有关绑定内容的信息（例如，数据值、数据长度及其绑定状态）。  
  
-   有关缓冲区中到这些部分中每个部分的偏移量的信息。  
  
-   数据值存在于使用者缓冲区中时的长度和类型。  
  
 获取数据时，访问接口将使用每个绑定中的信息来确定从使用者缓冲区的何处以及如何检索数据。 设置使用者缓冲区中的数据时，访问接口将使用每个绑定中的信息来确定在使用者缓冲区的何处以及如何返回数据。  
  
 指定 DBBINDING 结构后，创建取值函数 (**IAccessor::CreateAccessor**)。 取值函数是一个绑定集合，可用于获取或设置使用者缓冲区中的数据。  
  
## <a name="see-also"></a>另请参阅  
 [为 SQL Server 应用程序创建 OLE DB 驱动程序](../../oledb/ole-db-driver/creating-a-oledb-driver-for-sql-server-application.md)   
 [OLE DB 操作指南主题](../../oledb/ole-db-how-to/ole-db-how-to-topics.md)  
  
  
