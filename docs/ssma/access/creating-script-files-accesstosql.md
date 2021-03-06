---
title: "创建脚本文件 (AccessToSQL) |Microsoft 文档"
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssma-access
ms.custom: 
ms.date: 08/17/2017
ms.reviewer: 
ms.suite: sql
ms.technology: sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 64dfe192-965c-49d4-a3ea-848fbc5f619f
caps.latest.revision: "21"
author: Shamikg
ms.author: Shamikg
manager: murato
ms.workload: Inactive
ms.openlocfilehash: d39055374caa0697c073b6abfc8d99e87ed42bb1
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="creating-script-files-accesstosql"></a>创建脚本文件 (AccessToSQL)
第一步是启动 SSMA 控制台应用程序创建脚本文件之前，如果需要创建的变量值文件和服务器连接文件。  
  
脚本文件可分为三部分组成，viz..,:  
  
1.  **配置：**使用户能够设置控制台应用程序的配置参数。  
  
2.  **服务器：**使用户能够设置源/目标服务器定义。 这也可以是在单独的服务器连接文件中。  
  
3.  **脚本命令：**使用户能够执行 SSMA 工作流命令。  
  
下面将详细描述了每个部分：  
  
## <a name="configuring-access-console-settings"></a>配置访问控制台设置  
脚本的配置将显示在控制台脚本文件。  
  
如果在配置节点中指定了任何元素，它们设置为全局设置即它们是适用于所有的脚本命令。 这些配置元素也可以设置在每个命令中的脚本命令部分中，如果用户希望重写的全局设置。  
  
用户可配置选项包括：  
  
1.  **输出窗口提供程序：**如果禁止显示消息属性设置为 'true'，特定于命令的消息执行不显示在控制台上。 属性说明如下所示：  
  
    -   目标： 指定是否需要获取输出到文件或 stdout 输出。 这是默认情况下 false。  
  
    -   文件名称: （可选） 的文件的路径。  
  
    -   禁止显示消息： 不显示在控制台上的消息。 这是 'false'，默认情况下。  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
      <output-window  
  
        suppress-messages="<true/false>"   (optional)  
  
        destination="<file/stdout>"        (optional)  
  
        file-name="<file-name>"            (optional)  
  
       />  
  
    </output-providers>  
    ```  
    *或*  
  
    ```xml  
    <…All commands…>  
  
      <output-window  
  
         suppress-messages="<true/false>"   (optional)  
  
         destination="<file/stdout>"        (optional)  
  
         file-name="<file-name>"            (optional)  
  
       />  
  
    </…All commands…>  
    ```  
  
2.  **数据迁移连接提供程序：**这指定哪些源/目标服务器将被视为对于数据迁移。  源-使用-最后使用指示的最后一个使用的源服务器用于满足数据迁移。 同样目标的使用-最后使用指示的最后一个使用的目标服务器用于满足数据迁移。 用户还可以通过使用属性源服务器或目标服务器指定的服务器 （源或目标）。  
  
    即使用只有一个或其他指定的属性：  
  
    - 源-使用-最后使用 ="true"（默认值） 或源服务器 ="source_servername"  
  
    - 目标-使用-最后使用 ="true"（默认值） 或目标服务器 ="target_servername"  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
      <data-migration-connection   source-use-last-used="true"  
  
                                   target-server="target_1"/>  
  
    </output-providers>  
    ```  
    *或*  
  
    ```xml  
    <migrate-data>  
  
      <data-migration-connection   source-server="source_1"  
  
                                   target-use-last-used="true"/>  
  
    </migrate-data>  
    ```  
  
