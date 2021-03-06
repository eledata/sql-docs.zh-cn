---
title: 加载转换到 SQL Server (SybaseToSQL) 数据库对象 |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssma-sybase
ms.reviewer: ''
ms.suite: sql
ms.technology:
- sql-ssma
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
helpviewer_keywords:
- Loading Converted Database Objects
ms.assetid: 4c59256f-99a8-4351-9559-a455813dbd06
caps.latest.revision: 7
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f57bd83c71660e4268758bcf47cd30c2b9b3e1c8
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="loading-converted-database-objects-into-sql-server-sybasetosql"></a>加载转换到 SQL Server (SybaseToSQL) 数据库对象
转换到的 Sybase 自适应 Server Enterprise (ASE) 数据库对象后[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure，你可以将生成数据库对象加载到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure。 您可以让 SSMA 创建对象，或可以编写对象脚本时，还可以自行运行脚本。 此外，SSMA 使你可以更新目标元数据的实际内容[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 数据库。  
  
## <a name="choosing-between-synchronization-and-scripts"></a>同步和脚本之间进行选择  
如果你想要将已转换的数据库对象加载到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或者无需修改的 SQL Azure，您可以使用 SSMA 直接创建或重新创建数据库对象。 此方法可快速且简单，但不允许的自定义项[!INCLUDE[tsql](../../includes/tsql_md.md)]定义的代码[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 对象，而非存储过程。  
  
如果你想要修改[!INCLUDE[tsql](../../includes/tsql_md.md)]用于创建中的对象[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure，或者如果你希望更好地控制何时以及如何在中创建对象[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure，SSMA 用于创建[!INCLUDE[tsql](../../includes/tsql_md.md)]脚本。 然后可以修改这些脚本，每个对象单独创建，并甚至使用[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 代理来计划创建这些对象。  
  
## <a name="using-ssma-to-load-objects-into-sql-server-or-sql-azure"></a>SSMA 用于将对象加载到 SQL Server 或 SQL Azure  
若要使用 SSMA 创建[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 数据库对象，选择中的对象[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 元数据资源管理器，然后同步的对象与[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure，如下面的过程中所示。 默认情况下，如果对象已经存在于[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure，如果 SSMA 元数据具有某些本地更改或更新了这些非常对象的定义，则 SSMA 将 alter 中的对象定义[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure。 你可以通过编辑更改默认行为**项目设置**。  
  
> [!NOTE]  
> 你可以选择现有[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或多个未转换从 ASE 数据库的 SQL Azure 数据库对象。 但是，不会重新创建或更改的 SSMA 这些对象。  
  
**若要使用 SQL Server 或 SQL Azure 同步对象**  
  
1.  在[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 元数据资源管理器，展开顶部[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 节点，然后展开**数据库**。  
  
2.  选择要处理的对象：  
  
    -   若要同步整个数据库，选择数据库名称旁边的复选框。  
  
    -   若要同步或忽略单个对象的类别，选择或清除的对象或文件夹旁边的复选框。  
  
3.  选择要处理中的对象后[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 元数据资源管理器，右键单击**数据库**，然后单击**与数据库的同步**。  
  
    你还可以通过右键单击对象或其父文件夹，然后单击同步单个对象的类别**与数据库的同步**。  
  
    之后，将显示 SSMA**与数据库的同步**对话框中，可以看到两个项的组的位置。 在左侧，SSMA 显示在树中表示的所选的数据库对象。 在右侧，你可以看到表示 SSMA 元数据中的相同对象树。 你可以通过单击左或向右展开树 + 按钮。 同步方向放置在两个树之间的操作列所示。  
  
    一个操作符号可以处于三种状态：  
  
    -   向的左键意味着元数据的内容将保存在数据库 （默认值）。  
  
    -   右箭头意味着数据库内容将覆盖 SSMA 元数据。  
  
    -   交叉登录意味着将执行任何操作。  
  
单击以更改状态的操作符号。 当你单击时，将执行实际同步**确定**按钮**与数据库的同步**对话框。  
  
## <a name="scripting-objects"></a>编写对象脚本  
如果你想要保存[!INCLUDE[tsql](../../includes/tsql_md.md)]定义的转换后的数据库对象，或你想要更改的对象定义和运行脚本自己，可以将已转换的数据库保存到的对象定义[!INCLUDE[tsql](../../includes/tsql_md.md)]脚本。  
  
**若要将对象另存为脚本**  
  
1.  选择要将保存到脚本的对象后，右键单击**数据库**，然后选择**将另存为脚本**。  
  
    你还可以通过右键单击该对象或其包含的文件夹，然后选择脚本单个对象的类别**保存脚本**。  
  
2.  在**另存为**对话框框中，找到你想要保存该脚本中，输入中的文件名称的文件夹**文件名**框中，并依次**确定**。  
  
    SSMA 将追加.sql 文件扩展名。  
  
### <a name="modifying-scripts"></a>修改脚本  
保存后[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]或 SQL Azure 作为一个或多个脚本的对象定义，你可以使用[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)]查看和修改脚本。  
  
**若要修改的脚本**  
  
1.  上[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)]**文件**菜单上，指向**打开**，然后单击**文件**。  
  
2.  在**打开**对话框中，导航到并选择你的脚本文件，然后单击**确定**。  
  
3.  编辑并通过使用查询编辑器的脚本文件。  
  
    关于查询编辑器的详细信息，请参阅"编辑器方便命令和功能"中[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]联机丛书。  
  
4.  若要保存该脚本中，在文件菜单上，选择**保存**。  
  
### <a name="running-scripts"></a>运行脚本  
你可以在运行脚本或单个语句[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)]。  
  
**若要运行脚本**  
  
1.  上[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)]**文件**菜单上，指向**打开**，然后单击**文件**。  
  
2.  在**打开**对话框中，导航到并选择你的脚本文件，然后单击**确定**。  
  
3.  若要运行的完整脚本，按**F5**密钥。  
  
4.  若要运行一组语句，在查询编辑器窗口中，选择语句，，然后按**F5**密钥。  
  
有关如何使用查询编辑器来运行脚本的详细信息，请参阅"[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] [!INCLUDE[tsql](../../includes/tsql_md.md)]查询"中[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]联机丛书。  
  
你可以还使用运行脚本从命令行**sqlcmd**实用程序，并从[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]代理。 有关详细信息**sqlcmd**，请参阅中的"sqlcmd 实用工具"[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]联机丛书。 有关详细信息[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]代理，请参阅"自动执行管理任务 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]代理)"中[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]联机丛书。  
  
## <a name="securing-objects-in-sql-server"></a>保护 SQL Server 中的对象  
你已加载到的已转换的数据库对象后[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]，您可以授予和拒绝对这些对象的权限。 它是一个好办法执行此操作在迁移之前数据到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。 有关如何帮助保护信息中的对象为[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]，请参阅"安全注意事项的数据库和数据库应用程序"中[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]联机丛书。  
  
## <a name="next-step"></a>下一步  
迁移过程的下一步是[迁移 Sybase ASE 数据插入 SQL Server / SQL Azure(SybaseToSQL)](http://msdn.microsoft.com/en-us/54a39f5e-9250-4387-a3ae-eae47c799811)。  
  
## <a name="see-also"></a>另请参阅  
[将 Sybase ASE 数据库迁移到 SQL Server 的 Azure SQL DB &#40;SybaseToSQL&#41;](../../ssma/sybase/migrating-sybase-ase-databases-to-sql-server-azure-sql-db-sybasetosql.md)  
  
