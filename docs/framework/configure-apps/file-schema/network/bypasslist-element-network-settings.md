---
title: Элемент <bypasslist> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154950"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="2a029-102">Элемент \<bypasslist> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2a029-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="2a029-103">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2a029-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a><span data-ttu-id="2a029-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a029-104">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a029-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2a029-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2a029-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2a029-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a029-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2a029-107">Attributes</span></span>  
 <span data-ttu-id="2a029-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2a029-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2a029-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2a029-109">Child Elements</span></span>  
  
|<span data-ttu-id="2a029-110">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2a029-110">**Element**</span></span>|<span data-ttu-id="2a029-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2a029-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2a029-112">добавление</span><span class="sxs-lookup"><span data-stu-id="2a029-112">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="2a029-113">Добавление в список обхода прокси IP-адреса или DNS-имени.</span><span class="sxs-lookup"><span data-stu-id="2a029-113">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="2a029-114">открытым</span><span class="sxs-lookup"><span data-stu-id="2a029-114">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="2a029-115">Очищает список обхода.</span><span class="sxs-lookup"><span data-stu-id="2a029-115">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="2a029-116">remove</span><span class="sxs-lookup"><span data-stu-id="2a029-116">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="2a029-117">Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2a029-117">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a029-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2a029-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2a029-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2a029-119">**Element**</span></span>|<span data-ttu-id="2a029-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2a029-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2a029-121">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2a029-121">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2a029-122">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="2a029-122">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a029-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a029-123">Remarks</span></span>  
 <span data-ttu-id="2a029-124">Список обхода содержит регулярные выражения, описывающие URI, которые <xref:System.Net.WebRequest> обращаются к экземплярам напрямую, а не через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2a029-124">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="2a029-125">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="2a029-125">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="2a029-126">Регулярное выражение "[a-z] + \\ . contoso \\ . com" соответствует любому узлу в домене contoso.com, но также соответствует любому узлу в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="2a029-126">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="2a029-127">Чтобы сопоставить только узел в домене contoso.com, используйте привязку ("$"): "[a-z] + \\ . contoso \\ . com $".</span><span class="sxs-lookup"><span data-stu-id="2a029-127">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="2a029-128">Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2a029-128">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2a029-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="2a029-129">Configuration Files</span></span>  
 <span data-ttu-id="2a029-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2a029-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a029-131">Пример</span><span class="sxs-lookup"><span data-stu-id="2a029-131">Example</span></span>  
 <span data-ttu-id="2a029-132">В следующем примере в список обхода добавляется два адреса.</span><span class="sxs-lookup"><span data-stu-id="2a029-132">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="2a029-133">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором случае прокси-сервер обходится для всех серверов, IP-адреса которых начинаются с 192,168.</span><span class="sxs-lookup"><span data-stu-id="2a029-133">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a029-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2a029-134">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="2a029-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2a029-135">Network Settings Schema</span></span>](index.md)
