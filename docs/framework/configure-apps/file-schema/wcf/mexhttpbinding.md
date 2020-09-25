---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8c15b06e60e4de6ede4c9a683a6701140533534c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204740"
---
# \<mexHttpBinding>

<span data-ttu-id="a29a3-101">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="a29a3-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="a29a3-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a29a3-102">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a29a3-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a29a3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a29a3-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a29a3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a29a3-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a29a3-105">Attributes</span></span>  
  
|<span data-ttu-id="a29a3-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a29a3-106">Attribute</span></span>|<span data-ttu-id="a29a3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a29a3-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a29a3-108">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="a29a3-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a29a3-109">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a29a3-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a29a3-110">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a29a3-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="a29a3-111">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="a29a3-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a29a3-112">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="a29a3-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a29a3-113">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="a29a3-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a29a3-114">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a29a3-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="a29a3-115">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="a29a3-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a29a3-116">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a29a3-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a29a3-117">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a29a3-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a29a3-118">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="a29a3-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a29a3-119">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a29a3-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a29a3-120">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="a29a3-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="a29a3-121">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="a29a3-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a29a3-122">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a29a3-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a29a3-123">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a29a3-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a29a3-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a29a3-124">Child Elements</span></span>  

 <span data-ttu-id="a29a3-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a29a3-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a29a3-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a29a3-126">Parent Elements</span></span>  
  
|<span data-ttu-id="a29a3-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="a29a3-127">Element</span></span>|<span data-ttu-id="a29a3-128">Описание</span><span class="sxs-lookup"><span data-stu-id="a29a3-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="a29a3-129">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="a29a3-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a29a3-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="a29a3-130">Remarks</span></span>  

 <span data-ttu-id="a29a3-131">Эта привязка по существу является привязкой `WSHttpBinding` с отключенной безопасностью.</span><span class="sxs-lookup"><span data-stu-id="a29a3-131">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="a29a3-132">Она поддерживает большинство запросов метаданных.</span><span class="sxs-lookup"><span data-stu-id="a29a3-132">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a29a3-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a29a3-133">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="a29a3-134">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a29a3-134">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="a29a3-135">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="a29a3-135">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="a29a3-136">Метаданные</span><span class="sxs-lookup"><span data-stu-id="a29a3-136">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="a29a3-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="a29a3-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a29a3-138">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a29a3-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a29a3-139">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a29a3-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
