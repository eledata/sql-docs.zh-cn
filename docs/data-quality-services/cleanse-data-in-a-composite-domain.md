---
title: "清理复合域中的数据 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d1076e0-7710-469a-9107-e293e4bd80ac
caps.latest.revision: 14
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 14
---
# 清理复合域中的数据
  本主题提供有关清理 [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) 中的复合域的信息。 一个复合域由两个或更多的单一域构成，并且映射到一个由多个相关字词构成的数据字段。 复合域中的单独的域必须具有一个共同的知识范畴。 有关复合域的详细信息，请参阅 [Managing a Composite Domain](../data-quality-services/managing-a-composite-domain.md)。  
  
##  <a name="Mapping"></a> 将复合域映射到源数据  
 有两种方法可以将源数据映射到复合域：  
  
-   源数据是单个字段（即“全名”），该字段映射到某个复合域。  
  
    -   如果该复合域映射到某一引用数据服务，则源数据将按原样发送到引用数据服务以便进行更正和分析。  
  
    -   如果该复合域未映射到某一引用数据服务，则将基于为该复合域定义的分析方法对复合域进行分析。 有关为复合域指定分析方法的详细信息，请参阅 [Create a Composite Domain](../data-quality-services/create-a-composite-domain.md)。  
  
-   源数据由多个字段构成（例如“名字”、“中名”和“姓氏”），这些字段映射到复合域内的单独域。  
  
 有关如何将复合域映射到源数据的示例，请参阅 [附加域或复合域到引用数据](../data-quality-services/attach-domain-or-composite-domain-to-reference-data.md)。  
  
##  <a name="CDCorrection"></a> 使用明确的跨域规则更正数据  
 通过复合域中的跨域规则，您可以创建指示一个复合域中各域之间的关系的规则。 在您对涉及复合域的源数据运行清理活动时将考虑跨域规则。 除了让您知道跨域规则，明确的有效性 *然后* 跨域规则 **值是否等于**, ，还在数据清理活动期间更正数据。  
  
 请考虑下面的示例：有一个复合域 Product，该复合域有三个单独的域：ProductName、CompanyName 和 ProductVersion。 创建以下明确的跨域规则：  
  
 IF Domain ‘CompanyName’ Value contains *Microsoft* and Domain ‘ProductName’ Value is equal to *Office* and ‘ProductVersion’ Value is equal to *2010* THEN Domain ‘ProductName’ Value is equal to *Microsoft Office 2010*.  
  
 当此跨域规则运行时，源数据 (ProductName) 将在清理活动后进行如下更正：  
  
 **源数据**  
  
|ProductName|CompanyName|ProductVersion|  
|-----------------|-----------------|--------------------|  
|Office|Microsoft Inc.|2010|  
  
 **输出数据**  
  
|ProductName|CompanyName|ProductVersion|  
|-----------------|-----------------|--------------------|  
|Microsoft Office 2010|Microsoft Inc.|2010|  
  
 当您测试明确 *然后* 跨域规则 **值是否等于**, 、 **测试复合域规则** 对话框中包含新列， **更正为**, ，后者将显示正确的数据。 在清理数据质量项目中，此明确的跨域规则更改的数据与 100%置信度和 **原因** 列将显示以下消息︰ 更正规则*\< 跨域规则名称 >*。 有关跨域规则的详细信息，请参阅 [创建跨域规则](../data-quality-services/create-a-cross-domain-rule.md)。  
  
> [!NOTE]  
>  明确的跨域规则将不适用于附加到引用数据服务的复合域。  
  
##  <a name="DataProfiling"></a> 针对复合域的数据事件探查  
 DQS 事件探查提供两种数据质量维度︰ *完整性* （数据是否存在的程度） 和 *准确性* （向其数据可用于目标用途的程度） 在清理活动期间。 事件探查不会提供有关复合域的可靠完整性统计信息。 如果您需要完整性统计信息，请使用单一域而非复合域。 如果您要使用复合域，则最好使用用于进行事件探查的单一域创建一个知识库以确定完整性，并使用复合域创建另一个域来执行清理活动。 例如，使用复合域时，事件探查可能对于地址记录显示 95% 的完整性，但对于其中一列（例如，邮政编码列）可能显示高得多的不完整性。 在此示例中，您可能要衡量单一域的邮政编码列的完整性。  
  
 事件探查可能为复合域提供可靠的准确性统计信息，因为您可以同时为多个列衡量准确性。 此数据的值位于复合聚合中，因此，您最好使用复合域来衡量准确性。  
  
 有关详细信息数据清理活动期间分析请参阅 [探查器统计信息](../data-quality-services/cleanse-data-using-dqs-internal-knowledge.md#Profiler) 中 [使用 DQS 清理数据 & #40; 供内部使用 & #41;知识](../data-quality-services/cleanse-data-using-dqs-internal-knowledge.md)。  
  
  