---
title: 元数据发现 |Microsoft 文档
description: OLE DB 驱动程序的 SQL Server 中的元数据发现
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: oledb|features
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: reference
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c30e231bfe618afc6695921c908eadb5f63bb81d
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="metadata-discovery"></a>元数据发现
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  中的元数据发现改进[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]允许 OLE DB 驱动程序的 SQL Server 应用程序，以确保该列或参数元数据从查询执行返回等同于或在你之前指定的元数据格式与兼容执行查询。 如果执行查询后返回的元数据与执行该查询之前指定的元数据格式不兼容，您将会收到错误。  
  
 在 bcp 和 IBCPSession 和 IBCPSession2 接口中，你现在可以指定延迟读取 （延迟元数据发现） 以避免查询操作的元数据发现。 这样可以提高性能，并避免元数据发现失败。  
  
 如果你开发应用程序使用 SQL Server 的 OLE DB 驱动程序，但连接到服务器的版本早于[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]，元数据发现功能将对应于服务器的版本。  
  
## <a name="remarks"></a>注释   
 [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] 中增强了以下 OLE DB 成员函数，以提供改进的元数据发现：  
  
-   IColumnsInfo::GetColumnInfo  
  
-   IColumnsRowset::GetColumnsRowset  
  
-   ICommandWithParameters::GetParameterInfo (请参阅[ICommandWithParameters](../../oledb/ole-db-interfaces/icommandwithparameters.md)有关详细信息)  
  
 指定使用 IBCPSession::BCPSetBulkMode 的元数据格式时，您还会看到性能提高  
  
 OLE DB 驱动程序的 SQL Server 中的改进的元数据发现可能是因为存在两个存储过程中添加[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:  
  
-   sp_describe_first_result_set  
  
-   sp_describe_undeclared_parameters  
  
## <a name="see-also"></a>另请参阅  
 [适用于 SQL Server 的 OLE DB 驱动程序功能](../../oledb/features/oledb-driver-for-sql-server-features.md)  
  
  
