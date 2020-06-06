---
title: Элемент <remove> для webRequestModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154729"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="c6163-102">Элемент \<remove> для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="c6163-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="c6163-103">Удаляет пользовательский модуль веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="c6163-103">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="c6163-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6163-104">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6163-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c6163-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c6163-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c6163-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6163-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6163-107">Attributes</span></span>  
  
|<span data-ttu-id="c6163-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="c6163-108">**Attribute**</span></span>|<span data-ttu-id="c6163-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c6163-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="c6163-110">Префикс URI для запросов, обрабатываемых этим модулем веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="c6163-110">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6163-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6163-111">Child Elements</span></span>  
 <span data-ttu-id="c6163-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c6163-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6163-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6163-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c6163-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="c6163-114">**Element**</span></span>|<span data-ttu-id="c6163-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c6163-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c6163-116">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="c6163-116">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="c6163-117">Указывает модули, используемые для запроса сведений от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="c6163-117">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6163-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6163-118">Remarks</span></span>  
 <span data-ttu-id="c6163-119">`remove`Элемент удаляет зарегистрированный модуль веб-запросов для указанного префикса URI.</span><span class="sxs-lookup"><span data-stu-id="c6163-119">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="c6163-120">Значение `prefix` атрибута должно быть начальными символами допустимого универсального кода ресурса (URI), например " `http` " или " `http://www.contoso.com` ".</span><span class="sxs-lookup"><span data-stu-id="c6163-120">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c6163-121">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="c6163-121">Configuration Files</span></span>  
 <span data-ttu-id="c6163-122">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c6163-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6163-123">Пример</span><span class="sxs-lookup"><span data-stu-id="c6163-123">Example</span></span>  

<span data-ttu-id="c6163-124">В следующем примере удаляется существующий модуль веб-запросов для HTTP, а затем регистрируется новый пользовательский модуль веб-запросов для HTTP-запросов к `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c6163-124">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6163-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c6163-125">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="c6163-126">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="c6163-126">Network Settings Schema</span></span>](index.md)
