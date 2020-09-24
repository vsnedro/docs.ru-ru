---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 6545e1f1be2695d165b89a38c7218e0acdc88bfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162027"
---
# \<transportConfigurationTypes>

<span data-ttu-id="a3204-101">Представляет коллекцию элементов конфигурации, которые определяют тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="a3204-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="a3204-102">Может использоваться для добавления пользовательских протоколов WAS.</span><span class="sxs-lookup"><span data-stu-id="a3204-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="a3204-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3204-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3204-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a3204-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a3204-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a3204-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3204-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a3204-106">Attributes</span></span>  
  
|<span data-ttu-id="a3204-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a3204-107">Attribute</span></span>|<span data-ttu-id="a3204-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a3204-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3204-109">name</span><span class="sxs-lookup"><span data-stu-id="a3204-109">name</span></span>|<span data-ttu-id="a3204-110">Имя транспорта</span><span class="sxs-lookup"><span data-stu-id="a3204-110">The name of the transport</span></span>|  
|<span data-ttu-id="a3204-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="a3204-111">transportConfigurationType</span></span>|<span data-ttu-id="a3204-112">Тип, реализующий транспорт</span><span class="sxs-lookup"><span data-stu-id="a3204-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3204-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a3204-113">Child Elements</span></span>  
  
|<span data-ttu-id="a3204-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="a3204-114">Element</span></span>|<span data-ttu-id="a3204-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a3204-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="a3204-116">Добавляет элемент конфигурации, который определяет тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="a3204-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3204-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a3204-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a3204-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="a3204-118">Element</span></span>|<span data-ttu-id="a3204-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a3204-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="a3204-120">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="a3204-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3204-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a3204-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="a3204-122">Размещение</span><span class="sxs-lookup"><span data-stu-id="a3204-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
