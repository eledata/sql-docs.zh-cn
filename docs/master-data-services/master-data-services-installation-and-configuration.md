---
title: "Master Data Services 安装和配置 |Microsoft 文档"
ms.custom:
- SQL2016_New_Updated
ms.date: 07/28/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: f6cd850f-b01b-491f-972c-f966b9fe4190
caps.latest.revision: 44
author: sabotta
ms.author: carlasab
manager: craigg
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 25e5dc869efd2417c47b72c70ede7ba19ab54b46
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="master-data-services-installation-and-configuration"></a>Master Data Services 的安装和配置
  本文介绍了如何在 Windows Server 2012 R2 计算机上安装 [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)] 、设置 MDS 数据库和网站，以及部署示例模型和数据。 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS) 使你的组织能够管理数据的受信任版本。   
  
> [!NOTE] 
> 你可以安装[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]在 Windows 10 上的计算机在使用开发人员版现在支持[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]。 
>>有关详细信息在操作系统上支持不同[!INCLUDE[ssCurrent_md](../includes/sscurrent-md.md)]版本，请参阅[硬件和软件要求安装 SQL Server 2016](../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)。 

有关如何在 [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]中组织数据的概述，请参阅 [Master Data Services 概述 (MDS)](../master-data-services/master-data-services-overview-mds.md)。     
  
 有关 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] 中新增功能的信息，请参阅 [Master Data Services (MDS) 中的新增功能](../master-data-services/what-s-new-in-master-data-services-mds.md)。  
 
有关可帮助你了解 [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)] 的视频以及其他培训资源的链接，请参阅[了解 Master Data Services](../master-data-services/learn-sql-server-master-data-services.md)。 
  
