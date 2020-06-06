---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 41f5b19f5067d9ac7faa2c7329dd07dd9d48e9b3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430871"
---
# \<mexNamedPipeBinding>
<span data-ttu-id="bdf5e-101">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством именованного канала.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="bdf5e-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdf5e-102">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdf5e-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bdf5e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="bdf5e-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdf5e-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bdf5e-105">Attributes</span></span>  
  
|<span data-ttu-id="bdf5e-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bdf5e-106">Attribute</span></span>|<span data-ttu-id="bdf5e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="bdf5e-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="bdf5e-108">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="bdf5e-109">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bdf5e-110">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="bdf5e-111">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="bdf5e-112">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="bdf5e-113">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="bdf5e-114">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="bdf5e-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="bdf5e-115">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="bdf5e-116">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bdf5e-117">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="bdf5e-118">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="bdf5e-119">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bdf5e-120">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="bdf5e-121">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="bdf5e-122">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bdf5e-123">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdf5e-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bdf5e-124">Child Elements</span></span>  
 <span data-ttu-id="bdf5e-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdf5e-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bdf5e-126">Parent Elements</span></span>  
  
|<span data-ttu-id="bdf5e-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="bdf5e-127">Element</span></span>|<span data-ttu-id="bdf5e-128">Описание</span><span class="sxs-lookup"><span data-stu-id="bdf5e-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="bdf5e-129">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="bdf5e-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdf5e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bdf5e-130">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="bdf5e-131">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="bdf5e-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="bdf5e-132">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="bdf5e-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="bdf5e-133">Метаданные</span><span class="sxs-lookup"><span data-stu-id="bdf5e-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="bdf5e-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="bdf5e-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bdf5e-135">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="bdf5e-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="bdf5e-136">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="bdf5e-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
