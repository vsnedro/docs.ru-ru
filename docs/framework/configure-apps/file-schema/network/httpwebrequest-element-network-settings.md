---
title: Элемент <httpWebRequest> (параметры сети)
description: <httpWebRequest>Элемент Параметры сети настраивает параметры веб-запроса в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 59ab425dcef8ac5283035910a9d78a89a16be8b1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504593"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="cb614-103">Элемент \<httpWebRequest> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="cb614-103">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="cb614-104">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="cb614-104">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="cb614-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb614-105">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb614-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb614-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cb614-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb614-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb614-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb614-108">Attributes</span></span>  
  
|<span data-ttu-id="cb614-109">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="cb614-109">**Attribute**</span></span>|<span data-ttu-id="cb614-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cb614-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="cb614-111">Задает максимальную длину заголовка ответа в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="cb614-111">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="cb614-112">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="cb614-112">The default is 64.</span></span> <span data-ttu-id="cb614-113">Значение-1 указывает на то, что в заголовках ответа ограничение размера не накладывается.</span><span class="sxs-lookup"><span data-stu-id="cb614-113">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="cb614-114">Указывает максимальную длину ответа на ошибку в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="cb614-114">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="cb614-115">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="cb614-115">The default is 64.</span></span> <span data-ttu-id="cb614-116">Значение-1 указывает, что в ответе на ошибку не будет накладывается никаких ограничений на размер.</span><span class="sxs-lookup"><span data-stu-id="cb614-116">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="cb614-117">Указывает максимальную длину отправки в ответ на несанкционированный код ошибки в байтах.</span><span class="sxs-lookup"><span data-stu-id="cb614-117">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="cb614-118">Значение по умолчанию — -1.</span><span class="sxs-lookup"><span data-stu-id="cb614-118">The default is -1.</span></span> <span data-ttu-id="cb614-119">Значение -1 указывает на отсутствие ограничений.</span><span class="sxs-lookup"><span data-stu-id="cb614-119">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="cb614-120">Указывает, включен ли анализ ненадежных заголовков.</span><span class="sxs-lookup"><span data-stu-id="cb614-120">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="cb614-121">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="cb614-121">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb614-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb614-122">Child Elements</span></span>  
 <span data-ttu-id="cb614-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cb614-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb614-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb614-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cb614-125">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="cb614-125">**Element**</span></span>|<span data-ttu-id="cb614-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cb614-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cb614-127">параметры</span><span class="sxs-lookup"><span data-stu-id="cb614-127">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="cb614-128">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="cb614-128">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb614-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb614-129">Remarks</span></span>  
 <span data-ttu-id="cb614-130">По умолчанию .NET Framework строго применяет RFC 2616 для синтаксического анализа URI.</span><span class="sxs-lookup"><span data-stu-id="cb614-130">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="cb614-131">Некоторые серверные ответы могут содержать управляющие символы в запрещенных полях, что приведет к вызову <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> метода <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="cb614-131">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="cb614-132">Если **усеунсафехеадерпарсинг** имеет значение **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> в этом случае не будет создаваться исключение, однако приложение будет уязвимо для нескольких форм атак с синтаксическим анализом URI.</span><span class="sxs-lookup"><span data-stu-id="cb614-132">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="cb614-133">Лучшим решением является изменение сервера, чтобы ответ не включал управляющие символы.</span><span class="sxs-lookup"><span data-stu-id="cb614-133">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cb614-134">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="cb614-134">Configuration Files</span></span>  
 <span data-ttu-id="cb614-135">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cb614-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb614-136">Пример</span><span class="sxs-lookup"><span data-stu-id="cb614-136">Example</span></span>  
 <span data-ttu-id="cb614-137">В следующем примере показано, как задать большую, чем нормальную максимальную длину заголовка.</span><span class="sxs-lookup"><span data-stu-id="cb614-137">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb614-138">См. также</span><span class="sxs-lookup"><span data-stu-id="cb614-138">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="cb614-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="cb614-139">Network Settings Schema</span></span>](index.md)
