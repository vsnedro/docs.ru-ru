---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252107"
---
# \<chunkedCookieHandler>
<span data-ttu-id="b6b75-101">Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="b6b75-101">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="b6b75-102">Этот элемент может присутствовать только в том случае, если `mode` атрибут `<cookieHandler>` элемента имеет значение "default" или "фрагментированный".</span><span class="sxs-lookup"><span data-stu-id="b6b75-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="b6b75-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6b75-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6b75-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6b75-104">Attributes and Elements</span></span>  
 <span data-ttu-id="b6b75-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6b75-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6b75-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6b75-106">Attributes</span></span>  
  
|<span data-ttu-id="b6b75-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b6b75-107">Attribute</span></span>|<span data-ttu-id="b6b75-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="b6b75-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6b75-109">chunkSize</span><span class="sxs-lookup"><span data-stu-id="b6b75-109">chunkSize</span></span>|<span data-ttu-id="b6b75-110">Максимальный размер (в символах) данных cookie HTTP для одного файла cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6b75-110">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="b6b75-111">При изменении размера фрагмента данных необходимо соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="b6b75-111">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="b6b75-112">Веб-браузеры имеют разные ограничения на размер файлов cookie и число допустимых для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="b6b75-112">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="b6b75-113">Например, исходная спецификация Netscape поменяет такие ограничения: 300 cookies Total, 4096 байт на заголовок файла cookie (включая метаданные, а не только значение файла cookie) и 20 файлов cookie на домен.</span><span class="sxs-lookup"><span data-stu-id="b6b75-113">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="b6b75-114">Значение по умолчанию — 2000.</span><span class="sxs-lookup"><span data-stu-id="b6b75-114">The default is 2000.</span></span> <span data-ttu-id="b6b75-115">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b6b75-115">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6b75-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6b75-116">Child Elements</span></span>  
 <span data-ttu-id="b6b75-117">Нет</span><span class="sxs-lookup"><span data-stu-id="b6b75-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6b75-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6b75-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b6b75-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6b75-119">Element</span></span>|<span data-ttu-id="b6b75-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b6b75-120">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="b6b75-121">Настраивает <xref:System.IdentityModel.Services.CookieHandler> , что <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) использует для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="b6b75-121">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6b75-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6b75-122">Remarks</span></span>  
 <span data-ttu-id="b6b75-123">При указании, <xref:System.IdentityModel.Services.ChunkedCookieHandler> задав `mode` `<cookieHandler>` для атрибута элемента значение "по умолчанию" или "фрагментированный", можно указать размер фрагмента, который обработчик файлов cookie использует для чтения и записи файлов cookie, включая `<chunkedCookieHandler>` дочерний элемент и устанавливая его `chunkSize` атрибут.</span><span class="sxs-lookup"><span data-stu-id="b6b75-123">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="b6b75-124">Если `<chunkedCookieHandler>` элемент отсутствует, используется размер фрагмента по умолчанию (2000 байт).</span><span class="sxs-lookup"><span data-stu-id="b6b75-124">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="b6b75-125">Этот элемент не может быть указан, если `mode` для атрибута задано значение Custom.</span><span class="sxs-lookup"><span data-stu-id="b6b75-125">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="b6b75-126">`<chunkedCookieHandler>`Элемент представлен <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> классом.</span><span class="sxs-lookup"><span data-stu-id="b6b75-126">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6b75-127">Пример</span><span class="sxs-lookup"><span data-stu-id="b6b75-127">Example</span></span>  
 <span data-ttu-id="b6b75-128">В следующем примере настраивается обработчик фрагментированных файлов cookie, который записывает файлы cookie в фрагменты 3000 байт.</span><span class="sxs-lookup"><span data-stu-id="b6b75-128">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6b75-129">См. также</span><span class="sxs-lookup"><span data-stu-id="b6b75-129">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
