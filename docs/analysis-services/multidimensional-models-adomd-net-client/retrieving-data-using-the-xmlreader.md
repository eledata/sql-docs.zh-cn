---
title: "检索数据使用 XmlReader |Microsoft 文档"
ms.custom: 
ms.date: 02/14/2018
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- retrieving data
- XmlReader object
- data retrieval [ADOMD.NET], XmlReader object
ms.assetid: 420ec40e-be2d-413a-b4b2-6d2b1756e270
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: b5bfef8a355dea36e3444afe4ff32a1e783f96da
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="retrieving-data-using-the-xmlreader"></a>使用 XmlReader 检索数据
  **XmlReader**类的一部分**System.Xml** Microsoft.NET Framework 类库，命名空间是类似于<xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataReader>在于类**XmlReader**类还提供快速、 非缓存、 只进对访问数据。 如果没有数据使用的内存中的分析视图无需<xref:Microsoft.AnalysisServices.AdomdClient.CellSet>对象， **XmlReader**对象非常适用于检索 XML 数据，尤其是对于大量数据。 因为**XmlReader**流式处理数据， **XmlReader**没有用于检索和缓存的所有数据公开给调用方，数据之前，会出现情况<xref:Microsoft.AnalysisServices.AdomdClient.CellSet>对象用于将转换为分析对象模型表示形式的分析响应的 XML。  
  
 **XmlReader**类提供对 XML 分析响应由 ADOMD.NET 接收的直接访问时<xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand.ExecuteXmlReader%2A>方法<xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand>调用对象。 由于接收到的数据为原始 XML 数据，所以必须手动分析这些数据和元数据。 一旦已检索的数据， **XmlReader**应关闭对象。  
  
## <a name="retrieving-data-and-metadata"></a>检索数据和元数据  
 若要使用**XmlReader**类来检索数据，执行以下步骤：  
  
1.  **创建对象的新实例。**  
  
     若要创建的新实例**XmlReader**调用类，<xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand.Execute%2A>或<xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand.ExecuteXmlReader%2A>方法<xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand>对象。  
  
2.  **检索数据。**  
  
     该命令将运行查询并返回后**XmlReader**，必须分析数据和元数据。 XML 数据和元数据由 XML for Analysis 访问接口所使用的本机格式表示。 对于大多数 XML for Analysis 提供程序中，本机格式是**MDDataSet**格式。 **MDDataSet**格式提供数据和元数据格式结构良好的单元集。 有关详细信息**MDDataSet**格式，请参阅 XML for Analysis 规范。  
  
3.  **关闭读取器。**  
  
     始终应调用<xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.Close%2A>方法时使用完**XmlReader**对象。 虽然**XmlReader**是打开，该对话框**XmlReader**具有独占使用<xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>用于运行命令的对象。 你将无法运行任何命令使用该<xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>，包括创建另一个**XmlReader**或<xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataReader>，直到关闭原始**XmlReader**。  
  
### <a name="example-of-retrieving-data-from-the-xmlreader"></a>从 XmlReader 检索数据的示例  
 下面的示例运行命令，并且该数据检索为**XmlReader**，输出到控制台文件的内容。  
  
 [!code-cs[Adomd.NetClient#OutputDataWithXML](../../analysis-services/multidimensional-models-adomd-net-client/codesnippet/csharp/retrieving-data-using-th_1_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [从分析数据源检索数据](../../analysis-services/multidimensional-models-adomd-net-client/retrieving-data-from-an-analytical-data-source.md)   
 [使用单元集中检索数据](../../analysis-services/multidimensional-models-adomd-net-client/retrieving-data-using-the-cellset.md)   
 [使用 AdomdDataReader 检索数据](../../analysis-services/multidimensional-models-adomd-net-client/retrieving-data-using-the-adomddatareader.md)  
  
  
