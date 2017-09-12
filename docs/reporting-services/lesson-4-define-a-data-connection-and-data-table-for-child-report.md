---
title: "第 4 课： 定义子报表的数据连接和数据表 |Microsoft 文档"
ms.custom: 
ms.date: 05/18/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: a6aa2c56-227c-43c5-a28e-c7104131ac5e
caps.latest.revision: 7
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 214067875871c249aa56d0ed191f787a08b3ed7b
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="lesson-4-define-a-data-connection-and-data-table-for-child-report"></a>第 4 课：定义用于子报表的数据连接和数据表
设计父报表后，接下来要创建用于子报表的数据连接和数据表。 在本教程中，数据连接指向 AdventureWorks2014 数据库。  
  
### <a name="to-define-a-data-connection-and-datatable-by-adding-a-dataset-for-child-report"></a>通过添加 DataSet 定义数据连接和 DataTable（用于子报表）  
  
1.  上**网站**菜单上，选择**添加新项**。  
  
2.  在**添加新项**对话框中，选择**数据集**，然后选择**添加**。 出现提示时，你应将项添加到**App_Code**通过选择文件夹**是**。  
  
    此操作将一个新的 XSD 文件 **DataSet2.xsd** 添加到项目，并打开数据集设计器。  
  
3.  从“工具箱”窗口中，将 **TableAdapter** 控件拖到设计图面上。 随后将启动 **TableAdapter** 配置向导。  
  
4.  上**选择你的数据连接**页上，你可以选择在第 2 课中创建的连接。 如果这样做，选择**下一步**并转到步骤 8。 否则，请选择**新连接**。  
  
5.  在**添加连接**对话框框中，执行以下步骤：  
  
    1.  在**服务器名称**框中，输入服务器其中**AdventureWorks2014**数据库所在。  
  
        默认的 SQL Server Express 实例为 **(local)\sqlexpress**。  
  
    2.  在**登录到服务器**部分中，选择提供访问的数据的选项。 **使用 Windows 身份验证**是默认设置。  
  
    3.  从**选择或输入数据库名称**下拉列表中，选择**AdventureWorks2014**。  
  
    4.  选择“确定”，然后选择“下一步”。  
  
6.  如果你选择**使用 SQL Server 身份验证**在步骤 5 (b) 中，选择是在字符串中包含敏感数据还是在应用程序代码中设置信息。  
  
7.  上**将连接字符串保存到应用程序配置文件**页上，键入连接字符串的名称或接受默认值**AdventureWorks2014ConnectionString**。 选择“下一步” 。  
  
8.  上**选择命令类型**页上，选择**使用 SQL 语句**，然后选择**下一步**。  
  
9. 上**输入 SQL 语句**页上，输入下面的 TRANSACT-SQL 查询，来从检索数据**AdventureWorks2014**数据库，，然后选择**下一步**。  
  
    ```  
    SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail  
    ```  
  
    此外可以创建查询，通过选择**查询生成器**，然后通过选择验证查询**执行查询**按钮。 如果查询返回的数据不符合预期，则可能使用的 AdventureWorks 版本较低。 有关如何获取 **AdventureWorks2014** 示例数据库的详细信息，请参阅 [Microsoft SQL Server Database Product Samples](http://msftdbprodsamples.codeplex.com/)（Microsoft SQL Server 数据库产品示例）。  
  
10. 上**选择要生成的方法**页上，取消选中**创建方法以更新将直接发送到数据库 (GenerateDBDirectMethods)**，然后选择**完成**。  
  
    > [!WARNING]  
    > 请务必取消选中**创建方法以更新将直接发送到数据库 (GenerateDBDirectMethods)**  
  
    配置 ADO.NET [DataTable](http://msdn.microsoft.com/library/system.data.datatable.aspx) 作为报表的数据源现已完毕。 在 Visual Studio 中的“数据集设计器”页上，应看到所添加的 **DataTable** ，其中列出在查询中指定的列。 DataSet2 由根据查询从 PurhcaseOrderDetail 表获得的数据组成。  
  
11. 保存该文件。  
  
12. 若要预览的数据，选择**预览数据**上**数据**菜单，然后再选择**预览**。  
  
## <a name="next-task"></a>下一个任务  
您已成功创建了用于子报表的数据连接和数据表。 接下来，将使用报表向导设计子报表。 请参阅 [第 5 课：使用报表向导设计子报表](../reporting-services/lesson-5-design-the-child-report-using-the-report-wizard.md)。  
  

