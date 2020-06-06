---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850267"
---
# \<backupLists>
<span data-ttu-id="f9adc-101">Представляет раздел конфигурации для определения набора резервных служб, используемых при обработке ошибок.</span><span class="sxs-lookup"><span data-stu-id="f9adc-101">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="f9adc-102">Каждый дочерний элемент является резервным списком, в котором перечислен набор конечных точек, используемых службой маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="f9adc-102">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="f9adc-103">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="f9adc-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="f9adc-104">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="f9adc-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="f9adc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9adc-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9adc-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f9adc-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f9adc-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f9adc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9adc-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f9adc-108">Attributes</span></span>  
 <span data-ttu-id="f9adc-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f9adc-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9adc-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f9adc-110">Child Elements</span></span>  
  
|<span data-ttu-id="f9adc-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9adc-111">Element</span></span>|<span data-ttu-id="f9adc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f9adc-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="f9adc-113">Содержит список конечных точек, которые служба маршрутизации будет использовать, если основная конечная точка недоступна.</span><span class="sxs-lookup"><span data-stu-id="f9adc-113">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="f9adc-114">.</span><span class="sxs-lookup"><span data-stu-id="f9adc-114">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9adc-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f9adc-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f9adc-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9adc-116">Element</span></span>|<span data-ttu-id="f9adc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f9adc-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="f9adc-118">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF), <xref:System.ServiceModel.Dispatcher.MessageFilter> используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки для отправки сообщений при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="f9adc-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9adc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f9adc-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
