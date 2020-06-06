---
title: <routing> из <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 0998f4fc61de7099879ba6e122eed1e64588baec
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397734"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="e9404-102">\<routing> из \<serviceBehavior></span><span class="sxs-lookup"><span data-stu-id="e9404-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="e9404-103">Обеспечивает доступ к службе маршрутизации во время выполнения, чтобы вносить динамические изменения в конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e9404-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**  
  
## <a name="syntax"></a><span data-ttu-id="e9404-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9404-104">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9404-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9404-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e9404-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e9404-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9404-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9404-107">Attributes</span></span>  
  
|<span data-ttu-id="e9404-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e9404-108">Attribute</span></span>|<span data-ttu-id="e9404-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="e9404-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9404-110">filterTable</span><span class="sxs-lookup"><span data-stu-id="e9404-110">filterTable</span></span>|<span data-ttu-id="e9404-111">Строка, в которой указано имя таблицы маршрутизации, содержащей фильтры, вычисляемые службой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e9404-111">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="e9404-112">Это значение должно соответствовать `name` атрибуту [\<filterTable>](filtertable.md) элемента в [\<filterTables>](filtertables.md) разделе.</span><span class="sxs-lookup"><span data-stu-id="e9404-112">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="e9404-113">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="e9404-113">routeOnHeaderOnly</span></span>|<span data-ttu-id="e9404-114">Логическое значение, определяющее, какие части сообщения будут изучены фильтром: только заголовок или заголовок и текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="e9404-114">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="e9404-115">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="e9404-115">The default is `true`.</span></span>|  
|<span data-ttu-id="e9404-116">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="e9404-116">soapProcessingEnabled</span></span>|<span data-ttu-id="e9404-117">Логическое значение, указывающее, будет ли выполняться обработка SOAP.</span><span class="sxs-lookup"><span data-stu-id="e9404-117">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9404-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9404-118">Child Elements</span></span>  
 <span data-ttu-id="e9404-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e9404-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9404-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9404-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e9404-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9404-121">Element</span></span>|<span data-ttu-id="e9404-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e9404-122">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e9404-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="e9404-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9404-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9404-124">Remarks</span></span>  
 <span data-ttu-id="e9404-125">Если добавить к конфигурации поведения службы, этот элемент конфигурации включает маршрутизацию для службы.</span><span class="sxs-lookup"><span data-stu-id="e9404-125">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="e9404-126">В этом элементе можно указать фактическую таблицу маршрутизации, которая будет использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="e9404-126">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="e9404-127">Используя этот раздел конфигурации, можно на лету изменять параметры маршрутизации при изменении шаблона развертывания.</span><span class="sxs-lookup"><span data-stu-id="e9404-127">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="e9404-128">Во время выполнения можно зарегистрировать собственное расширение маршрутизации с новыми параметрами. В этом случае служба маршрутизации будет использовать обновленную конфигурацию для новых сеансов и сообщений (для уже запущенных на данных момент сообщений и сеансов будут применяться правила, действовавшие в момент их запуска).</span><span class="sxs-lookup"><span data-stu-id="e9404-128">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="e9404-129">Благодаря этому обеспечивается безопасная для сеансов и не требующая перезапуска повторная настройка службы маршрутизации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e9404-129">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