3.  **用户输入弹出窗口：**这样的错误，处理从数据库加载对象后。 如果是发生错误，控制台将继续按用户指定和用户提供了输入的模式中。  
  
    模式包括：  
  
    -   **要求-用户-**提示用户进行 continue('yes') 或出错 （否）。  
  
    -   **错误-**控制台会显示错误并停止执行。  
  
    -   **继续-**控制台将继续执行。  
  
    默认模式是**错误**。  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
      <user-input-popup mode="<ask-user/continue/error>"/>  
  
    </output-providers>  
    ```  
    *或*  
  
    ```xml  
    <!-- Connect to target database -->  
  
    <connect-target-database server="target_0">  
  
      <user-input-popup mode="<ask-user/continue/error>"/>  
  
    </connect-target-database>  
    ```  
  
4.  **重新连接提供程序：**这样，用户可以设置在发生连接故障的重新连接设置。 这可以为源和目标服务器设置。  
  
    重新连接模式包括：  
  
    -   重新连接到上一次-使用的服务器： 如果连接未处于活动状态的它将尝试重新连接到最后一个使用最多 5 次服务器。  
  
    -   生成一个错误： 如果连接未激活，会生成错误。  
  
    默认模式是**生成一个错误**。  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
     <reconnect-manager on-source-reconnect="<reconnect-to-last-used-server/generate-an-error>"  
  
                        on-target-reconnect="<reconnect-to-last-used-server/generate-an-error>"/>  
  
    </output-providers>  
    ```  
    *或*  
  
    ```xml  
    <!--synchronization-->  
  
    <synchronize-target>  
  
      <reconnect-manager on-target-reconnect="reconnect-to-last-used-server"/>  
  
    </synchronize-target>  
    ```  
    *或*  
  
    ```xml  
    <!--data migration-->  
  
    <migrate-data server="target_0">  
  
      <reconnect-manager  
  
        on-source-reconnect="reconnect-to-last-used-server"  
  
        on-target-reconnect="generate-an-error"/>  
  
    </migrate-data>  
    ```  
  
5.  **转换器覆盖提供程序：**这使用户能够处理已在目标上存在的对象元数据库。 可能的操作包括：  
  
    -   错误： 控制台会显示错误并停止执行。  
  
    -   覆盖： 将覆盖现有对象值。 默认情况下完成此操作。  
  
    -   跳过： 控制台跳过对数据库的已存在的对象  
  
    -   询问用户： 提示用户输入 (是 / 否)  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
      <object-overwrite action="<error|skip|overwrite|ask-user>"/>  
  
    </output-providers>  
    ```  
    *或*  
  
    ```xml  
    <convert-schema object-name="ssma.TT1">  
  
      <object-overwrite action="<error|skip|overwrite|ask-user>"/>  
  
    </convert-schema>  
    ```  
  
6.  **失败的系统必备组件提供程序：**这使用户能够处理任何所需的处理命令的必备项。 默认情况下，严格模式是 'false'。 如果设置为 'true'，异常获取生成失败满足先决条件。  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
      <prerequisites strict-mode="<true|false>"/>  
  
    </output-providers>  
    ```  
  
7.  **停止操作：**中间在操作期间，如果用户想要停止此操作，然后**Ctrl + C**热键可用。 访问控制台的 SSMA 将等待操作完成，然后终止控制台执行。  
  
    如果用户想要执行立即停止，然后， **Ctrl + C**热键可以再次按下的 SSMA 控制台应用程序突然终止。  
  
8.  **进度提供程序：**告知每个控制台命令的进度。 默认情况下禁用该功能。 进度报告属性构成：  
  
    -   off  
  
    -   每隔 1%  
  
    -   每隔 2%  
  
    -   每隔 5%  
  
    -   每隔 10%  
  
    -   每隔 20%  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
     <progress-reporting enable="<true|false>"           (optional)  
  
                         report-messages="<true|false>"  (optional)  
  
                         report-progress="every-1%|every-2%|every-5%|every-10%|every-20%|off" (optional)/>  
  
    </output-providers>  
    ```  
    *或*  
  
    ```xml  
    <…All commands…>  
  
      <progress-reporting  
  
        enable="<true|false>"              (optional)  
  
        report-messages="<true|false>"     (optional)  
  
        report-progress="every-1%|every-2%|every-5%|every-10%|every-20%|off"     (optional)/>  
  
    </…All commands…>  
    ```  
  
9. **记录器详细级别：**设定日志详细级别。 这对应于在 UI 中的所有类别选项。 默认情况下，日志详细级别为"错误"。  
  
    记录器级选项包括：  
  
    -   致命错误： 仅致命错误消息记录。  
  
    -   错误： 记录仅错误和严重错误消息。  
  
    -   警告： 记录除调试和信息消息以外的所有级别。  
  
    -   信息： 只记录调试消息的所有级别。  
  
    -   调试： 记录的消息的所有级别。  
  
    > [!NOTE]  
    > 在任何级别记录必需的消息。  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
      <log-verbosity level="fatal-error/error/warning/info/debug"/>  
  
    </output-providers>  
    ```  
    *或*  
  
    ```xml  
    <…All commands…>  
  
      <log-verbosity level="fatal-error/error/warning/info/debug"/>  
  
    </…All commands…>  
    ```  
  
