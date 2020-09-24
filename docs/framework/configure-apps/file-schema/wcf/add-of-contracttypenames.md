---
title: <add> из <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 69a0bbbc8774251dbdc062875bb06453f355c882
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149144"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="a7d8e-102">\<add> из \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="a7d8e-102">\<add> of \<contractTypeNames></span></span>

<span data-ttu-id="a7d8e-103">Элемент конфигурации, указывающий имя контракта искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="a7d8e-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="a7d8e-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="a7d8e-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="a7d8e-105">Обратите внимание, что в Windows Communication Foundation (WCF) конечная точка может поддерживать только один контракт.</span><span class="sxs-lookup"><span data-stu-id="a7d8e-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="a7d8e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7d8e-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7d8e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a7d8e-107">Attributes and Elements</span></span>  

 <span data-ttu-id="a7d8e-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a7d8e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7d8e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7d8e-109">Attributes</span></span>  
  
|<span data-ttu-id="a7d8e-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a7d8e-110">Attribute</span></span>|<span data-ttu-id="a7d8e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a7d8e-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7d8e-112">name</span><span class="sxs-lookup"><span data-stu-id="a7d8e-112">name</span></span>|<span data-ttu-id="a7d8e-113">Строка, в которой указано имя типа контракта.</span><span class="sxs-lookup"><span data-stu-id="a7d8e-113">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="a7d8e-114">namespace</span><span class="sxs-lookup"><span data-stu-id="a7d8e-114">namespace</span></span>|<span data-ttu-id="a7d8e-115">Строка, в которой указано пространство имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="a7d8e-115">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7d8e-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a7d8e-116">Child Elements</span></span>  

 <span data-ttu-id="a7d8e-117">Нет</span><span class="sxs-lookup"><span data-stu-id="a7d8e-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7d8e-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a7d8e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a7d8e-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="a7d8e-119">Element</span></span>|<span data-ttu-id="a7d8e-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a7d8e-120">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="a7d8e-121">Коллекция имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="a7d8e-121">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7d8e-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a7d8e-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
