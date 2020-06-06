---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 7a76e5a90fe3218bc0302501b71daa9de0b098bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854835"
---
# \<userDefinedType>
<span data-ttu-id="c7763-101">Представляет определяемый пользователем тип (UDT), подлежащий включению в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="c7763-101">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**  
  
## <a name="syntax"></a><span data-ttu-id="c7763-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7763-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7763-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c7763-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c7763-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c7763-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7763-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c7763-105">Attributes</span></span>  
  
|<span data-ttu-id="c7763-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c7763-106">Attribute</span></span>|<span data-ttu-id="c7763-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="c7763-107">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="c7763-108">Необязательный атрибут, содержащий строку, которая задает отображаемое имя типа.</span><span class="sxs-lookup"><span data-stu-id="c7763-108">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="c7763-109">Не используется средой выполнения, но помогает читателю различать типы.</span><span class="sxs-lookup"><span data-stu-id="c7763-109">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="c7763-110">Строка идентификатора GUID, которая идентифицирует конкретный тип UDT в зарегистрированной библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="c7763-110">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="c7763-111">Срока глобального уникального идентификатора (GUID), которая является идентификатором для зарегистрированной библиотеки типов, определяющей тип.</span><span class="sxs-lookup"><span data-stu-id="c7763-111">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="c7763-112">Срока, которая является идентификатором версии библиотеки типов, определяющей тип.</span><span class="sxs-lookup"><span data-stu-id="c7763-112">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7763-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c7763-113">Child Elements</span></span>  
 <span data-ttu-id="c7763-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c7763-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7763-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c7763-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c7763-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="c7763-116">Element</span></span>|<span data-ttu-id="c7763-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c7763-117">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="c7763-118">Коллекция элементов `userDefinedType`.</span><span class="sxs-lookup"><span data-stu-id="c7763-118">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7763-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7763-119">Remarks</span></span>  
 <span data-ttu-id="c7763-120">Среда выполнения интеграции СОМ+ создает службы путем проверки библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="c7763-120">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="c7763-121">Если в компоненте СОМ+ содержатся методы, которые служат для передачи VARIANT, система не в состоянии определить фактические типы для передачи до среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7763-121">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="c7763-122">Поэтому при попытке передать пользовательский тип (UDT) в рамках VARIANT происходит сбой, поскольку данный тип не является известным типом для сериализации.</span><span class="sxs-lookup"><span data-stu-id="c7763-122">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="c7763-123">Для решения этой проблемы можно добавить пользовательские типы в файл конфигурации, чтобы их можно было включить как известные типы в соответствующий контракт службы.</span><span class="sxs-lookup"><span data-stu-id="c7763-123">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="c7763-124">Для этого необходимо однозначно определить пользовательский тип и контракты, то есть исходные интерфейсы СОМ, которые его используют.</span><span class="sxs-lookup"><span data-stu-id="c7763-124">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="c7763-125">В следующем примере показано, как добавить два конкретных пользовательских типа в раздел <`userDefinedTypes`> файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c7763-125">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="c7763-126">При запуске службы среда выполнения интеграции выполняет поиск по указанным типам и добавляет их в коллекции известных типов для заданных контрактов.</span><span class="sxs-lookup"><span data-stu-id="c7763-126">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7763-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c7763-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="c7763-128">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="c7763-128">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="c7763-129">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="c7763-129">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
