---
title: "初始化订阅 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: replication
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
caps.latest.revision: 
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9a4258cf4f4e0f52b3501210d4f0ff8423dfb069
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="initialize-subscriptions"></a>初始化订阅
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  必须先初始化订阅服务器，然后才能接收复制的数据。 订阅服务器可以没有初始的数据集，但对于复制的每个对象以及复制所需的任何元数据表和过程，必须要具有相应的架构。  
  
## <a name="options"></a>“常规”  
 **订阅属性**  
 对于需要初始数据集的每个订阅服务器，请选中 **“初始化”** 列中的相应复选框。 如果该复选框为清除状态，将只初始化复制元数据和过程。 有关不使用快照初始化订阅的详细信息，请参阅[初始化事务订阅（不使用快照）](../../relational-databases/replication/initialize-a-transactional-subscription-without-a-snapshot.md)。  
  
 如果在 **“初始化时间”** 列的下拉列表框中选择 **“立即”** ，那么，合并代理或分发代理会在此向导完成后将快照文件传输到订阅服务器。 如果选择 **“首先同步”** ，代理则会在下次计划运行的时候传输文件。 **“立即”** 选项不可用于对 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]的请求订阅。 在 [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]的实例上不能运行合并代理和分发代理，因此必须通过其他方法初始化订阅。  
  
> [!NOTE]  
>  该向导可能会提示您连接到分发服务器，以启动分发代理或合并代理的相应作业。  
  
## <a name="see-also"></a>另请参阅  
 [Create a Pull Subscription](../../relational-databases/replication/create-a-pull-subscription.md)   
 [Create a Push Subscription](../../relational-databases/replication/create-a-push-subscription.md)   
 [初始化订阅](../../relational-databases/replication/initialize-a-subscription.md)   
 [订阅发布](../../relational-databases/replication/subscribe-to-publications.md)  
  
  
