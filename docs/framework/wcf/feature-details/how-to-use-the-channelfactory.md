---
title: Практическое руководство. Использование ChannelFactory
description: Узнайте, как создать фабрику каналов для создания более одного канала для доступа к службам с помощью клиента WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: dd767443fefb16ebc02300bffa4264357f12c3ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280589"
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
