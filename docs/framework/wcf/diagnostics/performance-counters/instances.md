---
title: Экземпляры
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: f4bf639e626945c7e753ac352dfecc7a79541bfd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266081"
---
# <a name="instances"></a><span data-ttu-id="b8d84-102">Экземпляры</span><span class="sxs-lookup"><span data-stu-id="b8d84-102">Instances</span></span>

<span data-ttu-id="b8d84-103">Имя счетчика: Instances.</span><span class="sxs-lookup"><span data-stu-id="b8d84-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b8d84-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d84-104">Description</span></span>  

 <span data-ttu-id="b8d84-105">Число контекстов экземпляра, которое в настоящий момент содержит служба.</span><span class="sxs-lookup"><span data-stu-id="b8d84-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="b8d84-106">В большинстве случаев число контекстов экземпляра идентично числу экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b8d84-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="b8d84-107">Однако приведенные ниже сценарии являются исключением из этого правила.</span><span class="sxs-lookup"><span data-stu-id="b8d84-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="b8d84-108">Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8d84-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="b8d84-109"><xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8d84-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d84-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b8d84-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
