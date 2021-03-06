---
title: "使用 SSL 加密 |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e566243-2f93-4b21-8065-3c8336649309
caps.latest.revision: "32"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 2ca2c1c7b566b70b82a70b939c5495e76ce4612a
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="using-ssl-encryption"></a>使用 SSL 加密
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  安全套接字层 (SSL) 加密支持传输加密的数据的实例之间的网络跨[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]和客户端应用程序。  
  
 安全套接字层 (SSL) 是一种协议，用于建立安全通信通道，以防止截获通过网络传输的重要信息或敏感信息以及其他 Internet 通信。 SSL 使客户端和服务器可以验证彼此的身份。 在参与方的身份获得验证之后，SSL 在两者之间提供加密连接，以进行安全的消息传输。  
  
 [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]提供了基础结构来启用和禁用基于指定的用户的特定连接上的加密连接属性及服务器和客户端设置。 用户可以指定证书存储区位置和密码、要用于验证证书的主机名以及何时对通信通道进行加密。  
  
 启用 SSL 加密将增强在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 实例与应用程序之间通过网络传输的数据的安全性。 但是，启用加密的确会降低性能。  
  
 本部分中的主题介绍如何[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]版本支持 SSL 加密，包括新的连接属性和在客户端，你就可以配置信任存储区。  
  
> [!NOTE]  
>  **HostNameInCertificate**建议连接属性验证 SSL 证书。  
  
## <a name="in-this-section"></a>本节内容  
  
|主题|Description|  
|-----------|-----------------|  
|[了解 SSL 支持](../../connect/jdbc/understanding-ssl-support.md)|描述如何[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]支持 SSL 加密。|  
|[使用 SSL 加密进行连接](../../connect/jdbc/connecting-with-ssl-encryption.md)|介绍如何连接到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]数据库使用新的 SSL 特定的连接属性。|  
|[为 SSL 加密配置客户端](../../connect/jdbc/configuring-the-client-for-ssl-encryption.md)|描述如何在客户端配置默认的信任存储区以及如何将私钥证书导入到客户端计算机的信任存储区中。|  
  
## <a name="see-also"></a>另请参阅  
 [保护 JDBC 驱动程序应用程序](../../connect/jdbc/securing-jdbc-driver-applications.md)  
  
  
