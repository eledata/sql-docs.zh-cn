---
title: "移动启用了 FILESTREAM 的数据库 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: blob
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-blob
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FILESTREAM [SQL Server], moving a FILESTREAM-enabled database
ms.assetid: dd4d270d-9283-431a-aa6b-e571fced1893
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4db31feef27d115b58f5248e844fa58db7c0c019
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2018
---
# <a name="move-a-filestream-enabled-database"></a>移动启用了 FILESTREAM 的数据库
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
本主题演示如何移动启用了 FILESTREAM 的数据库。  
  
> [!NOTE]  
>  本主题中的示例需要使用在 [创建启用了 FILESTREAM 的数据库](../../relational-databases/blob/create-a-filestream-enabled-database.md)中创建的存档数据库。  
  
### <a name="to-move-a-filestream-enabled-database"></a>移动启用了 FILESTREAM 的数据库  
  
1.  在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中，单击 **“新建查询”** 以打开查询编辑器。  
  
2.  将以下 [!INCLUDE[tsql](../../includes/tsql-md.md)] 脚本复制到查询编辑器中，然后单击“执行”。  此脚本显示 FILESTREAM 数据库所使用的物理数据库文件的位置。  
  
    ```sql  
    USE Archive  
    GO  
    SELECT type_desc, name, physical_name from sys.database_files  
    ```  
  
3.  将以下 [!INCLUDE[tsql](../../includes/tsql-md.md)] 脚本复制到查询编辑器中，然后单击“执行”。  此代码使 `Archive` 数据库脱机。  
  
    ```sql  
    USE master  
    EXEC sp_detach_db Archive  
    GO  
    ```  
  
4.  创建文件夹 `C:\moved_location`，然后将步骤 2 中列出的文件和文件夹移动到该文件夹中。  
  
5.  将以下 [!INCLUDE[tsql](../../includes/tsql-md.md)] 脚本复制到查询编辑器中，然后单击“执行”。  此脚本将 `Archive` 数据库设置为脱机。  
  
    ```sql  
    CREATE DATABASE Archive ON  
    PRIMARY ( NAME = Arch1,  
        FILENAME = 'c:\moved_location\archdat1.mdf'),  
    FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
        FILENAME = 'c:\moved_location\filestream1')  
    LOG ON  ( NAME = Archlog1,  
        FILENAME = 'c:\moved_location\archlog1.ldf')  
    FOR ATTACH  
    GO  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [sp_detach_db (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-detach-db-transact-sql.md)  
  
  
