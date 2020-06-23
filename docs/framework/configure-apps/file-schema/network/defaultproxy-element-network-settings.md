---
title: Элемент <defaultProxy> (параметры сети)
description: <defaultProxy>Элемент Параметры сети настраивает прокси-сервер HTTP в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 85004d49ce7605b050709a3019592ec696a7bada
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141635"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="b15bf-103">Элемент \<defaultProxy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b15bf-103">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="b15bf-104">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="b15bf-104">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="b15bf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b15bf-105">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="True|False"  
  useDefaultCredentials="True|False">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b15bf-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b15bf-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b15bf-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b15bf-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b15bf-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b15bf-108">Attributes</span></span>  
  
|<span data-ttu-id="b15bf-109">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b15bf-109">**Element**</span></span>|<span data-ttu-id="b15bf-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b15bf-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="b15bf-111">Указывает, используется ли веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="b15bf-111">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="b15bf-112">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="b15bf-112">The default value is `True`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="b15bf-113">Указывает, используются ли учетные данные по умолчанию для этого узла для доступа к веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="b15bf-113">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="b15bf-114">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="b15bf-114">The default value is `False`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b15bf-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b15bf-115">Child Elements</span></span>  
  
|<span data-ttu-id="b15bf-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b15bf-116">**Element**</span></span>|<span data-ttu-id="b15bf-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b15bf-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b15bf-118">bypasslist</span><span class="sxs-lookup"><span data-stu-id="b15bf-118">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="b15bf-119">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="b15bf-119">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="b15bf-120">модуль</span><span class="sxs-lookup"><span data-stu-id="b15bf-120">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="b15bf-121">Добавляет в приложение новый модуль прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b15bf-121">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="b15bf-122">-</span><span class="sxs-lookup"><span data-stu-id="b15bf-122">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="b15bf-123">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="b15bf-123">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b15bf-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b15bf-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b15bf-125">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b15bf-125">**Element**</span></span>|<span data-ttu-id="b15bf-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b15bf-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b15bf-127">system.net</span><span class="sxs-lookup"><span data-stu-id="b15bf-127">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="b15bf-128">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b15bf-128">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b15bf-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="b15bf-129">Remarks</span></span>  
 <span data-ttu-id="b15bf-130">Если элемент defaultProxy пуст, будут использоваться параметры прокси-сервера из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b15bf-130">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="b15bf-131">Это поведение отличается от поведения в .NET Framework версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="b15bf-131">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b15bf-132">Исключение возникает, если элемент [module](module-element-network-settings.md) указывает на неоткрытый тип, тип не является производным от <xref:System.Net.IWebProxy> класса, возникло исключение из конструктора без параметров данного объекта или возникло исключение при получении указанного системой прокси-сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b15bf-132">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="b15bf-133">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.</span><span class="sxs-lookup"><span data-stu-id="b15bf-133">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b15bf-134">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b15bf-134">Configuration Files</span></span>  
 <span data-ttu-id="b15bf-135">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b15bf-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b15bf-136">Пример</span><span class="sxs-lookup"><span data-stu-id="b15bf-136">Example</span></span>  
 <span data-ttu-id="b15bf-137">В следующем примере используются значения по умолчанию из прокси-сервера Internet Explorer, указывается адрес прокси-сервера и выполняется обход прокси-сервера для локального доступа и contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b15bf-137">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b15bf-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b15bf-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="b15bf-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b15bf-139">Network Settings Schema</span></span>](index.md)
