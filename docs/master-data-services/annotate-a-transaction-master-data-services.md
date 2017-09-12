---
title: "(Master Data Services) 为事务添加批注 |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
caps.latest.revision: 6
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 279808cca74dbbc7c5ca9aa09c4996660fe949dc
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="annotate-a-transaction-master-data-services"></a>为事务添加批注 (Master Data Services)
  在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中，为保留历史记录的目的而希望提供有关事务的支持详细信息时，可以为事务添加批注。  
  
> [!NOTE]  
>  您无法删除批注。  
  
## <a name="prerequisites"></a>先决条件  
  
-   若要为创建的事务添加批注，您必须有权访问 **“资源管理器”** 功能区域，并且必须至少对要添加批注的模型对象具有 **“更新”** 权限。  
  
-   若要为所有用户的事务添加批注，您必须有权访问 **“版本管理”** 功能区域并且必须是模型管理员。 有关详细信息，请参阅[管理员 (Master Data Services)](../master-data-services/administrators-master-data-services.md)。  
  
### <a name="to-annotate-a-transaction-in-explorer"></a>为资源管理器中为事务添加批注  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 在  主页上，从“模型”列表中，选择模型。  
  
2.   从“版本”列表中，选择某一版本。  
  
3.  单击“资源管理器”。  
  
4.  从菜单栏中指向 **“实体”** ，然后单击包含具有要添加批注的事务的成员的实体。  
  
5.  在网格中，单击该成员所在的行。  
  
6.  单击 **“查看事务”**。  
  
7.  在 **“查看事务”** 对话框中，单击要添加批注的事务。  
  
8.  在该对话框的底部的框中，键入您的批注。  
  
9. 单击 **“添加批注”**。 该批注显示在 **“批注”** 窗格中。  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a>在版本管理中为事务添加批注（仅限管理员）  
  
1.  在 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 主页上，单击 **“版本管理”**。  
  
2.  在菜单栏上，单击 **“事务”**。  
  
3.  在 **“事务”** 窗格中，单击网格中您要添加批注的事务所对应的行。  
  
4.  在 **“事务批注”** 窗格的 **“批注”** 框中，键入您的批注。  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [批注 &#40;Master Data Services &#41;](../master-data-services/annotations-master-data-services.md)   
 [事务 (Master Data Services)](../master-data-services/transactions-master-data-services.md)  
  
  