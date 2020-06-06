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
<span data-ttu-id="3d0a1-101">Этот раздел регистрирует новую стандартную конечную точку в разделе расширений файла конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="3d0a1-101">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="3d0a1-102">Добавить стандартную конечную точку в эту коллекцию можно, используя ключевое слово `add`, а также присвоив атрибуту `type` элемента значение, соответствующее типу конечной точки, а атрибуту `name` - имя стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3d0a1-102">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="3d0a1-103">В следующем примере элемент `add` и атрибут `name` используются для добавления стандартной конечной точки в раздел `<endpointExtensions>` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3d0a1-103">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="3d0a1-104">После регистрации стандартной конечной точки ее можно использовать, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3d0a1-104">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="3d0a1-105">В [\<endpoint>](endpoint-element.md) элементе `kind` атрибут указывает тип стандартной конечной точки, зарегистрированный в `<endpointExtensions>` разделе.</span><span class="sxs-lookup"><span data-stu-id="3d0a1-105">In the [\<endpoint>](endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="3d0a1-106">`endpointConfiguration`Атрибут будет идентичен `name` атрибуту элемента конфигурации стандартной конечной точки в `<standardEndpoints>` разделе.</span><span class="sxs-lookup"><span data-stu-id="3d0a1-106">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
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
