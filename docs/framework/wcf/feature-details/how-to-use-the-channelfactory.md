---
title: Практическое руководство. Использование ChannelFactory
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 4bb2053fb50931756e79d5346a3f14d2acbe04f6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595314"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="a33d3-102">Практическое руководство. Использование ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="a33d3-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="a33d3-103">Универсальный класс <xref:System.ServiceModel.ChannelFactory%601> используется в сложных сценариях, требующих создания фабрики каналов, которая может использоваться для создания нескольких каналов.</span><span class="sxs-lookup"><span data-stu-id="a33d3-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="a33d3-104">Создание и использование класса ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="a33d3-104">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="a33d3-105">Создание и запуск службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a33d3-105">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="a33d3-106">Дополнительные сведения см. в статьях [проектирование и реализация служб](../designing-and-implementing-services.md), [Настройка служб](../configuring-services.md)и [Размещение](../hosting-services.md)служб.</span><span class="sxs-lookup"><span data-stu-id="a33d3-106">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md), [Configuring Services](../configuring-services.md), and [Hosting Services](../hosting-services.md).</span></span>  
  
2. <span data-ttu-id="a33d3-107">Используйте [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать контракт (интерфейс) для клиента.</span><span class="sxs-lookup"><span data-stu-id="a33d3-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="a33d3-108">В коде клиента для создания нескольких прослушивателей конечной точки используйте класс <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="a33d3-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33d3-109">Пример</span><span class="sxs-lookup"><span data-stu-id="a33d3-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
