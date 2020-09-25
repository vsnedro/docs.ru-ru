---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 404cc66ce423ba947c2817b56bebb4daf341ef0b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176049"
---
# \<comContracts>

<span data-ttu-id="6191b-101">Раздел конфигурации `comContracts` содержит элементы, которые позволяют задавать различные свойства контракта службы интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="6191b-101">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="6191b-102">Задание пространства имен и контракта</span><span class="sxs-lookup"><span data-stu-id="6191b-102">Specifying Namespace and Contract</span></span>  

 <span data-ttu-id="6191b-103">Контракты службы интеграции COM+ в настоящее время ограничены `http://tempuri.org` пространством имен, а имя контракта является производным от поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6191b-103">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="6191b-104">Однако можно указать альтернативы, используя раздел `comContracts` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6191b-104">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="6191b-105">Например, для указания пространства имен, имени контракта службы и параметра для принудительного использования сеансовых привязок можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="6191b-105">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="6191b-106">После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.</span><span class="sxs-lookup"><span data-stu-id="6191b-106">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="6191b-107">Если раздел пуст, при инициализации службы применяется пространство имен по умолчанию и имя контракта, взятое из идентификатора поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6191b-107">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="6191b-108">Кроме того, элемент можно использовать [\<exposedMethod>](exposedmethod.md) для указания методов COM+, предоставляемых, когда интерфейс в компоненте com+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="6191b-108">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="6191b-109">Можно также использовать [\<persistableTypes>](persistabletypes.md) для указания сохраняемых типов, используемых при интеграции.</span><span class="sxs-lookup"><span data-stu-id="6191b-109">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="6191b-110">Наконец, можно использовать [\<userDefinedType>](userdefinedtype.md) элемент для включения определяемых пользователем типов (UDT), которые должны быть включены в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="6191b-110">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6191b-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6191b-111">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [<span data-ttu-id="6191b-112">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="6191b-112">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="6191b-113">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="6191b-113">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
