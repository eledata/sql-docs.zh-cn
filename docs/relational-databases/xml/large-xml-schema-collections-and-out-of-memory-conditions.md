---
title: "大型 XML 架构集合和内存不足的情况 | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: xml
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- out-of-memory conditions
- XML schema collections [SQL Server], large
ms.assetid: 29b9d839-aaaf-48fb-be17-840c751f36f1
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f9aa5cc37b4b2331af28944b97417cfb3acc1034
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2018
---
# <a name="large-xml-schema-collections-and-out-of-memory-conditions"></a>大型 XML 架构集合和内存不足的情况
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
当对大型 XML 架构集合调用内置 XML_SCHEMA_NAMESPACE() 函数时或当您试图删除大型 XML 架构集合时，可能会出现内存不足的情况。 可以使用以下解决方法来处理这种情况：  
  
-   在系统负荷较少时，请使用 DROP_XML_SCHEMA_COLLECTION 命令。 如果该命令执行失败，则请使用 ALTER DATABASE 语句将数据库置于单用户模式，然后再次尝试 DROP XML SCHEMA COLLECTION 命令。 如果 XML 架构集合存在于 **master**、 **model**或 **tempdb**中，则单用户模式还要求重启服务器。  
  
-   当调用 XML_SCHEMA_NAMESPACE 时，您可以尝试检索单个 XML 架构命名空间，或者您也可以在系统负荷更少时尝试调用，或者您还可以在单用户模式下尝试调用。  
  
## <a name="see-also"></a>另请参阅  
 [在服务器上使用 XML 架构集合的要求和限制](../../relational-databases/xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
