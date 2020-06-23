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
# <a name="how-to-use-the-channelfactory"></a>Практическое руководство. Использование ChannelFactory
Универсальный класс <xref:System.ServiceModel.ChannelFactory%601> используется в сложных сценариях, требующих создания фабрики каналов, которая может использоваться для создания нескольких каналов.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Создание и использование класса ChannelFactory  
  
1. Создание и запуск службы Windows Communication Foundation (WCF). Дополнительные сведения см. в статьях [проектирование и реализация служб](../designing-and-implementing-services.md), [Настройка служб](../configuring-services.md)и [Размещение](../hosting-services.md)служб.  
  
2. Используйте [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать контракт (интерфейс) для клиента.  
  
3. В коде клиента для создания нескольких прослушивателей конечной точки используйте класс <xref:System.ServiceModel.ChannelFactory%601>.  
  
## <a name="example"></a>Пример  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
