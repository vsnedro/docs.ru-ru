---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854924"
---
# \<transportConfigurationTypes>
<span data-ttu-id="61d1f-101">Представляет коллекцию элементов конфигурации, которые определяют тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="61d1f-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="61d1f-102">Может использоваться для добавления пользовательских протоколов WAS.</span><span class="sxs-lookup"><span data-stu-id="61d1f-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="61d1f-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61d1f-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61d1f-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="61d1f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="61d1f-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="61d1f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61d1f-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="61d1f-106">Attributes</span></span>  
  
|<span data-ttu-id="61d1f-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="61d1f-107">Attribute</span></span>|<span data-ttu-id="61d1f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="61d1f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61d1f-109">name</span><span class="sxs-lookup"><span data-stu-id="61d1f-109">name</span></span>|<span data-ttu-id="61d1f-110">Имя транспорта</span><span class="sxs-lookup"><span data-stu-id="61d1f-110">The name of the transport</span></span>|  
|<span data-ttu-id="61d1f-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="61d1f-111">transportConfigurationType</span></span>|<span data-ttu-id="61d1f-112">Тип, реализующий транспорт</span><span class="sxs-lookup"><span data-stu-id="61d1f-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61d1f-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="61d1f-113">Child Elements</span></span>  
  
|<span data-ttu-id="61d1f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="61d1f-114">Element</span></span>|<span data-ttu-id="61d1f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="61d1f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="61d1f-116">Добавляет элемент конфигурации, который определяет тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="61d1f-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61d1f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="61d1f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="61d1f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="61d1f-118">Element</span></span>|<span data-ttu-id="61d1f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="61d1f-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="61d1f-120">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="61d1f-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61d1f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="61d1f-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="61d1f-122">Размещение</span><span class="sxs-lookup"><span data-stu-id="61d1f-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
