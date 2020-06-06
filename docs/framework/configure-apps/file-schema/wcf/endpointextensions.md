---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: fe57cb84cfa70b1f6b92abf1dbac89ddad9d4dc8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "69925701"
---
# \<endpointExtensions>
Этот раздел регистрирует новую стандартную конечную точку в разделе расширений файла конфигурации компьютера или приложения. Добавить стандартную конечную точку в эту коллекцию можно, используя ключевое слово `add`, а также присвоив атрибуту `type` элемента значение, соответствующее типу конечной точки, а атрибуту `name` - имя стандартной конечной точки.  
  
 В следующем примере элемент `add` и атрибут `name` используются для добавления стандартной конечной точки в раздел `<endpointExtensions>` файла конфигурации.  
  
```xml  
<system.serviceModel>
  <extensions>
    <endpointExtensions>
      <add name="udpDiscoveryEndpoint"
           type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
 После регистрации стандартной конечной точки ее можно использовать, как показано в следующем примере. В [\<endpoint>](endpoint-element.md) элементе `kind` атрибут указывает тип стандартной конечной точки, зарегистрированный в `<endpointExtensions>` разделе. `endpointConfiguration`Атрибут будет идентичен `name` атрибуту элемента конфигурации стандартной конечной точки в `<standardEndpoints>` разделе.  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Service1">
      <endpoint kind="udpDiscoveryEndpoint"
                endpointConfiguration="udpConfig" />
    </service>
  </services>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