10. **重写加密密码：**明文密码如果 'true'，指定服务器连接文件的服务器定义部分中或在脚本文件中，如果为加密的密码存储在受保护存储的替代存在。 如果不使用密码以明文形式指定，系统会提示用户输入的密码。  
  
    下面两种情况下出现：  
  
    1.  如果覆盖选项是**false**，搜索的顺序将受保护存储-&gt;脚本文件-&gt;服务器连接文件-&gt;提示用户。  
  
    2.  如果覆盖选项是**true**，搜索的顺序将脚本文件-&gt;服务器连接文件-&gt;提示用户。  
  
    **示例：**  
  
    ```xml  
    <output-providers>  
  
      <encrypted-password override="<true/false>"/>  
  
    </output-providers>  
    ```  
  
非可配置的选项是：  
  
-   **最大重新连接尝试次数：**时建立的连接超时或中断由于网络故障，则需要服务器来重新连接。 重新连接尝试所允许的最大**5**重试后，控制台会自动执行重新连接。 自动重新连接的工具可减少你的工作量中重新运行该脚本。  
  
## <a name="server-connection-parameters"></a>服务器连接参数  
脚本文件中或将服务器连接文件中，可以定义服务器连接参数。 请参阅[创建服务器连接文件 &#40;AccessToSQL &#41;](../../ssma/access/creating-the-server-connection-files-accesstosql.md)有关详细信息部分。  
  
## <a name="script-commands"></a>脚本命令  
脚本文件包含 XML 格式的迁移工作流命令的序列。 SSMA 控制台应用程序处理顺序显示在脚本文件中的命令迁移。  
  
例如，典型的数据迁移的 Access 数据库中的特定表遵循的层次结构： 数据库-&gt;表。  
  
已成功执行脚本文件中的所有命令，SSMA 控制台应用程序退出，并将控制权返回给用户。 脚本文件的内容可能会更多或更少静态变量的信息包含在[变量值文件](http://msdn.microsoft.com/808595c3-8ef1-40bd-a93e-5cf237950e08)或变量值的脚本文件中的单独部分中。  
  
**示例：**  
  
```xml  
<!--Sample of script file commands -->  
  
<ssma-script-file>  
  
  <script-commands>  
  
    <create-new-project project-folder="$project_folder$"  
  
                        project-name="$project_name$"  
  
                        overwrite-if-exists="true"/>  
  
    <connect-source-database server="source_2"/>  
  
    <save-project/>  
  
    <close-project/>  
  
  </script-commands>  
  
</ssma-script-file>  
```  
模板变量值文件和服务器连接文件包含 3 的脚本文件 （用于执行各种方案），提供的产品目录的示例控制台脚本文件夹中：  
  
-   AssessmentReportGenerationSample.xml  
  
-   ConversionAndDataMigrationSample.xml  
  
-   VariableValueFileSample.xml  
  
-   ServersConnectionFileSample.xml  
  
更改为相关性其中显示的参数后，你可以执行模板 （文件）。  
  
在找不到的脚本命令的完整列表[执行 SSMA 控制台 &#40;AccessToSQL &#41;](../../ssma/access/executing-the-ssma-console-accesstosql.md)  
  
## <a name="script-file-validation"></a>脚本文件验证  
用户可以轻松地验证他/她脚本文件的架构定义文件对照**A2SSConsoleScriptSchema.xsd**架构文件夹中可用。  
  
## <a name="next-step"></a>下一步
操作控制台的下一步是[创建变量的值文件 &#40;AccessToSQL &#41;](../../ssma/access/creating-variable-value-files-accesstosql.md).  
  
## <a name="see-also"></a>另请参阅  
[创建变量的值文件 &#40;AccessToSQL &#41;](../../ssma/access/creating-variable-value-files-accesstosql.md)  
  
