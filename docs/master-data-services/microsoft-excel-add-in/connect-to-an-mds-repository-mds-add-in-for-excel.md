---
title: "连接到 MDS 存储库 （MDS 外接程序 excel） |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f427312-4c09-4c8b-b9f9-8b235557a74b
caps.latest.revision: 12
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 87931c60b791fd106d0476ac037e1dfcd4041fb2
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="connect-to-an-mds-repository-mds-add-in-for-excel"></a>连接 MDS 存储库（用于 Excel 的 MDS 外接程序）
  在 [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]中，你必须先连接到 MDS 存储库，然后才能加载或发布数据。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程：  
  
-    您必须有权访问“资源管理器”功能区域。  
  
### <a name="to-connect-to-an-mds-repository"></a>连接 MDS 存储库  
  
1.  在 MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]中的 **“主数据”** 选项卡上的 **“连接并加载”** 组中，单击 **“连接”** 按钮下的箭头，然后单击 **“管理连接”**。  
  
2.  在 **“管理连接”** 对话框上的 **“新建连接”** 部分中，单击 **“创建新连接”**。  
  
3.  单击 **“新建”**。  
  
4.  在 **“添加新连接”** 对话框的 **“描述”** 字段中，键入您的连接说明。 在您单击工具栏上的 **“连接”** 按钮后将显示此连接。  
  
5.  在**MDS 服务器地址**框中，键入的 URL [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web 应用程序，例如`http://contoso/mds`。  
  
    > [!NOTE]  
    >  确保使用计算机名称；而不要使用“localhost”。  
  
6.  单击 **“确定”**。 名称将显示在 **“现有连接”** 部分中。  
  
7.  还可以单击 **“测试”** 对连接进行测试。 将显示一个确认或错误对话框。 单击 **“确定”** 将其关闭。  
  
8.  单击 **“连接”**。 随即显示 **Master Data Services** 窗格。  
  
## <a name="next-steps"></a>后续步骤  
  
-   [Export Data to Excel from Master Data Services](../../master-data-services/microsoft-excel-add-in/export-data-to-excel-from-master-data-services.md)  
  
-   [导出前筛选数据（用于 Excel 的 MDS 外接程序）](../../master-data-services/microsoft-excel-add-in/filter-data-before-exporting-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a>另请参阅  
 [连接（用于 Excel 的 MDS 外接程序）](../../master-data-services/microsoft-excel-add-in/connections-mds-add-in-for-excel.md)  
  
  