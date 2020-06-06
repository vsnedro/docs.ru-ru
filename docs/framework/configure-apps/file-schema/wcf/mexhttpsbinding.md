---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430341"
---
# \<mexHttpsBinding>
<span data-ttu-id="13786-101">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством HTTPS.</span><span class="sxs-lookup"><span data-stu-id="13786-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="13786-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13786-102">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13786-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13786-103">Attributes and Elements</span></span>  
 <span data-ttu-id="13786-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="13786-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13786-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13786-105">Attributes</span></span>  
  
|<span data-ttu-id="13786-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="13786-106">Attribute</span></span>|<span data-ttu-id="13786-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="13786-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="13786-108">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="13786-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="13786-109">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="13786-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="13786-110">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="13786-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="13786-111">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="13786-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="13786-112">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="13786-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="13786-113">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="13786-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="13786-114">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="13786-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="13786-115">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="13786-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="13786-116">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="13786-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="13786-117">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="13786-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="13786-118">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="13786-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="13786-119">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="13786-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="13786-120">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="13786-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="13786-121">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="13786-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="13786-122">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="13786-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="13786-123">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="13786-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13786-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13786-124">Child Elements</span></span>  
 <span data-ttu-id="13786-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="13786-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13786-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13786-126">Parent Elements</span></span>  
  
|<span data-ttu-id="13786-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="13786-127">Element</span></span>|<span data-ttu-id="13786-128">Описание</span><span class="sxs-lookup"><span data-stu-id="13786-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="13786-129">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="13786-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13786-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="13786-130">Remarks</span></span>  
 <span data-ttu-id="13786-131">Эта привязка по существу является привязкой `WSHttpBinding`, которая поддерживает безопасность уровня транспорта с помощью сертификатов.</span><span class="sxs-lookup"><span data-stu-id="13786-131">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="13786-132">Дополнительные сведения о настройке и использовании такой конечной точки метаданных см. в разделе [как настроить настраиваемую привязку WS-Metadata Exchange](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [как получать метаданные через привязку обмена метаданными](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), а также образец [настраиваемой конечной точки безопасных метаданных](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="13786-132">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13786-133">См. также</span><span class="sxs-lookup"><span data-stu-id="13786-133">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="13786-134">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="13786-134">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="13786-135">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="13786-135">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="13786-136">Практическое руководство. Настройка пользовательской привязки для обмена WS-Metadata</span><span class="sxs-lookup"><span data-stu-id="13786-136">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="13786-137">Практическое руководство. Получение метаданных через привязку, не использующую MEX</span><span class="sxs-lookup"><span data-stu-id="13786-137">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="13786-138">Пользовательская конечная точка защищенных метаданных</span><span class="sxs-lookup"><span data-stu-id="13786-138">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="13786-139">Метаданные</span><span class="sxs-lookup"><span data-stu-id="13786-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="13786-140">Привязки</span><span class="sxs-lookup"><span data-stu-id="13786-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="13786-141">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="13786-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="13786-142">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="13786-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
