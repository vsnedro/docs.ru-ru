---
title: Элемент <add> для webRequestModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: 8d792b967d967540469dca7c090e0f905ecb2e6b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201763"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="adaaf-102">Элемент \<add> для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="adaaf-102">\<add> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="adaaf-103">Добавляет пользовательский модуль веб-запросов в приложение.</span><span class="sxs-lookup"><span data-stu-id="adaaf-103">Adds a custom Web request module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="adaaf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adaaf-104">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adaaf-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="adaaf-105">Attributes and Elements</span></span>  

 <span data-ttu-id="adaaf-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="adaaf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adaaf-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="adaaf-107">Attributes</span></span>  
  
|<span data-ttu-id="adaaf-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="adaaf-108">**Attribute**</span></span>|<span data-ttu-id="adaaf-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="adaaf-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="adaaf-110">Префикс URI для запросов, обрабатываемых этим модулем веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="adaaf-110">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="adaaf-111">Полное имя типа (обозначенное <xref:System.Type.FullName%2A> свойством) и имя сборки (обозначенное <xref:System.Reflection.Assembly.FullName%2A> свойством), разделенные запятыми, которые реализуют этот модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="adaaf-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="adaaf-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="adaaf-112">Child Elements</span></span>  

 <span data-ttu-id="adaaf-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="adaaf-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="adaaf-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="adaaf-114">Parent Elements</span></span>  
  
|<span data-ttu-id="adaaf-115">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="adaaf-115">**Element**</span></span>|<span data-ttu-id="adaaf-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="adaaf-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="adaaf-117">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="adaaf-117">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="adaaf-118">Указывает модули, используемые для запроса сведений от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="adaaf-118">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adaaf-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="adaaf-119">Remarks</span></span>  

 <span data-ttu-id="adaaf-120">`prefix`Атрибут определяет префикс URI, который использует указанный модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="adaaf-120">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="adaaf-121">Модули веб-запросов обычно регистрируются для работы с конкретным протоколом, например HTTP или FTP, но могут быть зарегистрированы, чтобы обрабатывать запросы к определенному серверу или пути на сервере.</span><span class="sxs-lookup"><span data-stu-id="adaaf-121">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="adaaf-122">Модуль веб-запросов создается, когда в метод передается соответствующий префикс URI <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="adaaf-122">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="adaaf-123">Значение `prefix` атрибута должно быть начальными символами допустимого URI.</span><span class="sxs-lookup"><span data-stu-id="adaaf-123">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="adaaf-124">Например, `http` или `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="adaaf-124">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="adaaf-125">Значением `type` атрибута должно быть допустимое имя типа и соответствующее имя сборки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="adaaf-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="adaaf-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="adaaf-126">Configuration Files</span></span>  

 <span data-ttu-id="adaaf-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="adaaf-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="adaaf-128">Пример</span><span class="sxs-lookup"><span data-stu-id="adaaf-128">Example</span></span>  

 <span data-ttu-id="adaaf-129">В следующем примере регистрируется пользовательский модуль веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="adaaf-129">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="adaaf-130">Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="adaaf-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="adaaf-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="adaaf-131">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="adaaf-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="adaaf-132">Network Settings Schema</span></span>](index.md)
