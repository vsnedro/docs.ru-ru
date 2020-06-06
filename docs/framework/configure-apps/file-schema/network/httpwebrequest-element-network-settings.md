---
title: Элемент <httpWebRequest> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: d33dadc14510feb00e05ca557b507b0cf8fa0dd0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087460"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="d0022-102">Элемент \<httpWebRequest> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="d0022-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="d0022-103">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="d0022-103">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="d0022-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0022-104">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0022-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0022-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d0022-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0022-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0022-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0022-107">Attributes</span></span>  
  
|<span data-ttu-id="d0022-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="d0022-108">**Attribute**</span></span>|<span data-ttu-id="d0022-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d0022-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="d0022-110">Задает максимальную длину заголовка ответа в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="d0022-110">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="d0022-111">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="d0022-111">The default is 64.</span></span> <span data-ttu-id="d0022-112">Значение-1 указывает на то, что в заголовках ответа ограничение размера не накладывается.</span><span class="sxs-lookup"><span data-stu-id="d0022-112">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="d0022-113">Указывает максимальную длину ответа на ошибку в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="d0022-113">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="d0022-114">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="d0022-114">The default is 64.</span></span> <span data-ttu-id="d0022-115">Значение-1 указывает, что в ответе на ошибку не будет накладывается никаких ограничений на размер.</span><span class="sxs-lookup"><span data-stu-id="d0022-115">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="d0022-116">Указывает максимальную длину отправки в ответ на несанкционированный код ошибки в байтах.</span><span class="sxs-lookup"><span data-stu-id="d0022-116">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="d0022-117">Значение по умолчанию — -1.</span><span class="sxs-lookup"><span data-stu-id="d0022-117">The default is -1.</span></span> <span data-ttu-id="d0022-118">Значение -1 указывает на отсутствие ограничений.</span><span class="sxs-lookup"><span data-stu-id="d0022-118">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="d0022-119">Указывает, включен ли анализ ненадежных заголовков.</span><span class="sxs-lookup"><span data-stu-id="d0022-119">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="d0022-120">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="d0022-120">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0022-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0022-121">Child Elements</span></span>  
 <span data-ttu-id="d0022-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d0022-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0022-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0022-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d0022-124">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="d0022-124">**Element**</span></span>|<span data-ttu-id="d0022-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d0022-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d0022-126">параметры</span><span class="sxs-lookup"><span data-stu-id="d0022-126">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="d0022-127">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="d0022-127">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0022-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0022-128">Remarks</span></span>  
 <span data-ttu-id="d0022-129">По умолчанию .NET Framework строго применяет RFC 2616 для синтаксического анализа URI.</span><span class="sxs-lookup"><span data-stu-id="d0022-129">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="d0022-130">Некоторые серверные ответы могут содержать управляющие символы в запрещенных полях, что приведет к вызову <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> метода <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="d0022-130">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="d0022-131">Если **усеунсафехеадерпарсинг** имеет значение **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> в этом случае не будет создаваться исключение, однако приложение будет уязвимо для нескольких форм атак с синтаксическим анализом URI.</span><span class="sxs-lookup"><span data-stu-id="d0022-131">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="d0022-132">Лучшим решением является изменение сервера, чтобы ответ не включал управляющие символы.</span><span class="sxs-lookup"><span data-stu-id="d0022-132">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d0022-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="d0022-133">Configuration Files</span></span>  
 <span data-ttu-id="d0022-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d0022-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0022-135">Пример</span><span class="sxs-lookup"><span data-stu-id="d0022-135">Example</span></span>  
 <span data-ttu-id="d0022-136">В следующем примере показано, как задать большую, чем нормальную максимальную длину заголовка.</span><span class="sxs-lookup"><span data-stu-id="d0022-136">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0022-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d0022-137">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="d0022-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="d0022-138">Network Settings Schema</span></span>](index.md)
