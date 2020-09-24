---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 0c6d844ac287037b7a546d3a48e7cd924e8a63d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153616"
---
# \<serviceThrottling>

<span data-ttu-id="17f27-101">Задает механизм настройки службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="17f27-101">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**  
  
## <a name="syntax"></a><span data-ttu-id="17f27-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17f27-102">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17f27-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="17f27-103">Attributes and Elements</span></span>  

 <span data-ttu-id="17f27-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="17f27-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17f27-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="17f27-105">Attributes</span></span>  
  
|<span data-ttu-id="17f27-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="17f27-106">Attribute</span></span>|<span data-ttu-id="17f27-107">Описание</span><span class="sxs-lookup"><span data-stu-id="17f27-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17f27-108">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="17f27-108">maxConcurrentCalls</span></span>|<span data-ttu-id="17f27-109">Положительное целое число, ограничивающее количество сообщений, обрабатываемых в текущий момент в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="17f27-109">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="17f27-110">Вызовы, превышающие этот предел, ставятся в очередь.</span><span class="sxs-lookup"><span data-stu-id="17f27-110">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="17f27-111">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="17f27-111">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="17f27-112">Значение по умолчанию: 16 \* количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="17f27-112">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="17f27-113">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="17f27-113">maxConcurrentInstances</span></span>|<span data-ttu-id="17f27-114">Положительное целое число, ограничивающее количество объектов <xref:System.ServiceModel.InstanceContext>, одновременно выполняющихся в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="17f27-114">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="17f27-115">Запросы на создание дополнительных экземпляров ставятся в очередь и выполняются, когда происходит отступление от предельной величины.</span><span class="sxs-lookup"><span data-stu-id="17f27-115">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="17f27-116">Значение по умолчанию: сумма maxConcurrentSessions и MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="17f27-116">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="17f27-117">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="17f27-117">maxConcurrentSessions</span></span>|<span data-ttu-id="17f27-118">Положительное целое число, ограничивающее количество сеансов, которое может принять объект <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="17f27-118">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="17f27-119">Служба принимает соединения сверх предела, но только каналы, количество которых меньше предельного значения, являются активными (сообщения считываются из канала).</span><span class="sxs-lookup"><span data-stu-id="17f27-119">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="17f27-120">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="17f27-120">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="17f27-121">Значение по умолчанию: 100 \* количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="17f27-121">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17f27-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="17f27-122">Child Elements</span></span>  

 <span data-ttu-id="17f27-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="17f27-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17f27-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="17f27-124">Parent Elements</span></span>  
  
|<span data-ttu-id="17f27-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="17f27-125">Element</span></span>|<span data-ttu-id="17f27-126">Описание</span><span class="sxs-lookup"><span data-stu-id="17f27-126">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="17f27-127">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="17f27-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17f27-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="17f27-128">Remarks</span></span>  

 <span data-ttu-id="17f27-129">Элементы регулирования ограничивают число одновременных вызовов, экземпляров или сеансов, чтобы предотвратить чрезмерное потребление ресурсов.</span><span class="sxs-lookup"><span data-stu-id="17f27-129">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="17f27-130">Каждый раз при достижении значений атрибутов происходит запись трассировки.</span><span class="sxs-lookup"><span data-stu-id="17f27-130">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="17f27-131">Первая трассировка записывается как предупреждение.</span><span class="sxs-lookup"><span data-stu-id="17f27-131">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17f27-132">Пример</span><span class="sxs-lookup"><span data-stu-id="17f27-132">Example</span></span>  

 <span data-ttu-id="17f27-133">В следующем примере конфигурации служба допускает максимум 2 одновременно выполняющихся вызова, а максимальное количество одновременно присутствующих экземпляров равно 10.</span><span class="sxs-lookup"><span data-stu-id="17f27-133">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="17f27-134">Подробный пример выполнения этого примера см. в разделе [регулирование](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="17f27-134">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="17f27-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="17f27-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="17f27-136">Использование ServiceThrottlingBehavior для управления производительностью службы WCF</span><span class="sxs-lookup"><span data-stu-id="17f27-136">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
