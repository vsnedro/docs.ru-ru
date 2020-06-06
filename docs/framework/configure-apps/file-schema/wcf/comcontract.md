---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850031"
---
# \<comContract>
<span data-ttu-id="8b954-101">Указывает контракт службы интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="8b954-101">Specifies a COM+ integration service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a><span data-ttu-id="8b954-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b954-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b954-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8b954-103">Attributes and Elements</span></span>  
 <span data-ttu-id="8b954-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8b954-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b954-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8b954-105">Attributes</span></span>  
  
|<span data-ttu-id="8b954-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8b954-106">Attribute</span></span>|<span data-ttu-id="8b954-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="8b954-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b954-108">contract</span><span class="sxs-lookup"><span data-stu-id="8b954-108">contract</span></span>|<span data-ttu-id="8b954-109">Строка, содержащая тип контракта.</span><span class="sxs-lookup"><span data-stu-id="8b954-109">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="8b954-110">name</span><span class="sxs-lookup"><span data-stu-id="8b954-110">name</span></span>|<span data-ttu-id="8b954-111">Строка, содержащая имя контракта.</span><span class="sxs-lookup"><span data-stu-id="8b954-111">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="8b954-112">namespace</span><span class="sxs-lookup"><span data-stu-id="8b954-112">namespace</span></span>|<span data-ttu-id="8b954-113">Строка, содержащая пространство имен контракта.</span><span class="sxs-lookup"><span data-stu-id="8b954-113">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="8b954-114">requiresSession</span><span class="sxs-lookup"><span data-stu-id="8b954-114">requiresSession</span></span>|<span data-ttu-id="8b954-115">Логическое значение, указывающее, ограничено ли использование контракта только сеансовыми привязками.</span><span class="sxs-lookup"><span data-stu-id="8b954-115">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="8b954-116">При инициализации службы среда выполнения интеграции обеспечивает согласованность этого параметра с типом используемой привязки.</span><span class="sxs-lookup"><span data-stu-id="8b954-116">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="8b954-117">В случае конфликта одной или нескольких привязок для контракта создается исключение.</span><span class="sxs-lookup"><span data-stu-id="8b954-117">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="8b954-118">Если это свойство имеет значение `false`, то при использовании одностороннего канала и наличии параметров [out] также создается исключение.</span><span class="sxs-lookup"><span data-stu-id="8b954-118">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b954-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8b954-119">Child Elements</span></span>  
  
|<span data-ttu-id="8b954-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8b954-120">Element</span></span>|<span data-ttu-id="8b954-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8b954-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b954-122">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="8b954-122">persistableTypes</span></span>|<span data-ttu-id="8b954-123">Все сохраняемые типы.</span><span class="sxs-lookup"><span data-stu-id="8b954-123">All the persistable types.</span></span>|  
|<span data-ttu-id="8b954-124">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="8b954-124">userDefinedTypes</span></span>|<span data-ttu-id="8b954-125">Коллекция пользовательских типов (UDT), подлежащая включению в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="8b954-125">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="8b954-126">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="8b954-126">exposedMethods</span></span>|<span data-ttu-id="8b954-127">Коллекция методов COM+, которые предоставляются при предоставлении интерфейса компонента COM+ как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="8b954-127">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b954-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8b954-128">Parent Elements</span></span>  
  
|<span data-ttu-id="8b954-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="8b954-129">Element</span></span>|<span data-ttu-id="8b954-130">Описание</span><span class="sxs-lookup"><span data-stu-id="8b954-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b954-131">comContracts</span><span class="sxs-lookup"><span data-stu-id="8b954-131">comContracts</span></span>|<span data-ttu-id="8b954-132">Содержит коллекцию элементов `comContract`.</span><span class="sxs-lookup"><span data-stu-id="8b954-132">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b954-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b954-133">Remarks</span></span>  
 <span data-ttu-id="8b954-134">Контракты службы интеграции COM+ в настоящее время ограничены `http://tempuri.org` пространством имен, а имя контракта является производным от поддерживающего COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8b954-134">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="8b954-135">Однако можно указать альтернативы, используя раздел `comContracts`, а также элемент `comContract` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8b954-135">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="8b954-136">Например, для указания пространства имен, имени контракта и подлежащих включению пользовательских типов, а также других параметров контракта службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="8b954-136">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="8b954-137">После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.</span><span class="sxs-lookup"><span data-stu-id="8b954-137">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b954-138">См. также</span><span class="sxs-lookup"><span data-stu-id="8b954-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="8b954-139">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="8b954-139">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="8b954-140">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="8b954-140">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
