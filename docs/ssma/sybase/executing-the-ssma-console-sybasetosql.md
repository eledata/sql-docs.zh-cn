---
title: "执行 SSMA 控制台 (SybaseToSQL) |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
helpviewer_keywords:
- Sybase Console,Database Connection Commands
- Sybase Console,Manageability Commands
- Sybase Console,Migration Commands
- Sybase Console,Migration Preparation Command
- Sybase Console,Project Commands
- Sybase Console,Report Commands
- Sybase Console,Script File Commands
- Sybase Console,Script Generation Commands
ms.assetid: ea8950b7-fabc-4aa4-89f8-9573a2617d70
caps.latest.revision: 22
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 0df634087870db32ed0357c97b1211d4fc1ddcba
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="executing-the-ssma-console-sybasetosql"></a>执行 SSMA 控制台 (SybaseToSQL)
Microsoft 为你提供一组可靠的脚本来执行和控制 SSMA 活动的文件命令。 接下来的部分详细介绍相同。  
  
## <a name="script-file-commands"></a>脚本文件命令  
控制台应用程序在此部分中使用作为枚举的某些标准脚本文件命令。  
  
## <a name="project-commands"></a>项目命令  
创建项目，打开、 保存和退出项目项目命令句柄。  
  
### <a name="create-new-project"></a>创建新的项目  
创建一个新的 SSMA 项目  
  
-   `project-folder`指示获取创建的项目的文件夹。  
  
-   `project-name`指示项目的名称。 {字符串}  
  
-   `overwrite-if-exists`可选特性指示是否应覆盖现有项目。 {布尔值}  
  
-   `project-type:`可选特性。 指示项目类型即"sql server 2005"项目或"sql server 2008"项目或"sql server 2012"项目或"sql server 2014"项目或"sql azure"项目。 默认值为"sql server 2008"。  
  
**示例：**  
  
```xml  
<create-new-project  
  
  project-folder="<project-folder>"  
  
  project-name="<project-name>"  
  
  overwrite-if-exists="<true/false>" (optional)  
  
   project-type=”<sql-server-2008/sql-server-2005/sql-server-2012/sql-server-2014/sql-azure>”  
/>  
```  
覆盖-如果-存在的属性是**false**默认情况下。  
  
属性项目类型是**sql server 2008**默认情况下。  
  
### <a name="open-project"></a>打开项目  
  
-   `project-folder`指示获取创建的项目的文件夹。 如果指定的文件夹不存在，则该命令将失败。  {字符串}  
  
-   `project-name`指示项目的名称。 如果指定的项目不存在，则该命令将失败。  {字符串}  
  
**语法示例：**  
  
```xml  
<open-project  
  
  project-folder="<project-folder>"  
  
  project-name="<project-name>"  
  
/>  
```  
> [!NOTE]  
> Sybase 控制台应用程序的 SSMA 支持向后兼容性。 你将能够打开创建的以前版本的 SSMA 项目。  
  
### <a name="save-project"></a>保存项目  
将保存迁移项目  
  
**语法示例：**  
  
```xml  
<save-project/>  
```  
  
### <a name="close-project"></a>关闭项目  
关闭迁移项目  
  
**语法示例：**  
  
```xml  
<close-project   
  if-modified="<save/error/ignore>"   (optional)  
/>  
```  
如果修改的属性是可选的**忽略**默认情况下。  
  
## <a name="database-connection-commands"></a>数据库连接命令  
数据库连接命令帮助连接到数据库。  
  
