---
title: <add> из <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 6d8fd26170059226583a300b1b48b849666db929
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181626"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="c615c-102">\<add> из \<backupList></span><span class="sxs-lookup"><span data-stu-id="c615c-102">\<add> of \<backupList></span></span>

<span data-ttu-id="c615c-103">Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c615c-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="c615c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c615c-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c615c-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c615c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c615c-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c615c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c615c-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c615c-107">Attributes</span></span>  
  
|<span data-ttu-id="c615c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c615c-108">Attribute</span></span>|<span data-ttu-id="c615c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c615c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c615c-110">name</span><span class="sxs-lookup"><span data-stu-id="c615c-110">name</span></span>|<span data-ttu-id="c615c-111">Строка, задающая имя резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c615c-111">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c615c-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c615c-112">Child Elements</span></span>  

 <span data-ttu-id="c615c-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c615c-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c615c-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c615c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c615c-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c615c-115">Element</span></span>|<span data-ttu-id="c615c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c615c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="c615c-117">Содержит список конечных точек, которые служба маршрутизации будет использовать, если основная конечная точка недоступна.</span><span class="sxs-lookup"><span data-stu-id="c615c-117">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c615c-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c615c-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
