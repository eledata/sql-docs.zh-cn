---
title: 安装组件 |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing ODBC components [ODBC], setup program
- ODBC [ODBC], component installation
ms.assetid: 9de15ca0-fe6a-4634-8709-a928d3c9cc73
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 1e8d3c6f5362cef672c5aa02b7547fa86040b4aa
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="installation-components"></a>安装组件
> [!NOTE]  
>  从 Windows XP 和 Windows Server 2003 开始，在 Windows 操作系统中包含 ODBC。 在早期版本的 Windows 上，应仅显式安装 ODBC。  
  
 用户在运行安装程序时，将启动安装过程。 安装程序与结合工作*安装程序 DLL*和*驱动程序安装程序 DLL*每个驱动程序。 安装程序和安装程序 DLL 使用中的自变量**SQLInstallDriverEx**和**SQLInstallTranslatorEx**函数来确定哪些文件将复制或删除每个组件。 下图显示这些安装组件之间的关系。  
  
 ![安装组件之间的关系](../../../odbc/reference/install/media/pr29.gif "pr29")  
  
> [!IMPORTANT]  
>  ODBC 2 中使用 Odbc.inf 文件。*x*来描述所需的每个 ODBC 文件组件中未使用 ODBC 3*.x*。 驱动程序附带 ODBC 3*.x*组件不需要创建一个 Odbc.inf 文件。 删除**SQLInstallDriver**和**SQLInstallODBC**，和的弃用**SQLInstallTranslator**，已呈现 Odbc.inf 不必要。 中现在提供用于 Odbc.inf 驱动程序关键字部分中的驱动程序信息*lpszDriver*中的参数**SQLInstallDriverEx**。 用于在 [ODBC 转换器] 转换器信息和中现在提供 Odbc.inf 转换器规范部分*lpszTranslator*参数**SQLInstallTranslatorEx**。 这些更改允许 ODBC 安装程序可以跨平台更易于移植。  
  
 有关这些组件的详细信息，请参阅本部分末尾的以下主题。  
  
-   [安装程序](../../../odbc/reference/install/setup-program.md)  
  
-   [安装程序 DLL](../../../odbc/reference/install/installer-dll.md)  
  
-   [驱动程序安装程序 DLL](../../../odbc/reference/install/driver-setup-dll.md)
