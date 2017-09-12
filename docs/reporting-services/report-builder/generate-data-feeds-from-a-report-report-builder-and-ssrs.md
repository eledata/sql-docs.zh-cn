---
title: "从报表 （报表生成器和 SSRS） 生成数据馈送 |Microsoft 文档"
ms.custom: 
ms.date: 05/30/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e68baae2-9f2a-4f13-9179-9ac7f29111c5
caps.latest.revision: 11
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: b49b80de8516e14972b05d7ae91f4f72e765803a
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---

# <a name="generate-data-feeds-from-a-report-report-builder-and-ssrs"></a>从报表生成数据馈送（报表生成器和 SSRS）

你可以从分页报表生成 Atom 兼容数据馈送，然后使用应用程序，如 Power Pivot 中的数据馈送或 Power BI 中，可以使用数据源。  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Atom 呈现扩展插件可生成 Atom 服务文档，该文档列出报表中可用的数据馈送。 该文档为报表中的每个数据区域至少列出一个数据馈送。 根据数据区域的类型以及数据区域显示的数据， [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 可以自数据区域生成多个数据馈送。  
  
 Atom 服务文档为每个数据馈送包含一个唯一标识符，在 URL 中使用该标识符可以查看数据馈送的内容。  
  
 有关详细信息，请参阅 [基于报表生成数据馈送（报表生成器和 SSRS）](../../reporting-services/report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md)中处理数据。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-generate-an-atom-service-document"></a>生成 Atom 服务文档  
  
1.  在 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web 门户中，导航到想要生成数据馈送的报表。  
  
2.  单击该报表。  
  
     该报表将运行。  
  
3.  在工具栏上，单击**将导出到数据馈送**图标。  
  
     将出现一条消息，询问是要保存还是要打开包含数据馈送的 Atom 文档。  
  
4.  单击 **“保存”** 可以将文档保存到文件系统，单击 **“打开”** 可以在保存前查看文档内容。 **默认情况下，文档将在浏览器中打开。**  
  
5.  找到保存文档的位置。  
  
6.  或者更改文档的名称。  
  
    > [!NOTE]  
    >  默认情况下，文档名称就是报表名称。  
  
7.  确认文档类型为 **“ATOMSVC 文件”**，然后单击 **“保存”**。  
  
8.  或者，在浏览器或者文本编辑器或 XML 编辑器中打开该 .atomsvc 文件。  
  
### <a name="to-view-an-atom-compliant-data-feed"></a>查看与 Atom 兼容的数据馈送  
  
1.  如果 Atom 服务文档尚未打开，则找到该文档并在 Internet Explorer 之类的浏览器中打开它。  
  
2.  将您要查看的数据馈送的 URL 从 Atom 服务文档复制到浏览器。  
  
     该 URL 的格式如下：  
  
     `http://<server name>/ReportServer?%2f<ReportName>rs%3aCommand=Render&rs%3aFormat=ATOM&rc%3aDataFeed=<Identifier>`  
  
3.  按 Enter。  
  
     将出现一条消息，询问是要保存还是要打开包含数据馈送的 Atom 文档。  
  
4.  单击 **“保存”** 可以将文档保存到文件系统，单击 **“打开”** 可以在保存前查看数据馈送。  
  
5.  找到保存文档的位置。  
  
6.  或者更改文档的名称。  
  
    > [!NOTE]  
    >  默认情况下，文档名称就是报表名称。 如果该 Atom 服务文档具有多个数据馈送，默认情况下它们全都使用相同的名称，即报表名称。 为了区分它们，请重命名这些数据馈送以便使用有意义的名称。  
  
7.  确认文档类型为 **“ATOM 文件”**，然后单击 **“保存”**。  
  
8.  或者，在浏览器或者文本编辑器或 XML 编辑器中打开该 .atom 文件。  

## <a name="next-steps"></a>后续步骤

[导出报表](../../reporting-services/report-builder/export-reports-report-builder-and-ssrs.md)  

更多问题？ [尝试的 Reporting Services 论坛](http://go.microsoft.com/fwlink/?LinkId=620231)