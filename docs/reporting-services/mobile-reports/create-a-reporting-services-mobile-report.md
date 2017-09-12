---
title: "创建 Reporting Services 移动报表 |Microsoft 文档"
ms.custom: 
ms.date: 03/30/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e84dc855-aede-4fb4-b721-e6d8787961f4
caps.latest.revision: 10
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 7fce4526bb296113aedb62e5dcf94b50e198210f
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="create-a-reporting-services-mobile-report"></a>创建 Reporting Services 移动报表
借助 SQL Server 移动报表发布服务器，你可以快速创建缩放至任何屏幕的大小，可调整的网格行和列和移动报表元素灵活的设计图面上的 SQL Server 2016 Reporting Services 移动报表。  
  
首次创建移动报表，你可以从 Reporting Services web 门户你本地计算机上安装 SQL Server 移动报表发布服务器。 也可以从 [Microsoft 下载中心](http://go.microsoft.com/fwlink/?LinkID=733527)安装此应用程序。 在首次安装之后，就可以从 Web 门户或本地开始了。   
    
1. 在 Reporting Services web 门户的顶部栏中，选择**新建** > **移动报表**。  
  
   ![PBI_SSMRP_NewMenu](../../reporting-services/mobile-reports/media/pbi-ssmrp-newmenu.png)  
     
2. 上**布局**选项卡移动报表发布服务器中，选择导航器、 仪表、 图表、 地图或数据网格并将其拖到设计网格。  
  
3. 抓住元素的右下角并将其拖到所需大小。  
  
   ![SSMRP_ResizeChart](../../reporting-services/mobile-reports/media/ssmrp-resizechart.png)  
  
   在“主”  设计网格中创建报表中的所需元素。 然后，便可以 [在平板电脑或手机中设计报表](../../reporting-services/mobile-reports/lay-out-a-reporting-services-mobile-report-for-phone-or-tablet.md)。     
     
   在设计网格下方的“可视属性”  中，查看你可以设置的各种属性。  
     
4. 选择**数据**的左上角，和你的选项卡，请参阅图表已具有模拟与之关联的数据。   
  
   ![SSMRP_SimTable](../../reporting-services/mobile-reports/media/ssmrp-simtable.png)  
  
5. 在右上角选择“添加数据”  。  
  
6. 选择“本地 Excel”  或“报表服务器” 。  
  
   >**提示**：如果从 Excel 中添加数据，请确保：  
    >* [准备 Excel 数据](../../reporting-services/mobile-reports/prepare-excel-data-for-reporting-services-mobile-reports.md) 以在移动报表中进行处理。  
    >* 先关闭该文件。  
7. 选择需要的工作表，并选择“导入” 。   
   一次可以从工作簿中添加多个工作表。  
    
     ![SSMRP_AddExcelData](../../reporting-services/mobile-reports/media/ssmrp-addexceldata.png)  
  
8. 仍然在“数据”  选项卡上的“数据属性”  框中，选择该图表所需的表和字段。  
  
   ![SSMRP_DataProps](../../reporting-services/mobile-reports/media/ssmrp-dataprops.png)  
  
9. 返回“布局”  选项卡，在“可视属性”  框中可以设置以下属性，如“标题” 、“时间单位” 和“数字格式” 。  
  
   ![SSMRP_ChartVizProps](../../reporting-services/mobile-reports/media/ssmrp-chartvizprops.png)  
    
10. 在左上角选择“预览”  以查看报表如何成形。  
  
11. 保存报表的时间。 在左上角选择“保存”图标，然后选择“保存在本地”  或“保存到服务器” 。  
  
   若要将其保存到服务器，你需要访问 SQL Server 2016 Reporting Services 报表服务器。  
     
   ### <a name="see-also"></a>另请参阅  
     
-   [使用 SQL Server 移动报表发布服务创建和发布移动报表](../../reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher.md)  
-   [为手机或平板电脑设计 Reporting Services 移动报表](../../reporting-services/mobile-reports/lay-out-a-reporting-services-mobile-report-for-phone-or-tablet.md)  
  
   