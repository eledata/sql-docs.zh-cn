---
title: "用于迁移评估的 PowerShell Cmdlet | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: in-memory-oltp
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 117250d3-9982-47fe-94fd-6f29f6159940
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 63f5604c01bba64b75c51908840b8b9650ed03d2
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2018
---
# <a name="powershell-cmdlet-for-migration-evaluation"></a>用于迁移评估的 PowerShell Cmdlet
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
Save-SqlMigrationReport cmdlet 工具可评估 SQL Server 数据库中多个对象的迁移适用性。 目前，它仅限于评估内存中 OLTP 的迁移适用性。 该 cmdlet 可以在提升的 Windows PowerShell 环境和 sqlps 中运行。  
  
## <a name="syntax"></a>语法  
  
```powershell  
Save-SqlMigrationReport [ -MigrationType OLTP ] [ -Server server -Database database [ -Object object_name ] ]  |  [ -InputObject smo_object ] -FolderPath path  
```  
  
#### <a name="parameters"></a>Parameters  
 下表对这些参数进行了说明。  
  
|Parameters|Description|  
|----------------|-----------------|  
|MigrationType|该 cmdlet 设定为目标的迁移方案的类型。 目前，唯一的值是默认 OLTP。 可选。|  
|“服务器”|目标 SQL Server 实例的名称。 如果未提供 -InputObject 参数，则在 Windows Powershell 环境中为强制参数。 在 SQLPS 中为可选。|  
|“数据库”|目标 SQL Server 数据库的名称。 如果未提供 -InputObject 参数，则在 Windows Powershell 环境中为强制参数。 在 SQLPS 中为可选。|  
|Object|目标数据库对象的名称。 可以是表或存储过程。|  
|InputObject|该 cmdlet 设定为目标的 SMO 对象。 如果未提供 -Server 和 -Database，则在 Windows Powershell 环境中为强制参数。 在 SQLPS 中为可选。|  
|FolderPath|该 cmdlet 应在其中存放所生成的报告的文件夹。 必需的。|  
  
## <a name="results"></a>结果  
 在 FolderPath 参数指定的文件夹中，将有两个文件夹名称：表和存储过程。 如果目标对象是一个表，其报表将位于表文件夹内。 否则它将在存储过程文件夹内。  
  
  
