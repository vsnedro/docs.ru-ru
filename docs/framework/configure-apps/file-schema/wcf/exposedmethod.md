---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 2947f0de6a88f39463e58a3b39bda52588fe4baa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203908"
---
# \<exposedMethod>

<span data-ttu-id="0914d-101">Представляет метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="0914d-101">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="0914d-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0914d-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0914d-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0914d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0914d-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0914d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0914d-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0914d-105">Attributes</span></span>  
  
|<span data-ttu-id="0914d-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0914d-106">Attribute</span></span>|<span data-ttu-id="0914d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0914d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0914d-108">name</span><span class="sxs-lookup"><span data-stu-id="0914d-108">name</span></span>|<span data-ttu-id="0914d-109">Строка, которая содержит метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="0914d-109">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0914d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0914d-110">Child Elements</span></span>  

 <span data-ttu-id="0914d-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0914d-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0914d-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0914d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="0914d-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="0914d-113">Element</span></span>|<span data-ttu-id="0914d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0914d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="0914d-115">Коллекция [\<exposedMethod>](exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="0914d-115">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0914d-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="0914d-116">Remarks</span></span>  

 <span data-ttu-id="0914d-117">Средство конфигурации интеграции COM+ (ComSvcConfig.exe) может применяться для добавления определенных методов COM-интерфейса для использования в созданном контракте службы.</span><span class="sxs-lookup"><span data-stu-id="0914d-117">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="0914d-118">Например, для добавления в созданный контракт службы трех именованных методов из COM-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="0914d-118">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="0914d-119">При запуске ComSvcConfig.exe также создается следующий контракт службы, в котором перечислены упомянутые выше методы как [\<exposedMethod>](exposedmethod.md) элементы.</span><span class="sxs-lookup"><span data-stu-id="0914d-119">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="0914d-120">Во время инициализации службы среда выполнения пытается создать контракт службы, отражая и добавляя только методы, входящие в список [\<exposedMethod>](exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="0914d-120">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="0914d-121">Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.</span><span class="sxs-lookup"><span data-stu-id="0914d-121">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0914d-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0914d-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="0914d-123">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="0914d-123">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="0914d-124">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="0914d-124">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
