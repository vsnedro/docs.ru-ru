---
title: <add> из <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 2c6b5de51e6508965daf6022a47d12d8d73f2a4d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149131"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="ab66a-102">\<add> из \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="ab66a-102">\<add> of \<defaultPorts></span></span>

<span data-ttu-id="ab66a-103">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="ab66a-103">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ab66a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab66a-104">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab66a-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ab66a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ab66a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ab66a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab66a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ab66a-107">Attributes</span></span>  
  
|<span data-ttu-id="ab66a-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ab66a-108">Attribute</span></span>|<span data-ttu-id="ab66a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ab66a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab66a-110">порт</span><span class="sxs-lookup"><span data-stu-id="ab66a-110">port</span></span>|<span data-ttu-id="ab66a-111">Целочисленное значение, определяющее номер COM-порта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab66a-111">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="ab66a-112">scheme</span><span class="sxs-lookup"><span data-stu-id="ab66a-112">scheme</span></span>|<span data-ttu-id="ab66a-113">Строка, в которой указана группа параметров протокола, связанных с COM-портом.</span><span class="sxs-lookup"><span data-stu-id="ab66a-113">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab66a-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ab66a-114">Child Elements</span></span>  

 <span data-ttu-id="ab66a-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ab66a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab66a-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ab66a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ab66a-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ab66a-117">Element</span></span>|<span data-ttu-id="ab66a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ab66a-118">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="ab66a-119">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="ab66a-119">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab66a-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ab66a-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
