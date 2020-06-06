---
title: <add> из <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850316"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="d5f10-102">\<add> из \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="d5f10-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="d5f10-103">Данный элемент представляет собой пару ключ/значение, которая идентифицирует тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="d5f10-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d5f10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5f10-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5f10-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5f10-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d5f10-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5f10-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5f10-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5f10-107">Attributes</span></span>  
  
|<span data-ttu-id="d5f10-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d5f10-108">Attribute</span></span>|<span data-ttu-id="d5f10-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d5f10-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5f10-110">name</span><span class="sxs-lookup"><span data-stu-id="d5f10-110">name</span></span>|<span data-ttu-id="d5f10-111">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5f10-111">Required String attribute.</span></span><br /><br /> <span data-ttu-id="d5f10-112">Содержит ключ, определяемый пользователем, который является уникальным идентификатором типа транспорта.</span><span class="sxs-lookup"><span data-stu-id="d5f10-112">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="d5f10-113">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="d5f10-113">transportConfigurationType</span></span>|<span data-ttu-id="d5f10-114">Строка, содержащая тип, реализующий конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="d5f10-114">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5f10-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5f10-115">Child Elements</span></span>  
 <span data-ttu-id="d5f10-116">Нет</span><span class="sxs-lookup"><span data-stu-id="d5f10-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5f10-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5f10-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d5f10-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5f10-118">Element</span></span>|<span data-ttu-id="d5f10-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d5f10-119">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="d5f10-120">Коллекция типов, реализующих конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="d5f10-120">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d5f10-121">Пример</span><span class="sxs-lookup"><span data-stu-id="d5f10-121">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="d5f10-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d5f10-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="d5f10-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="d5f10-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
