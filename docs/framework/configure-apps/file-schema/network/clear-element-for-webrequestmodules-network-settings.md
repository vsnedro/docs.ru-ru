---
title: Элемент <clear> для webRequestModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 892058dd8af8a38bd7bde868b34a2c6899d9a989
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184044"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="3f7cc-102">Элемент \<clear> для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="3f7cc-102">\<clear> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="3f7cc-103">Удаляет из приложения все зарегистрированные модули веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="3f7cc-103">Removes all registered Web request modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="3f7cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f7cc-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f7cc-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3f7cc-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3f7cc-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3f7cc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f7cc-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3f7cc-107">Attributes</span></span>  

 <span data-ttu-id="3f7cc-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3f7cc-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3f7cc-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3f7cc-109">Child Elements</span></span>  

 <span data-ttu-id="3f7cc-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3f7cc-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f7cc-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3f7cc-111">Parent Elements</span></span>  
  
|<span data-ttu-id="3f7cc-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="3f7cc-112">**Element**</span></span>|<span data-ttu-id="3f7cc-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3f7cc-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3f7cc-114">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="3f7cc-114">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="3f7cc-115">Указывает модули, используемые для запроса сведений от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="3f7cc-115">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f7cc-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="3f7cc-116">Remarks</span></span>  

 <span data-ttu-id="3f7cc-117">`clear`Элемент удаляет все зарегистрированные модули веб-запросов, определенные ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3f7cc-117">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3f7cc-118">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="3f7cc-118">Configuration Files</span></span>  

 <span data-ttu-id="3f7cc-119">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3f7cc-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f7cc-120">Пример</span><span class="sxs-lookup"><span data-stu-id="3f7cc-120">Example</span></span>  

 <span data-ttu-id="3f7cc-121">В следующем примере очищаются все модули веб-запросов, а затем выполняется регистрация модуля веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="3f7cc-121">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f7cc-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3f7cc-122">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="3f7cc-123">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3f7cc-123">Network Settings Schema</span></span>](index.md)
