---
title: Элемент <defaultProxy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 0945629c1395917bc1cf825f2ba84d20afa99957
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698205"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="2c480-102">Элемент \<defaultProxy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2c480-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="2c480-103">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="2c480-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="2c480-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c480-104">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c480-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2c480-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2c480-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2c480-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c480-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2c480-107">Attributes</span></span>  
  
|<span data-ttu-id="2c480-108">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2c480-108">**Element**</span></span>|<span data-ttu-id="2c480-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2c480-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="2c480-110">Указывает, используется ли веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="2c480-110">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="2c480-111">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="2c480-111">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="2c480-112">Указывает, используются ли учетные данные по умолчанию для этого узла для доступа к веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="2c480-112">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="2c480-113">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2c480-113">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c480-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2c480-114">Child Elements</span></span>  
  
|<span data-ttu-id="2c480-115">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2c480-115">**Element**</span></span>|<span data-ttu-id="2c480-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2c480-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2c480-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="2c480-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="2c480-118">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2c480-118">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="2c480-119">модуль</span><span class="sxs-lookup"><span data-stu-id="2c480-119">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="2c480-120">Добавляет в приложение новый модуль прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2c480-120">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="2c480-121">proxy</span><span class="sxs-lookup"><span data-stu-id="2c480-121">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="2c480-122">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2c480-122">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c480-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2c480-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2c480-124">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2c480-124">**Element**</span></span>|<span data-ttu-id="2c480-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2c480-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2c480-126">system.net</span><span class="sxs-lookup"><span data-stu-id="2c480-126">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="2c480-127">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="2c480-127">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c480-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c480-128">Remarks</span></span>  
 <span data-ttu-id="2c480-129">Если элемент defaultProxy пуст, будут использоваться параметры прокси-сервера из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2c480-129">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="2c480-130">Это поведение отличается от поведения в .NET Framework версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="2c480-130">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2c480-131">Исключение возникает, если элемент [module](module-element-network-settings.md) указывает на неоткрытый тип, тип не является производным от <xref:System.Net.IWebProxy> класса, возникло исключение из конструктора без параметров данного объекта или возникло исключение при получении указанного системой прокси-сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2c480-131">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="2c480-132">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.</span><span class="sxs-lookup"><span data-stu-id="2c480-132">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2c480-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="2c480-133">Configuration Files</span></span>  
 <span data-ttu-id="2c480-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2c480-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c480-135">Пример</span><span class="sxs-lookup"><span data-stu-id="2c480-135">Example</span></span>  
 <span data-ttu-id="2c480-136">В следующем примере используются значения по умолчанию из прокси-сервера Internet Explorer, указывается адрес прокси-сервера и выполняется обход прокси-сервера для локального доступа и contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2c480-136">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c480-137">См. также</span><span class="sxs-lookup"><span data-stu-id="2c480-137">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="2c480-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2c480-138">Network Settings Schema</span></span>](index.md)
