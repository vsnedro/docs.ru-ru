---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 0d12f886eaee6283ee686209dfc129e397a8e1fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204701"
---
# \<mexTcpBinding>

<span data-ttu-id="91e54-101">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по TCP.</span><span class="sxs-lookup"><span data-stu-id="91e54-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="91e54-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91e54-102">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91e54-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="91e54-103">Attributes and Elements</span></span>  

 <span data-ttu-id="91e54-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="91e54-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91e54-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="91e54-105">Attributes</span></span>  
  
|<span data-ttu-id="91e54-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="91e54-106">Attribute</span></span>|<span data-ttu-id="91e54-107">Описание</span><span class="sxs-lookup"><span data-stu-id="91e54-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="91e54-108">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="91e54-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="91e54-109">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="91e54-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="91e54-110">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="91e54-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="91e54-111">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="91e54-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="91e54-112">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="91e54-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="91e54-113">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="91e54-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="91e54-114">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="91e54-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="91e54-115">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="91e54-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="91e54-116">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="91e54-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="91e54-117">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="91e54-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="91e54-118">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="91e54-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="91e54-119">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="91e54-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="91e54-120">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="91e54-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="91e54-121">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="91e54-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="91e54-122">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="91e54-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="91e54-123">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="91e54-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91e54-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="91e54-124">Child Elements</span></span>  

 <span data-ttu-id="91e54-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="91e54-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91e54-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="91e54-126">Parent Elements</span></span>  
  
|<span data-ttu-id="91e54-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="91e54-127">Element</span></span>|<span data-ttu-id="91e54-128">Описание</span><span class="sxs-lookup"><span data-stu-id="91e54-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="91e54-129">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="91e54-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91e54-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="91e54-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="91e54-131">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="91e54-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="91e54-132">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="91e54-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="91e54-133">Метаданные</span><span class="sxs-lookup"><span data-stu-id="91e54-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="91e54-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="91e54-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="91e54-135">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="91e54-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="91e54-136">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="91e54-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
