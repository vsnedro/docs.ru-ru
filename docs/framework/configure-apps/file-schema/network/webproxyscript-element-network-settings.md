---
title: Элемент <webProxyScript> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: dbad888cd0537f63c09840ac1053f924db9ea9bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089061"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="ac673-102">Элемент \<webProxyScript> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ac673-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="ac673-103">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="ac673-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="ac673-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac673-104">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac673-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ac673-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ac673-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ac673-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac673-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ac673-107">Attributes</span></span>  
  
|<span data-ttu-id="ac673-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ac673-108">Attribute</span></span>|<span data-ttu-id="ac673-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="ac673-109">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="ac673-110">Указывает максимальное время загрузки скрипта в часах, минутах и секундах.</span><span class="sxs-lookup"><span data-stu-id="ac673-110">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="ac673-111">Значение по умолчанию — одна минута.</span><span class="sxs-lookup"><span data-stu-id="ac673-111">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac673-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ac673-112">Child Elements</span></span>  
 <span data-ttu-id="ac673-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ac673-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac673-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ac673-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ac673-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ac673-115">Element</span></span>|<span data-ttu-id="ac673-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ac673-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac673-117">параметры</span><span class="sxs-lookup"><span data-stu-id="ac673-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="ac673-118">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="ac673-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac673-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac673-119">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ac673-120">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="ac673-120">Configuration Files</span></span>  
 <span data-ttu-id="ac673-121">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ac673-121">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac673-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ac673-122">See also</span></span>

- [<span data-ttu-id="ac673-123">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ac673-123">Network Settings Schema</span></span>](index.md)
