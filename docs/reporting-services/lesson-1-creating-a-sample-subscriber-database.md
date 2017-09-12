---
title: "第 1 课： 创建示例订阅服务器数据库 |Microsoft 文档"
ms.custom: 
ms.date: 05/30/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: 47a882b7-efe5-4ee6-bef4-06118eb56903
caps.latest.revision: 45
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 4d862dc34dcbb81ce8d50cfac53d81a80f47d29c
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---

# <a name="lesson-1-creating-a-sample-subscriber-database"></a>第 1 课：创建示例订阅服务器数据库

本 [!INCLUDE[ssRSnoversion_md](../includes/ssrsnoversion-md.md)] 教程课程中，会创建一个小型“订阅服务器”数据库，以存储将由数据驱动订阅使用的订阅数据。 处理订阅时，报表服务器将检索此数据并使用它来自定义报表输出。 例如，数据行包含用于筛选器的特定订单编号，以及生成报表将以何种文件格式进行创建。  
  
本课假定你在使用[!INCLUDE[ssManStudioFull_md](../includes/ssmanstudiofull-md.md)]若要创建 SQL Server 数据库。  
  
### <a name="to-create-a-sample-subscriber-database"></a>创建示例订阅服务器数据库  
  
1.  启动 [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]，打开到 [!INCLUDE[ssDEnoversion_md](../includes/ssdenoversion-md.md)]实例的连接。  
  
2.  右键单击数据库，选择**新数据库...**.  
  
3.  在新数据库对话框中，在**数据库名称**，类型*订阅服务器*。 
4. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  单击**新查询**工具栏上的按钮。  
  
6.  将下列 [!INCLUDE[tsql](../includes/tsql-md.md)] 语句复制到空查询中：  
  
    ```  
    Use Subscribers  
    CREATE TABLE [dbo].[OrderInfo] (  
        [SubscriptionID] [int] NOT NULL PRIMARY KEY ,  
        [Order] [nvarchar] (20) NOT NULL,  
        [FileType] [bit],  
        [Format] [nvarchar] (20) NOT NULL ,  
    ) ON [PRIMARY]  
    GO  
  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('1', 'so43659', '1', 'IMAGE')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('2', 'so43664', '1', 'MHTML')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('3', 'so43668', '1', 'PDF')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('4', 'so71949', '1', 'Excel')  
    GO  
    ```  
  
7.  单击**“!执行**工具栏上。  
  
8.  使用 SELECT 语句查看您是否有三行数据。 例如： `select * from OrderInfo`  
  
## <a name="next-steps"></a>后续步骤  
+ 您已成功创建了订阅数据，这些数据将为每个订阅服务器驱动报表分发并改变报表输出。 
+ 下一步，修改报表的数据源属性，以使用已存储凭据。 
+ 您还将修改报表设计以便包括订阅将用于订阅服务器数据的参数。 [第 2 课：修改报表数据源属性](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)。  

## <a name="next-steps"></a>后续步骤

[创建数据驱动的订阅](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md)  
[创建数据库](../relational-databases/databases/create-a-database.md)  
[创建基本表报表](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)  

更多问题？ [尝试的 Reporting Services 论坛](http://go.microsoft.com/fwlink/?LinkId=620231)