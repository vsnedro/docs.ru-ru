---
title: Как определить версию обнаружения зондирующего запроса
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 2b7e42714ae1d16a84bcb6f0fc79cf5b376a7a16
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595418"
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

## <a name="see-also"></a>Дополнительно

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Реализация прокси-сервера обнаружения](implementing-a-discovery-proxy.md)