> [!NOTE]  
> 1.  **浏览**控制台中不支持的 UI 的功能。  
> 2.  创建脚本文件的详细信息，请参阅[创建脚本文件 &#40;SybaseToSQL &#41;](../../ssma/sybase/creating-script-files-sybasetosql.md).  
  
### <a name="connect-source-database"></a>连接源数据库  
  
-   执行与源数据库的连接并加载的高级别的元数据的源数据库但不是所有元数据。  
  
-   如果无法建立到源的连接，会生成错误并且控制台应用程序会进一步停止执行  
  
从定义的服务器部分中的每个连接的服务器连接文件或脚本文件的名称特性中检索服务器定义。  
  
**语法示例：**  
  
```xml  
<connect-source-database  server="<server-unique-name>"/>  
```  
  
### <a name="force-load-sourcetarget-database"></a>强制负载-源/目标的数据库  
  
-   加载源元数据。  
  
-   用于处理脱机迁移项目。  
  
-   如果无法建立到源/目标连接，会生成错误和控制台应用程序将停止进一步执行  
  
作为命令行参数需要一个或多个元数据库节点。  
  
**语法示例：**  
  
```xml  
<force-load metabase=”<source/target>” >  
  
  <metabase-object object-name="<object-name>"/>  
  
</force-load>  
```  
  
### <a name="reconnect-source-database"></a>重新连接源数据库  
  
-   重新连接到源数据库，但不会加载与连接源数据库命令的任何元数据。  
  
-   如果无法建立 (re) 与源的连接，会生成错误和控制台应用程序将停止进一步执行。  
  
**语法示例：**  
  
```xml  
<reconnect-source-database  server="<server-unique-name>"/>  
```  
  
### <a name="connect-target-database"></a>连接目标数据库  
  
-   连接到目标 SQL Server 数据库，并完全加载的目标数据库的高级别元数据，但不是元数据。  
  
-   如果无法建立到目标连接，会生成错误和控制台应用程序将停止进一步执行。  
  
从定义的服务器部分中的每个连接的服务器连接文件或脚本文件的名称特性中检索服务器定义  
  
**语法示例：**  
  
```xml  
<connect-target-database  server="<server-unique-name>"/>  
```  
  
### <a name="reconnect-target-database"></a>重新连接目标数据库  
  
-   重新连接到目标数据库，但不会加载任何元数据，与不同的是连接目标数据库命令。  
  
-   如果无法建立 (re) 连接到目标，生成错误和控制台应用程序将停止进一步执行。  
  
**语法示例：**  
  
```xml  
<reconnect-target-database  server="<server-unique-name>"/>  
```  
  
## <a name="report-commands"></a>报表命令  
报表命令生成有关各种 SSMA 控制台活动的性能报告。  
  
### <a name="generate-assessment-report"></a>生成评估报表  
  
-   生成对源数据库的评估报表。  
  
-   如果执行此命令，将生成错误并控制台应用程序退出，则不会执行源数据库连接。  
  
-   命令在执行期间，连接到源数据库服务器失败也会导致终止控制台应用程序。  
  
-   `conversion-report-folder:`指定评估报表可以存储在其中的文件夹。（可选属性）  
  
-   `object-name:`指定被认为是评估报表生成 （它可以具有 indivdual 对象名称或组对象名称） 的对象。  
  
-   `object-type:`指定的类型 （如果指定对象类别，则对象类型将为"类别"） 中的对象名称属性指定的对象。  
  
-   `conversion-report-overwrite:`指定是否要覆盖评估报表文件夹，如果它已存在。  
  
    **默认值：** false。 （可选属性）  
  
-   `write-summary-report-to:`指定将生成报表的路径。  
  
    如果只提到的文件夹路径，然后按名称文件**AssessmentReport&lt;n&gt;。XML**创建。 （可选属性）  
  
    报表创建具有两个其他子类别：  
  
    -   `report-errors`（="true/false"，使用默认为"false"（可选属性））  
  
    -   `verbose`（="true/false"，使用默认为"false"（可选属性））  
  
**语法示例：**  
  
```xml  
<generate-assessment-report  
  
  object-name="<object-name>"  
  
  object-type="<object-category>"  
  
  write-summary-report-to="<file-name/folder-name>”             (optional)  
  
  verbose="<true/false>"                       (optional)  
  
  report-errors="<true/false>"                 (optional)  
  
  assessment-report-folder="<folder-name>"          (optional)  
  
  conversion-report-overwrite="<true/false>"   (optional)  
  
/>  
```  
或  
  
```xml  
<generate-assessment-report  
  
  assessment-report-folder="<folder-name>"            (optional)  
  
  conversion-report-overwrite="<true/false>"     (optional)  
  
>  
<metabase-object object-name="<object-name>"  
  
        object-type="<object-category>"/>  
  
</generate-assessment-report>  
```  
  
## <a name="migration-commands"></a>迁移命令  
迁移命令将目标数据库架构转换为源架构，并将数据迁移到目标服务器。  
  
### <a name="convert-schema"></a>转换架构  
  
-   执行架构转换从源到目标架构。  
  
-   如果源或目标数据库连接不执行在执行此命令之前或在命令执行过程中与源或目标数据库服务器的连接失败，则会生成错误并控制台应用程序退出。  
  
-   `conversion-report-folder:`指定评估报表可以存储在其中的文件夹。（可选属性）  
  
-   `object-name:`指定进行转换 （它可以具有 indivdual 对象名称或组对象名称） 的架构被视为源对象。  
  
-   `object-type:`指定的类型 （如果指定对象类别，则对象类型将为"类别"） 中的对象名称属性指定的对象。  
  
-   `conversion-report-overwrite:`指定是否要覆盖评估报表文件夹，如果它已存在。  
  
    **默认值：** false。 （可选属性）  
  
-   `write-summary-report-to:`指定将生成摘要报表的路径。  
  
    如果只提到的文件夹路径，然后按名称文件**SchemaConversionReport&lt;n&gt;。XML**创建。 （可选属性）  
  
    报表创建具有两个其他子类别：  
  
    -   `report-errors`（="true/false"，使用默认为"false"（可选属性））  
  
    -   `verbose`（="true/false"，使用默认为"false"（可选属性））  
  
**语法示例：**  
  
```xml  
<convert-schema  
  
  object-name="<object-name>"  
  
  object-type="<object-category>"  
  write-summary-report-to="<file-name/folder-name>"     (optional)  
  
  verbose="<true/false>"                          (optional)  
  
  report-errors="<true/false>"                    (optional)  
  
  conversion-report-folder="<folder-name>"             (optional)  
  
  conversion-report-overwrite="<true/false>"      (optional)  
  
/>  
```  
或  
  
```xml  
<convert-schema  
  
  conversion-report-folder="<folder-name>"         (optional)  
  
  conversion-report-overwrite="<true/false>"> (optional)  
  
  <metabase-object object-name="<object-name>"  
  
    object-type="<object-category>"/>  
  
</convert-schema>  
```  
  
### <a name="migrate-data"></a>迁移数据  
将源数据迁移到目标。  
  
-   `object-name:`指定被视为用于迁移的源对象数据 （它可以具有 indivdual 对象名称或组对象名称）。  
  
-   `object-type:`指定的类型 （如果指定对象类别，则对象类型将为"类别"） 中的对象名称属性指定的对象。  
  
-   `write-summary-report-to:`指定将生成报表的路径。  
  
    如果只提到的文件夹路径，然后按名称文件**DataMigrationReport&lt;n&gt;。XML**创建。 （可选属性）  
  
    报表创建具有两个其他子类别：  
  
    -   `report-errors`（="true/false"，使用默认为"false"（可选属性））  
  
    -   `verbose`（="true/false"，使用默认为"false"（可选属性））  
  
**语法示例：**  
  
```xml  
<migrate-data  
  
  write-summary-report-to="<file-name/folder-name>"  
  
  report-errors="<true/false>" verbose="<true/false>">  
  
    <metabase-object object-name="<object-name>"/>  
  
    <metabase-object object-name="<object-name>"/>  
  
    <metabase-object object-name="<object-name>"/>  
  
    <data-migration-connection  
  
      source-use-last-used="true"/source-server="<server-unique-name>"  
  
      target-use-last-used="true"/target-server="<server-unique-name>"/>  
  
</migrate-data>  
```  
或  
  
```xml  
<migrate-data  
  
  object-name="<object-name>"  
  
  object-type="<object-category>"  
  
  write-summary-report-to="<file-name/folder-name>"  
  
  report-errors="<true/false>" verbose="<true/false>"/>  
```  
  
## <a name="migration-preparation-command"></a>迁移准备命令  
迁移准备命令会启动源和目标数据库之间的架构映射。  
  
> [!NOTE]  
> 迁移命令设置了默认控制台输出，则与不进行详细的错误报告的完整输出报告： 源对象树的根节点处仅摘要。  
  
### <a name="map-schema"></a>映射架构  
架构映射到目标架构的源数据库。  
  
-   `source-schema`指定我们想要迁移的源架构。  
  
-   `sql-server-schema`指定希望它要迁移的目标架构。  
  
**语法示例：**  
  
```xml  
<map-schema source-schema="<source-schema>"  
  
sql-server-schema="<target-schema>"/>  
```  
  
## <a name="manageability-commands"></a>可管理性命令  
可管理性命令帮助将目标数据库对象与源数据库同步。  
  
> [!NOTE]  
> 迁移命令设置了默认控制台输出，则与不进行详细的错误报告的完整输出报告： 源对象树的根节点处仅摘要。  
  
### <a name="synchronize-target"></a>同步目标  
  
-   将目标对象与目标数据库同步。  
  
-   如果针对源数据库执行此命令，则被遇到错误。  
  
-   如果在执行此命令之前不执行目标数据库连接或连接到的目标数据库服务器在命令执行期间失败，则生成错误并控制台应用程序退出。  
  
-   `object-name:`指定与目标数据库 （它可以具有 indivdual 对象名称或组对象名称） 进行同步视为目标对象。  
  
-   `object-type:`指定的类型 （如果指定对象类别，则对象类型将为"类别"） 中的对象名称属性指定的对象。  
  
-   `on-error:`指定是否为警告或错误指定同步错误。 错误上的可用选项包括：  
  
    -   为警告报告总数  
  
    -   报表-每个-作为-警告  
  
    -   失败脚本  
  
-   `report-errors-to:`为同步操作 （可选） 如果只提供了文件夹路径，然后将文件按名称指定了错误报告位置**TargetSynchronizationReport.XML**创建。  
  
**语法示例：**  
  
```xml  
<synchronize-target  
  
object-name="<object-name>"  
  
on-error="<report-total-as-warning/  
  
report-each-as-warning/  
  
fail-script>" (optional)  
  
  report-errors-to="<file-name/folder-name>"        (optional)  
  
/>  
```  
或  
  
```xml  
<synchronize-target  
  
  object-name="<object-name>"  
  
  object-type="<object-category>"/>  
```  
或  
  
```xml  
<synchronize-target>  
  
  <metabase-object object-name="<object-name>"/>  
  
  <metabase-object object-name="<object-name>"/>  
  
  <metabase-object object-name="<object-name>"/>  
  
</synchronize-target>  
```  
  
### <a name="refresh-from-database"></a>从数据库中刷新  
  
-   刷新数据库中的源对象。  
  
-   如果针对目标数据库执行此命令，则会生成错误。  
  
作为命令行参数需要一个或多个元数据库节点。  
  
-   `object-name:`指定视为刷新从 （它可以具有 indivdual 对象名称或组对象名称） 的源数据库的源对象。  
  
-   `object-type:`指定的类型 （如果指定对象类别，则对象类型将为"类别"） 中的对象名称属性指定的对象。  
  
-   `on-error:`指定是否为警告或错误指定刷新错误。 错误上的可用选项包括：  
  
    -   为警告报告总数  
  
    -   报表-每个-作为-警告  
  
    -   失败脚本  
  
-   `report-errors-to:`刷新操作 （可选） 如果只提供了文件夹路径，然后将文件按名称指定的错误报告的位置**SourceDBRefreshReport.XML**创建。  
  
**语法示例：**  
  
```xml  
<refresh-from-database  
  
  object-name="<object-name>"  
  
  on-error="<report-total-as-warning/  
  
             report-each-as-warning/  
  
             fail-script>"              (optional)  
  
  report-errors-to="<file-name/folder-name>"        (optional)  
  
/>  
```  
或  
  
```xml  
<refresh-from-database  
  
  object-name="<object-name>"  
  
  object-type="<object-category>" />  
```  
或  
  
```xml  
<refresh-from-database>  
  
  <metabase-object object-name="<object-name>"/>  
  
</refresh-from-database>  
```  
  
## <a name="script-generation-commands"></a>脚本生成命令  
脚本生成命令执行双重任务： 它们帮助节省控制台输出在脚本文件;并记录到控制台或基于你指定的参数文件的 T-SQL 的输出。  
  
### <a name="save-as-script"></a>保存为脚本  
用于将对象的脚本保存到文件时提到元数据库 = 目标，这是同步命令，其中在我们获取脚本脚本并在目标数据库上执行相同的替代方法。  
  
作为命令行参数需要一个或多个元数据库节点。  
  
-   `object-name:`指定其脚本将保存的对象。 （它可以具有 indivdual 对象名称或组对象名称）  
  
-   `object-type:`指定的类型 （如果指定对象类别，则对象类型将为"类别"） 中的对象名称属性指定的对象。  
  
-   `metabase:`指定是否它 ithe 源或目标元数据库。  
  
-   `destination:`指定的路径或其中脚本已保存，如果文件没有给定的名称然后文件名格式 （object_name 属性值）.out 中的文件夹  
  
-   `overwrite:`如果为 true 然后它将覆盖如果存在相同的文件名。 它可具有的值 (true/false)。  
  
**语法示例：**  
  
```xml  
<save-as-script  
  
  metabase="<source/target>"  
  
  object-name="<object-name>"  
  
  object-type="<object-category>"  
  
  destination="<file-name/folder-name>"  
  
  overwrite="<true/false>"   (optional)  
  
/>  
```  
或  
  
```xml  
<save-as-script  
  
  metabase="<source/target>"  
  
  destination="<file-name/folder-name>"  
  
    <metabase-object object-name="<object-name>"  
  
                     object-type="<object-category>"/>  
  
</save-as-script>  
```  
  
### <a name="convert-sql-statement"></a>转换 sql 语句  
  
-   `context`指定的架构名称。  
  
-   `destination`指定是否应将输出存储在文件中。  
  
    如果未指定此属性，则在控制台上显示转换后的 T-SQL 的语句。 （可选属性）  
  
-   `conversion-report-folder`指定评估报表可以存储在其中的文件夹。（可选属性）  
  
-   `conversion-report-overwrite`指定是否要覆盖评估报表文件夹，如果它已存在。  
  
    **默认值：** false。 （可选属性）  
  
-   `write-converted-sql-to`指定的文件 （或） 存储转换后的 T-SQL 所在的文件夹路径。 当与指定的文件夹路径`sql-files`属性，每个源文件将具有相应的目标的指定文件夹下创建的 T-SQL 文件。 当与指定的文件夹路径`sql`属性，转换后的 T-SQL 的写入到指定的文件夹下名为 Result.out 的文件。  
  
-   `sql`指定要转换一个或多个语句的 Sybase sql 语句可以使用分隔";"  
  
-   `sql-files`指定的路径的 sql 文件具有要转换为 T-SQL 代码。  
  
-   `write-summary-report-to`指定将生成摘要报表的路径。 如果只提到的文件夹路径，然后按名称文件**ConvertSQLReport.XML**创建。 （可选属性）  
  
    创建具有 2 viz 进一步子类别的摘要报表。。，：  
  
    -   报告错误 （="true/false"，使用默认为"false"（可选属性））。  
  
    -   详细 （="true/false"，使用默认为"false"（可选属性））。  
  
作为命令行参数需要一个或多个元数据库节点。  
  
**语法示例：**  
  
```  
<convert-sql-statement  
  
       context="<database-name>.<schema-name>"  
  
        conversion-report-folder="<folder-name>"  
  
        conversion-report-overwrite="<true/false>"  
  
        write-summary-report-to="<file-name/folder-name>"   (optional)  
  
        verbose="<true/false>"   (optional)  
  
        report-errors="<true/false>"   (optional)  
  
        destination="<stdout/file>"   (optional)  
  
        write-converted-sql-to ="<file-name/folder-name>"  
  
        sql="SELECT 1 FROM DUAL;">  
  
    <output-window suppress-messages="<true/false>" />  
  
</convert-sql-statement>  
```  
或  
  
```  
<convert-sql-statement  
  
         context="<database-name>.<schema-name>"  
  
         conversion-report-folder="<folder-name>"  
  
         conversion-report-overwrite="<true/false>"  
  
         write-summary-report-to="<file-name/folder-name>"   (optional)  
  
         verbose="<true/false>"   (optional)  
  
         report-errors="<true/false>"   (optional)  
  
         destination="<stdout/file>"   (optional)  
  
         write-converted-sql-to ="<file-name/folder-name>"  
  
         sql-files="<folder-name>\*.sql"  
  
/>  
```  
或  
  
```  
<convert-sql-statement  
  
         context="<database-name>.<schema-name>"  
  
         conversion-report-folder="<folder-name>"  
  
         conversion-report-overwrite="<true/false>"  
  
         sql-files="<folder-name>\*.sql"  
  
/>  
```  
  
## <a name="next-step"></a>下一步  
有关命令行选项的信息，请参阅[SSMA 控制台 &#40; 中的命令行选项SybaseToSQL &#41;](../../ssma/sybase/command-line-options-in-ssma-console-sybasetosql.md) .  
  
示例控制台脚本文件的信息，请参阅[使用控制台中的示例脚本文件 &#40;SybaseToSQL &#41;](../../ssma/sybase/working-with-the-sample-console-script-files-sybasetosql.md)  
  
下一步取决于您的项目要求：  
  
-   用于指定的密码或导出 / 导入密码，请参阅[管理密码 &#40;SybaseToSQL &#41;](../../ssma/sybase/managing-passwords-sybasetosql.md).  
  
-   有关生成报表，请参阅[生成报表 &#40;SybaseToSQL &#41;](../../ssma/sybase/generating-reports-sybasetosql.md).  
  
-   有关故障排除控制台中的问题，请参阅[故障排除 &#40;SybaseToSQL &#41;](../../ssma/sybase/troubleshooting-sybasetosql.md).  
  
