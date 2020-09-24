---
title: <add> из <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 9bef44ed39ee892080342058206f779b38fb460d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151159"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="fefb3-102">\<add> из \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="fefb3-102">\<add> of \<transportConfigurationType></span></span>

<span data-ttu-id="fefb3-103">Данный элемент представляет собой пару ключ/значение, которая идентифицирует тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="fefb3-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="fefb3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fefb3-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fefb3-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fefb3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fefb3-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fefb3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fefb3-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fefb3-107">Attributes</span></span>  
  
|<span data-ttu-id="fefb3-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fefb3-108">Attribute</span></span>|<span data-ttu-id="fefb3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fefb3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fefb3-110">name</span><span class="sxs-lookup"><span data-stu-id="fefb3-110">name</span></span>|<span data-ttu-id="fefb3-111">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="fefb3-111">Required String attribute.</span></span><br /><br /> <span data-ttu-id="fefb3-112">Содержит ключ, определяемый пользователем, который является уникальным идентификатором типа транспорта.</span><span class="sxs-lookup"><span data-stu-id="fefb3-112">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="fefb3-113">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="fefb3-113">transportConfigurationType</span></span>|<span data-ttu-id="fefb3-114">Строка, содержащая тип, реализующий конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="fefb3-114">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fefb3-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fefb3-115">Child Elements</span></span>  

 <span data-ttu-id="fefb3-116">Нет</span><span class="sxs-lookup"><span data-stu-id="fefb3-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fefb3-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fefb3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fefb3-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="fefb3-118">Element</span></span>|<span data-ttu-id="fefb3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fefb3-119">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="fefb3-120">Коллекция типов, реализующих конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="fefb3-120">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fefb3-121">Пример</span><span class="sxs-lookup"><span data-stu-id="fefb3-121">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="fefb3-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fefb3-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="fefb3-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="fefb3-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
