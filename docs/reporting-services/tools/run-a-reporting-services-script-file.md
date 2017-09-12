---
title: "运行 Reporting Services 脚本文件 |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scripts [Reporting Services], running
ms.assetid: 0de4995c-85ec-4d4c-aaef-fbd30edfb20f
caps.latest.revision: 36
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: ed67f96cd8487703e81ec702505724725e5c13d3
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="run-a-reporting-services-script-file"></a>运行 Reporting Services 脚本文件
  应使用 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 脚本环境 (RS.exe) 从命令提示符处运行[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 脚本文件。 RS.exe 有许多可供使用的命令提示符参数。 有关命令提示符选项的详细信息，请参阅 [RS.exe 实用工具 (SSRS)](../../reporting-services/tools/rs-exe-utility-ssrs.md)。 有关更多脚本示例，请参阅 [SQL Server Reporting Services Product Samples](http://go.microsoft.com/fwlink/?LinkId=177889)（SQL Server Reporting Services 产品示例）。  
  
## <a name="sample-command-lines"></a>示例命令行  
  
-   在指定目标报表服务器的脚本环境中运行 Script.rss。 默认情况下会应用 Windows 身份验证：  
  
    ```  
    rs –i Script.rss -s http://servername/reportserver  
    ```  
  
-   在指定用来对 Web 服务调用进行身份验证的用户名和密码的脚本环境中运行 Script.rss：  
  
    ```  
    rs –i Script.rss -s http://servername/reportserver -u myusername -p mypassword  
    ```  
  
-   在将服务器超时值指定为 30 秒的脚本环境中运行 Script.rss：  
  
    ```  
    rs –i Script.rss -s http://servername/reportserver -l 30  
    ```  
  
-   在指定名为 *report*的全局脚本变量的脚本环境中运行 Script.rss。  
  
    ```  
    rs –i Script.rss -s http://servername/reportserver -v report="Company Sales"  
    ```  
  
-   在指定以批处理方式运行脚本文件中的 Web 服务操作的脚本环境中运行 Script.rss。  
  
    ```  
    rs –i Script.rss -s http://servername/reportserver -b  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [技术参考 &#40;SSRS &#41;](../../reporting-services/technical-reference-ssrs.md)  
  
  