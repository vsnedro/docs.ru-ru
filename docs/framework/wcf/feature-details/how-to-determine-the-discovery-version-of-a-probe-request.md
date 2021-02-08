---
description: Дополнительные сведения см. в статье как определить версию обнаружения запроса на пробу.
title: Как определить версию обнаружения зондирующего запроса
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: c41283cb84d75dd2dbf7e86da0dec075ab8b6635
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793796"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Как определить версию обнаружения зондирующего запроса

Прокси-сервер обнаружения может выдать несколько конечных точек обнаружения с помощью разных версий обнаружения. Когда запрос проверки многоадресной рассылки UDP поступает на прокси-сервер, прокси-сервер должен ответить с сообщением о подавлении многоадресной рассылки. Для этого ему пришлось бы узнать версию обнаружения запроса.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Определение версии обнаружения зондирующего запроса

В методе, отвечающем на запрос пробы (например <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> ,), используйте свойство static для поиска <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> , как показано в следующем коде.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Реализация прокси-сервера обнаружения](implementing-a-discovery-proxy.md)
