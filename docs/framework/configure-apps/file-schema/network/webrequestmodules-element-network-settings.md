---
title: Элемент <webRequestModules> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 9396ca393523dce5593531f332e5c07241987947
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187008"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="ff994-102">Элемент \<webRequestModules> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ff994-102">\<webRequestModules> Element (Network Settings)</span></span>

<span data-ttu-id="ff994-103">Указывает модули, используемые для запроса сведений от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="ff994-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a><span data-ttu-id="ff994-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff994-104">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff994-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff994-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ff994-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ff994-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff994-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff994-107">Attributes</span></span>  

 <span data-ttu-id="ff994-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff994-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff994-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff994-109">Child Elements</span></span>  
  
|<span data-ttu-id="ff994-110">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ff994-110">**Element**</span></span>|<span data-ttu-id="ff994-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ff994-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ff994-112">add</span><span class="sxs-lookup"><span data-stu-id="ff994-112">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ff994-113">Добавляет пользовательский модуль веб-запросов в приложение.</span><span class="sxs-lookup"><span data-stu-id="ff994-113">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="ff994-114">пусто</span><span class="sxs-lookup"><span data-stu-id="ff994-114">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ff994-115">Удаляет из приложения все зарегистрированные модули веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="ff994-115">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="ff994-116">remove</span><span class="sxs-lookup"><span data-stu-id="ff994-116">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ff994-117">Удаляет пользовательский модуль веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="ff994-117">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff994-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff994-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ff994-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ff994-119">**Element**</span></span>|<span data-ttu-id="ff994-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ff994-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ff994-121">system.net</span><span class="sxs-lookup"><span data-stu-id="ff994-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="ff994-122">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="ff994-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff994-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff994-123">Remarks</span></span>  

 <span data-ttu-id="ff994-124">Элемент `webRequestModules` регистрирует потомки класса <xref:System.Net.WebRequest>, чтобы обработать запросы информации к сетевым узлам.</span><span class="sxs-lookup"><span data-stu-id="ff994-124">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="ff994-125">Модули веб-запросов должны реализовывать <xref:System.Net.IWebRequestCreate> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ff994-125">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="ff994-126">.NET Framework включает модули веб-запросов для URI, которые начинаются с `http://` , `https://` и `file://` .</span><span class="sxs-lookup"><span data-stu-id="ff994-126">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="ff994-127">Модули по умолчанию можно переопределить только путем регистрации пользовательского модуля в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ff994-127">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ff994-128">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="ff994-128">Configuration Files</span></span>  

 <span data-ttu-id="ff994-129">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ff994-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff994-130">Пример</span><span class="sxs-lookup"><span data-stu-id="ff994-130">Example</span></span>  

 <span data-ttu-id="ff994-131">В следующем примере регистрируется HTTP-модуль по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ff994-131">The following example registers the default HTTP module.</span></span> <span data-ttu-id="ff994-132">Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="ff994-132">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff994-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff994-133">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="ff994-134">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ff994-134">Network Settings Schema</span></span>](index.md)
