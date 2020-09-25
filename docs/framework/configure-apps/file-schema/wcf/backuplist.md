---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 8f4dcf8f7d71cfa2ed9944822d7cce974e7f1979
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201568"
---
# \<backupList>

<span data-ttu-id="1552f-101">Представляет раздел конфигурации для определения резервного списка, в котором перечислен набор конечных точек, используемых службой маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="1552f-101">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="1552f-102">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="1552f-102">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="1552f-103">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="1552f-103">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**  
  
## <a name="syntax"></a><span data-ttu-id="1552f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1552f-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1552f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1552f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1552f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1552f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1552f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1552f-107">Attributes</span></span>  
  
|<span data-ttu-id="1552f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1552f-108">Attribute</span></span>|<span data-ttu-id="1552f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1552f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1552f-110">name</span><span class="sxs-lookup"><span data-stu-id="1552f-110">name</span></span>|<span data-ttu-id="1552f-111">Строка, в которой приведено имя, используемое для указания этого списка конечных точек.</span><span class="sxs-lookup"><span data-stu-id="1552f-111">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1552f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1552f-112">Child Elements</span></span>  
  
|<span data-ttu-id="1552f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="1552f-113">Element</span></span>|<span data-ttu-id="1552f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1552f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="1552f-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1552f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="1552f-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="1552f-116">Element</span></span>|<span data-ttu-id="1552f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1552f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="1552f-118">Список резервных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="1552f-118">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1552f-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="1552f-119">Remarks</span></span>  

 <span data-ttu-id="1552f-120">Этот раздел содержит упорядоченную коллекцию конечных точек, в которые будет передаваться сообщение в случае, если при отправке в основную конечную точку возникает исключение связи.</span><span class="sxs-lookup"><span data-stu-id="1552f-120">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="1552f-121">Если отправка в основную конечную точку, указанную в `endpointName` атрибуте, [\<add>](add-of-entries.md) завершается с исключением связи, служба Routing Service попытается отправить сообщение в первую конечную точку в этом разделе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1552f-121">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="1552f-122">Если эта отправка также приведет к возникновению исключения связи, служба маршрутизации попытается отправить сообщение в следующую точку, указанную в этом разделе, пока отправка не завершится успешно или не возвратит ошибку, не связанную с исключением связи, либо пока ошибки не будут возвращены для всех конечных точек из коллекции.</span><span class="sxs-lookup"><span data-stu-id="1552f-122">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="1552f-123">В следующем примере, если отправка в основную конечную точку с именем "Destination" возвращает исключение связи, Служба попытается отправить сообщение в "Алтернатесервицекуеуе".</span><span class="sxs-lookup"><span data-stu-id="1552f-123">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="1552f-124">Если эта попытка также возвращает исключение связи, то служба маршрутизации попытается отправить сообщение в следующую конечную точку в коллекции.</span><span class="sxs-lookup"><span data-stu-id="1552f-124">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="1552f-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1552f-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
