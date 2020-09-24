---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b3234bfa60cd1e3c88778951fc27301c615c84ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148962"
---
# \<client>

<span data-ttu-id="7b432-101">Элемент `client` определяет список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="7b432-101">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="7b432-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b432-102">Syntax</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7b432-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7b432-103">Attributes and Elements</span></span>

 <span data-ttu-id="7b432-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7b432-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7b432-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b432-105">Attributes</span></span>

 <span data-ttu-id="7b432-106">Нет</span><span class="sxs-lookup"><span data-stu-id="7b432-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="7b432-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7b432-107">Child Elements</span></span>

|<span data-ttu-id="7b432-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b432-108">Element</span></span>|<span data-ttu-id="7b432-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7b432-109">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="7b432-110">Содержит коллекцию элементов Endpoint, указывающих конечные точки, к которым может подключаться этот клиент.</span><span class="sxs-lookup"><span data-stu-id="7b432-110">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="7b432-111">Содержит параметры обработки метаданных.</span><span class="sxs-lookup"><span data-stu-id="7b432-111">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7b432-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7b432-112">Parent Elements</span></span>

|<span data-ttu-id="7b432-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b432-113">Element</span></span>|<span data-ttu-id="7b432-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7b432-114">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="7b432-115">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7b432-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7b432-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="7b432-116">Remarks</span></span>

 <span data-ttu-id="7b432-117">В разделе `client` определяется список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="7b432-117">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="7b432-118">Каждая конечная точка, указанная в разделе клиента, определяет свои собственные привязку, поведение и контракт.</span><span class="sxs-lookup"><span data-stu-id="7b432-118">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="7b432-119">Она однозначно определяется сочетанием атрибутов `name` и `contract`.</span><span class="sxs-lookup"><span data-stu-id="7b432-119">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="7b432-120">В коде клиента указывается атрибут `name` для подключения к конечной точке службы, выполняемой клиентом.</span><span class="sxs-lookup"><span data-stu-id="7b432-120">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="7b432-121">Если атрибут `name` отсутствует, конечная точка действует как конечная точка по умолчанию для контракта, который она реализует.</span><span class="sxs-lookup"><span data-stu-id="7b432-121">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="7b432-122">Кроме того, в данном разделе также задаются параметры обработки метаданных.</span><span class="sxs-lookup"><span data-stu-id="7b432-122">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="7b432-123">Пример</span><span class="sxs-lookup"><span data-stu-id="7b432-123">Example</span></span>

```xml
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```

## <a name="see-also"></a><span data-ttu-id="7b432-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7b432-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="7b432-125">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="7b432-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="7b432-126">Клиенты</span><span class="sxs-lookup"><span data-stu-id="7b432-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
