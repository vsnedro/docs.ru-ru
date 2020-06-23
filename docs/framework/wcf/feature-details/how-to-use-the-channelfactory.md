---
title: Практическое руководство. Использование ChannelFactory
description: Узнайте, как создать фабрику каналов для создания более одного канала для доступа к службам с помощью клиента WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7c87026ca4cf7c739f4615da9bc7f0272a382392
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246666"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="3dc64-103">Практическое руководство. Использование ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="3dc64-103">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="3dc64-104">Универсальный класс <xref:System.ServiceModel.ChannelFactory%601> используется в сложных сценариях, требующих создания фабрики каналов, которая может использоваться для создания нескольких каналов.</span><span class="sxs-lookup"><span data-stu-id="3dc64-104">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="3dc64-105">Создание и использование класса ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="3dc64-105">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="3dc64-106">Создание и запуск службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3dc64-106">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="3dc64-107">Дополнительные сведения см. в статьях [проектирование и реализация служб](../designing-and-implementing-services.md), [Настройка служб](../configuring-services.md)и [Размещение](../hosting-services.md)служб.</span><span class="sxs-lookup"><span data-stu-id="3dc64-107">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md), [Configuring Services](../configuring-services.md), and [Hosting Services](../hosting-services.md).</span></span>  
  
2. <span data-ttu-id="3dc64-108">Используйте [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать контракт (интерфейс) для клиента.</span><span class="sxs-lookup"><span data-stu-id="3dc64-108">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="3dc64-109">В коде клиента для создания нескольких прослушивателей конечной точки используйте класс <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="3dc64-109">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dc64-110">Пример</span><span class="sxs-lookup"><span data-stu-id="3dc64-110">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
