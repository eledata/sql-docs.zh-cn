---
title: "catalog.object_versions（SSISDB 数据库）| Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: system-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 2fd8c020-1c77-4702-8e6b-efa6a348daab
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a8a790874900f5fc69e4f8e50d4f84d835d63c1a
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="catalogobjectversions-ssisdb-database"></a>catalog.object_versions（SSISDB 数据库）
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  显示 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 目录中对象的版本。 在此版本中，此视图只支持项目的版本。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|object_version_lsn|**bigint**|对象版本的唯一标识符 (ID)。 此数字不保证是按顺序排列的。|  
|object_id|**bigint**|对象的唯一 ID。|  
|object_type|**int**|对象的类型。 将针对项目显示值 `20`。|  
|object_name|**sysname(nvarchar(128))**|对象的名称。|  
|description|**nvarchar(1024)**|项目的说明。|  
|created_by|**nvarchar(128)**|向目录添加对象的用户名。|  
|created_time|**datetimeoffset**|将对象添加到目录中的日期和时间。|  
|restored_by|**nvarchar(128)**|还原对象的用户名。|  
|last_restored_time|**datetimeoffset**|上次还原对象的日期和时间。|  
  
## <a name="remarks"></a>Remarks  
 此视图对于目录中的每个对象版本显示一行。  
  
## <a name="permissions"></a>权限  
 若要查看此视图中的行，您必须具有以下权限之一：  
  
-   针对对象的 READ 权限  
  
-   ssis_admin 数据库角色的成员资格  
  
-   sysadmin 服务器角色中的成员资格。  
  
> [!NOTE]  
>  将实施行级安全性；只显示您有权查看的行。  
  
  