> **下载**  
>-   若要下载 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]，请转到  **[评估中心](https://www.microsoft.com/en-us/evalcenter/evaluate-sql-server-2017-ctp/)**。  
>-   是否拥有 Azure 帐户？  然后转到**[此处](https://azure.microsoft.com/en-us/services/virtual-machines/sql-server/?wt.mc_id=sqL16_vm)**以加速已安装的 SQL server 虚拟机。  
 
> **无法创建 MDS 网站？**
>>请查看此 Microsoft 支持文章以获取有关如何解决此问题的说明。
[无法在 SQL Server 2016 中通过使用低特权帐户创建 MDS 网站](https://aka.ms/mdssupport) 

## <a name="internet-explorer-and-silverlight"></a>Internet Explorer 和 Silverlight
- 当你安装[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]在 Windows Server 2012 计算机上，你可能必须配置 Internet Explorer 增强安全性以允许使用脚本为 Web 应用程序站点。 否则，浏览到服务器计算机上的站点将失败。
- 若要在 Web 应用程序中工作，必须在客户端计算机上安装 Silverlight 5。 如果你没有所需的 Silverlight 版本，将提示您导航到某个区域的 Web 应用程序需要它时安装它。 你可以安装 Silverlight 5 **[此处](https://www.microsoft.com/silverlight/)**。

## <a name="includessmdsshortmdincludesssmdsshort-mdmd-on-an-azure-virtual-machine"></a>[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]Azure 虚拟机上
默认情况下，当你启动了与 Azure 虚拟机[!INCLUDE[ssCurrent_md](../includes/sscurrent-md.md)]已安装，[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]也会安装。 

你下一步是安装 Internet 信息服务 (IIS)。 请参阅[安装和配置 IIS](#InstallIIS)部分。 

如果你感兴趣的安装进行更改[!INCLUDE[ssCurrent_md](../includes/sscurrent-md.md)]，你将在默认位置中，找到的 setup.exe 文件`<drive>`: \SQLServer_13.0_Full。
  
## <a name="InstallMDS"></a>安装 Master Data Services  
 可以使用 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 安装程序安装向导或命令提示符来安装 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]。  
  
 **在 Windows Server 2012 R2 计算机上使用 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 安装程序安装 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]**  
  
1.  双击 Setup.exe，然后按照安装向导中的步骤进行操作。  
  
2.  在“功能选择”页的“共享功能”下，选择 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]。  
  
     将安装 [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]、程序集、Windows PowerShell 管理单元以及 Web 应用程序和服务的文件夹和文件。  
  
     ![mds_SQLServer2016Setup_FeatureSelection](../master-data-services/media/mds-sqlserver2016setup-featureselection.png "mds_SQLServer2016Setup_FeatureSelection")  
  
3.  完成安装向导。  

## <a name="InstallIIS"></a>安装和配置 IIS
  
1.  在 [!INCLUDE[winblue_server_2](../includes/winblue-server-2-md.md)] 中，单击“桌面”上任务栏上的“服务器管理器”图标。  
  
     ![为服务器管理器在 Windows Server 2012 任务栏图标](../master-data-services/media/mds-windowsservertaskbar-servermanagericon.png "为服务器管理器在 Windows Server 2012 任务栏图标")  
  
5.  在“服务器管理器”中，单击“管理”菜单中的“添加角色和功能”。  
   
     ![在服务器管理、 添加角色和功能的菜单命令](../master-data-services/media/mds-servermanagerdashboard-addrolesfeaturesmenu.png "在管理服务器、 添加角色和功能的菜单命令")  
  
6.  在“添加角色和功能向导”的“安装类型”页上，接受默认值（**基于角色或基于功能的安装**），然后单击“下一步”。  
  
7.  单击“从服务器池中选择服务器”，然后单击安装 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 的服务器。  
  
     ![mds_AddRolesFeaturesWizard_ServerSelectionPage](../master-data-services/media/mds-addrolesfeatureswizard-serverselectionpage.png) 
  
8. 上**服务器角色**页上，单击**Web 服务器**，然后单击**下一步**。 

   ![mds_AddRolesFeaturesWizard_ServerRolesPage](../master-data-services/media/mds-addrolesfeatureswizard-serverrolespage.png)
   
9. 上**功能**页上，确认以下功能选择，然后单击**下一步**。 这些功能所需的[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]上[!INCLUDE[winblue_server_2_md](../includes/winblue-server-2-md.md)]。
  
    |功能|功能|  
    |--------------|--------------|  
    |![mds_AddRolesFeaturesWizard_FeaturesPage](../master-data-services/media/mds-addrolesfeatureswizard-featurespage.png)|![mds_AddRolesFeaturesWizard_FeaturesPage_WindowsProcActive](../master-data-services/media/mds-addrolesfeatureswizard-featurespage-windowsprocactive.png)|  

10. 在左侧窗格中，单击**Web 服务器角色 (IIS)** ，然后单击**角色服务**。
11. 上**角色服务**页上，确认以下服务选择，然后单击**下一步**。 这些服务所需的[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]上[!INCLUDE[winblue_server_2](../includes/winblue-server-2-md.md)]。

    > [!WARNING]  
    >  不要安装 WebDAV 发布角色服务。 WebDAV 发布与 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]不兼容。  
  
     |角色服务|角色服务|  
    |-----------------------------|-----------------------------|  
    |![mds_AddRolesFeaturesWizard_RoleServicesPage](../master-data-services/media/mds-addrolesfeatureswizard-roleservicespage.png)|![mds_AddRolesFeaturesWizard_RoleServicesPage_PerformSecurity](../master-data-services/media/mds-addrolesfeatureswizard-roleservicespage-performsecurity.png)|  
    |![mds_AddRolesFeaturesWizard_RoleServicesPage_AppDevsection](../master-data-services/media/mds-addrolesfeatureswizard-roleservicespage-appdevsection.png)|![mds_AddRolesFeaturesWizard_RoleServicesPage_ManageToolssection](../master-data-services/media/mds-addrolesfeatureswizard-roleservicespage-managetoolssection.png)|  
    |||  
  
     所需的功能和角色服务在其他操作系统上的列表，请参阅[Web 应用程序要求 &#40;Master Data Services &#41;](../master-data-services/install-windows/web-application-requirements-master-data-services.md) .   
  
 有关使用安装程序安装 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 的详细信息，请参阅[使用安装向导安装 SQL Server 2016（安装程序）](../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md)。  
  
 有关使用命令提示符安装 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 的详细信息，请参阅[从命令提示符安装 SQL Server 2016](../database-engine/install-windows/install-sql-server-2016-from-the-command-prompt.md)。 使用命令提示符时， [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 作为功能参数提供。  
  
 有关链接到与预安装任务相关的其他信息的简要说明，请参阅 [安装 Master Data Services](../master-data-services/install-windows/install-master-data-services.md)。  
  
##  <a name="SetUpWeb"></a> 设置数据库和网站  
 **使用 [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] 设置数据库和网站**  

 
> [!WARNING]  
    >  你必须[安装 IIS](#InstallIIS)在启动前[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]Configuration Manager。 否则为配置管理器将显示信息的信息服务错误，你将不能创建[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]web 应用程序。  
    
> **浏览器要求**
>>[!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)] Web 的应用程序仅在 Internet Explorer (IE) 9 或更高版本。 不支持 IE 8 及早期版本、 Microsoft Edge 和 Chrome。    
  
1.  启动 [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]，然后单击左窗格中的“数据库配置”。  
  
2.  单击“创建数据库”，然后在“创建数据库向导”中单击“下一步”。  
  
3.  在“数据库服务器”页上，选择“身份验证类型”，然后单击“测试连接”，以确认可以使用所选的身份验证类型的凭据连接到数据库。 单击“下一步” 。
  
    > [!NOTE]  
    >  选择“当前用户 - 集成安全性”作为身份验证类型时，“用户名”框为只读，并且显示登录到计算机的 Windows 用户帐户的名称。 如果你正在运行[!INCLUDE[ssCurrent_md](../includes/sscurrent-md.md)][!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]在 Azure 虚拟机 (VM)，**用户名**框中显示 VM 上的 VM 名称和本地管理员帐户的用户名。 

    ![mds_2016ConfigManager_CreateDatabaseWizard_ServerPage](../master-data-services/media/mds-2016configmanager-createdatabasewizard-serverpage.png)  
  
4.  在“数据库名称”字段中键入名称。 （可选） 若要选择 Windows 排序规则，请清除**SQL Server 默认排序规则**复选框并单击一个或多个可用的选项，例如**区分大小写**。 单击“下一步” 。

    ![mds_2016ConfigManager_CreateDatabaseWizard_DatabasePage](../master-data-services/media/mds-2016configmanager-createdatabasewizard-databasepage.png)  
  
     有关 Windows 排序规则的详细信息，请参阅 [Windows 排序规则名称 (Transact-SQL)](https://msdn.microsoft.com/library/ms188046.aspx)。  
  
5.  在“用户名”字段中，指定将成为 Master Data Services 默认超级用户的用户 Windows 帐户。 超级用户有权访问所有功能区域，并且可以添加、删除和更新所有模型。  

    ![mds_2016ConfigManager_CreateDatabaseWizard_AdminPage](../master-data-services/media/mds-2016configmanager-createdatabasewizard-adminpage.png)  
  
6.  单击**下一步**来查看的设置的摘要[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]数据库，并依次**下一步**以创建数据库。 **进度和完成**页将出现。

7. 创建并配置数据库，单击**完成**。  
  
     有关“创建数据库向导”中的设置的详细信息，请参阅[创建数据库向导（Master Data Services 配置管理器）](../master-data-services/create-database-wizard-master-data-services-configuration-manager.md)。  
  
7.  上**数据库配置**页面[!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]，单击**选择数据库**。  
  
8.  单击**连接**，选择[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]数据库，你在步骤 7 中创建，然后单击**确定**。 

    ![mds_2016ConfigManager_SelectDatabaseButton_ConnectToDatabaseDialog](../master-data-services/media/mds-2016configmanager-selectdatabasebutton-connecttodatabasedialog.png)  
  
     你已经完成了数据库的设置。 “数据库配置”页现在将显示为 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]（创建的数据库和当前的数据库版本）连接的 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 实例。  

    ![mds_2016ConfigManager_DatabaseConfig_Completed](../master-data-services/media/mds-2016configmanager-databaseconfig-completed.png)   
  
9. 在 [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] 中，单击左窗格中的“Web 配置”。  
  
10. 在“网站”列表框中，单击“默认网站”，然后单击“创建”以创建 Web 应用程序。  
  
    > [!NOTE]  
    >  选择“默认网站”时，必须创建一个 Web 应用程序。 如果在列表框中选择“创建新网站”，将自动创建应用程序。  

     ![mds_2016ConfigManager_WebConfig](../master-data-services/media/mds-2016configmanager-webconfig.png)  
  
11. 在“应用程序池”部分中，执行下列操作之一。  
  
    -   为数据库“管理员帐户”输入在第 5 步中输入的同一用户名称，输入密码，然后单击“确定”。  
  
         **- 或 -**  
  
    -   输入不同的用户名称，输入密码，然后单击“确定”。  
  
         创建数据库和 Web 应用程序时，不必使用相同的帐户。  

        ![mds_2016ConfigManager_WebConfig_CreateWebApplication](../master-data-services/media/mds-2016configmanager-webconfig-createwebapplication.png)   
  
     有关“创建 Web 应用程序”对话框的详细信息，请参阅[创建 Web 应用程序对话框（Master Data Services 配置管理器）](../master-data-services/create-web-application-dialog-box-master-data-services-configuration-manager.md)。  
  
12. 在“Web 配置”页的“Web 应用程序”框中，单击已创建的应用程序，然后单击“将应用程序与数据库相关联”部分中的“选择”。  
  
13. 单击“连接”，选择想要与 Web 应用程序相关联的 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 数据库，然后单击“确定”。  
  
     你已经完成了网站的设置。 “Web 配置”页现在将显示你所选的网站、创建的 Web 应用程序以及与应用程序相关联的 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 数据库。  

     ![mds_2016ConfigManager_WebConfig_Completed](../master-data-services/media/mds-2016configmanager-webconfig-completed.png)  
 
     
15. 单击 **“应用”**。 **配置完成**消息框中显示。 单击**确定**在消息框中，以启动 web 应用程序。 网站地址是 http://*server name*/*web application*/。 


![mds_2016ConfigurationComplete_MessageBox](../master-data-services/media/mds-2016configurationcomplete-messagebox.png) 
  
     For more information about the settings on the Web Configuration page, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../master-data-services/web-configuration-page-master-data-services-configuration-manager.md)  
  
 你还可以使用 [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] 指定与 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 数据库相关联的 Web 应用程序和服务的其他设置。 例如，你可以指定加载数据的频率或发送验证电子邮件的频率。 有关详细信息，请参阅[系统设置 (Master Data Services)](../master-data-services/system-settings-master-data-services.md)。  
  
##  <a name="deploySample"></a>部署示例模型和数据  
 以下三个示例模型包都包含在  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中。   这些示例模型包括数据。 **示例模型包的默认位置为 %programfiles%\Microsoft SQL Server\140\Master 数据 Services\Samples\Packages。**
  
-   chartofaccounts_en.pkg  
  
-   customer_en.pkg  
  
-   product_en.pkg  
  
 可以使用 MDSModelDeploy 工具部署这些包。 MDSModelDeploy 工具的默认位置是*驱动器*files\microsoft SQL Server\ 140\Master 数据 Services\Configuration。  
  
 有关运行此工具的先决条件的信息，请参阅 [使用 MDSModelDeploy 部署模型部署包](../master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)。  
  
 有关以支持新功能在对数据所做的更新信息[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]，请参阅[SQL Server 示例： 模型部署包 (MDS)](../master-data-services/sql-server-samples-model-deployment-packages-mds.md)。  
  
 **部署示例模型**  
  
1.  将复制到的示例模型包*驱动器*files\microsoft SQL Server\140\Master 数据 Services\Configuration。  
  
2.  通过运行以下命令打开管理员命令提示符，然后导航到 MDSModelDeploy.exe。  
  
    ```  
    cd c:\Program Files\Microsoft SQL Server\140\Master Data Services\Configuration  
    ```  
  
3.  通过运行以下每个命令将每个示例模型部署到 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 。  
  
    > [!IMPORTANT]  
    >  在下面的示例中，`MDS1` 服务值是指定的。 设置 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 网站时，如果选择了“默认网站”，则使用此值。  请参阅[设置数据库和网站](#SetUpWeb)部分。  
    >   
    >  如果创建了一个新的网站，或选择了另一个现有网站，首先运行以下命令以确定正确的服务值。  
    >   
    >  `MDSModelDeploy listservices`  
    >   
    >  返回的值列表中，第一个服务值为指定用于部署模型的值。  
    >
    > [!NOTE]
    > 若要了解有关详细信息的示例模型的元数据信息，请参阅在此位置"c:\Program Files\Microsoft SQL Server\140\Master 数据 Services\Configuration"可用的自述文件
    >
   
     **部署 chartofaccounts_en.pkg 示例模型**  
  
    ```  
    MDSModelDeploy deploynew -package chartofaccounts_en.pkg -model ChartofAccounts -service MDS1  
    ```  
  
     **部署 customer_en.pkg 示例模型**  
  
    ```  
    MDSModelDeploy deploynew -package customer_en.pkg -model Customer -service MDS1  
    ```  
  
     **部署 product_en.pkg 示例模型**  
  
    ```  
    MDSModelDeploy deploynew -package product_en.pkg -model Product -service MDS1  
  
    ```  
  
     成功部署某一模型后，将显示“MDSModelDeploy 操作已完成”消息。  
  
     下图显示部署 product_en.pkg 示例模型的命令。  
  
     ![命令行部署产品示例模型](../master-data-services/media/mds-commandprompt-deployingsamplemodel-product.png "命令行部署产品示例模型")  
  
4.  若要查看示例模型，执行以下操作。  
  
    1.  导航到你设置的 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 网站。 请参阅 [设置数据库和网站](#SetUpWeb) 部分。  
  
         网站地址是 http://*server name*/*web application*/。  
  
    2.  从“模型”列表框中选择模型，然后单击“资源管理器”。  
  
         ![MDS Web 站点，主页。] (../master-data-services/media/mds-mdswebsite-homepage-selectsamplemodel.png "MDS Web 站点、 主页。")  
  
## <a name="next-step"></a>下一步  
 为你的数据创建一个新的模型和实体。 请参阅[创建模型 (Master Data Services)](../master-data-services/create-a-model-master-data-services.md) 和[创建实体 (Master Data Services)](../master-data-services/create-an-entity-master-data-services.md)。  
  
 有关如何使用模型和实体为 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 中的数据生成结构的概述，请参阅 [Master Data Services 概述 (MDS)](../master-data-services/master-data-services-overview-mds.md)  
  
## <a name="did-this-article-help-you-were-listening"></a>本文是否对你有帮助？ 我们洗耳恭听  
 你正在查找哪些信息，是否已经找到？ 我们不断听取你的反馈来改进内容。 请将你的评论提交到 [sqlfeedback@microsoft.com](mailto:sqlfeedback@microsoft.com?subject=Get%20Started%20with%20Master%20Data%20Services)  
  
## <a name="see-also"></a>另请参阅  
 [Master Data Services 数据库](../master-data-services/master-data-services-database.md)   
 [主数据管理器 Web 应用程序](../master-data-services/master-data-manager-web-application.md)   
 [“数据库配置”页（Master Data Services 配置管理器）](../master-data-services/database-configuration-page-master-data-services-configuration-manager.md)   
 [Master Data Services (MDS) 中的新增功能](../master-data-services/what-s-new-in-master-data-services-mds.md)  
  
  
