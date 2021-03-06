---
title: 使用 SSMA 项目 (DB2ToSQL) |Microsoft 文档
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssma-db2
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology:
- sql-ssma
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 07abef8a-28e8-4a66-927c-c9a5b8c938ef
caps.latest.revision: 7
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 76642133566117c55fb750d1308e3e9331e1e6de
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="working-with-ssma-projects-db2tosql"></a>使用 SSMA 项目 (DB2ToSQL)
迁移到 DB2 数据库[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]，首先创建新的 SSMA 项目。 项目是一个文件，其中包含以下信息：  
  
-   有关你想要迁移到 DB2 数据库的元数据[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。  
  
-   元数据的目标实例的有关[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]中将接收迁移的对象和数据。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 连接信息。  
  
-   项目设置。  
  
当你打开的项目时，它从 DB2 断开和[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。 允许您在脱机工作。 有关重新连接到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]，请参阅[连接到 SQL Server &#40;DB2eToSQL&#41;](../../ssma/db2/connecting-to-sql-server-db2etosql.md)。  
  
## <a name="reviewing-default-project-settings"></a>查看默认项目设置  
SSMA 进行转换和加载数据库对象、 迁移数据，和与 DB2 同步 SSMA 包含多个设置和[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。 默认设置是适用于多个用户。 但是，在创建新的 SSMA 项目之前，你应查看这些设置。 如果你愿意，你可以更改将用于所有新项目的默认设置。  
  
**若要查看默认项目设置**  
  
1.  上**工具**菜单上，单击**默认项目设置**。  
  
2.  选择中的项目类型**迁移目标版本**下拉列表的设置所需查看或更改，然后单击**常规**选项卡。  
  
3.  在左窗格中，单击**转换**。  
  
4.  在右窗格中，查看并根据需要更改设置。 有关这些设置的详细信息，请参阅[项目设置&#40;转换&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-conversion-db2tosql.md)。  
  
5.  重复步骤 1-3 的迁移、 同步、 加载系统对象、 GUI，和类型映射页。  
  
    -   有关迁移设置的信息，请参阅[项目设置&#40;迁移&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-migration-db2tosql.md)。  
  
    -   有关系统对象设置的信息，请参阅[项目设置&#40;加载系统对象&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-loading-system-objects-db2tosql.md)。  
  
    -   有关同步到的设置信息[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]，请参阅[项目设置&#40;同步&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-synchronization-db2tosql.md)。  
  
    -   有关 GUI 设置的信息，请参阅[项目设置&#40;GUI&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-gui-db2tosql.md)。  
  
    -   有关数据类型映射设置的信息，请参阅[项目设置&#40;类型映射&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-type-mapping-db2tosql.md)。  
  
## <a name="creating-new-projects"></a>创建新项目  
若要迁移到 DB2 数据库中的数据[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]，你必须首先创建一个项目。  
  
**创建项目**  
  
1.  上**文件**菜单上，单击**新项目**。  
  
    此时将显示“新建项目”  对话框。  
  
2.  在**名称**框中，输入你的项目的名称。  
  
3.  在**位置**框中，输入或选择用于该项目的文件夹，然后单击**确定**。  
  
4.  在**迁移到**下拉列表中，选择的目标版本[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]用于迁移。 可用选项包括：  
  
    -   [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 2012  
  
    -   [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 2014  
  
    -   [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 2016  
  
    -   Azure SQL DB  
  
## <a name="customizing-project-settings"></a>自定义项目设置  
除了定义应用于所有新的 SSMA 项目的默认项目设置，你可以自定义的每个项目的设置。 有关详细信息，请参阅[设置项目选项&#40;OracleToSQL&#41; ](../../ssma/oracle/setting-project-options-oracletosql.md)和相关部分。  
  
当你自定义源和目标数据库之间的数据类型映射时，你可以定义在项目、 数据库或对象级别的映射。 有关详细信息，请参阅[映射 DB2 和 SQL Server 数据类型&#40;DB2ToSQL&#41;](../../ssma/db2/mapping-db2-and-sql-server-data-types-db2tosql.md)。  
  
## <a name="saving-projects"></a>保存项目  
保存项目时，SSMA 保留项目设置中，和 （可选） 选择数据库元数据中的项目文件。  
  
**若要保存项目**  
  
-   上**文件**菜单上，单击**保存项目**。  
  
    如果项目中的架构已更改，或尚未转换，SSMA 将提示你用于加载和保存元数据。 加载和保存元数据将让你脱机工作。 它还允许你将完成的项目文件发送给其他人，（如技术支持人员）。 如果系统提示你保存元数据，请执行以下操作：  
  
    1.  显示状态的每个架构**元数据缺少**，选择数据库名称旁边的复选框。  
  
        保存元数据可能需要几分钟。 如果你不想保存元数据，不选中所有复选框。  
  
    2.  单击 **保存** 按钮。  
  
        SSMA 将分析 DB2 架构并将元数据保存到项目文件。  
  
## <a name="opening-projects"></a>打开项目  
当你打开项目时，它已断开连接从 DB2 和[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。 允许您在脱机工作。 若要更新元数据，数据库将对象加载到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。 若要将数据迁移，必须重新连接到 DB2 和[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。  
  
**若要打开的项目**  
  
1.  可使用下列过程之一：  
  
    -   上**文件**菜单上，指向**最近项目**，然后单击你想要打开的项目。  
  
    -   上**文件**菜单上，选择**打开项目**，找到.o2ssproj 项目文件、 选择的文件，然后单击**打开**。  
  
2.  若要重新连接到 DB2，在**文件**菜单上，单击**重新连接到 DB2**。  
  
3.  若要重新连接到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]上**文件**菜单上，单击**重新连接到 SQL Server**。  
  
## <a name="next-step"></a>下一步  
迁移过程的下一步是[连接到 DB2 数据库](http://msdn.microsoft.com/en-us/5eb5801d-f0c3-4127-97c0-0b1ef49f4844)。  
  
## <a name="see-also"></a>另请参阅  
[迁移 DB2 数据库移到 SQL Server &#40;DB2ToSQL&#41;](../../ssma/db2/migrating-db2-databases-to-sql-server-db2tosql.md)  
[连接到 DB2 数据库&#40;DB2ToSQL&#41;](../../ssma/db2/connecting-to-db2-database-db2tosql.md)  
[连接到 SQL Server &#40;DB2eToSQL&#41;](../../ssma/db2/connecting-to-sql-server-db2etosql.md)  
  
