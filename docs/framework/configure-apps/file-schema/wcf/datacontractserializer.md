---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0e4cbc50c25d4fa1f67f283f2b52d4b174428cd3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153928"
---
# <a name="datacontractserializer"></a><span data-ttu-id="3cdd1-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="3cdd1-102">dataContractSerializer</span></span>

<span data-ttu-id="3cdd1-103">Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="3cdd1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cdd1-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cdd1-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3cdd1-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3cdd1-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cdd1-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3cdd1-107">Attributes</span></span>  
  
|<span data-ttu-id="3cdd1-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cdd1-108">Element</span></span>|<span data-ttu-id="3cdd1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3cdd1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cdd1-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="3cdd1-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="3cdd1-111">Логическое значение, указывающее, должны ли пропускаться данные, предоставляемые конечной точкой, при их сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-111">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="3cdd1-112">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="3cdd1-112">maxItemsInObjectGraph</span></span>|<span data-ttu-id="3cdd1-113">Целое число, указывающее максимальное количество элементов для сериализации или десериализации.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-113">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cdd1-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3cdd1-114">Child Elements</span></span>  

 <span data-ttu-id="3cdd1-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cdd1-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3cdd1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3cdd1-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cdd1-117">Element</span></span>|<span data-ttu-id="3cdd1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3cdd1-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3cdd1-119">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-119">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cdd1-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cdd1-120">Remarks</span></span>  

 <span data-ttu-id="3cdd1-121">Дополнительные сведения об известных типах см. в документации по <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-121">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="3cdd1-122">Элемент поведения `<dataContractSerializer>` (если он присутствует) должен всегда находиться в файле конфигурации перед элементом поведения `<enableWebScript>`.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-122">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="3cdd1-123">В противном случае результирующее поведение является неопределенным.</span><span class="sxs-lookup"><span data-stu-id="3cdd1-123">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdd1-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3cdd1-124">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="3cdd1-125">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="3cdd1-125">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3cdd1-126">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="3cdd1-126">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
