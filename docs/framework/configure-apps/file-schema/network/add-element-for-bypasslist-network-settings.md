---
title: Элемент <add> для bypasslist (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 927a43f352fd776d9e6ba52ebea6ba2a1ccd4d48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149495"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="5fb51-102">Элемент \<add> для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="5fb51-102">\<add> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="5fb51-103">Добавление в список обхода прокси IP-адреса или DNS-имени.</span><span class="sxs-lookup"><span data-stu-id="5fb51-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="5fb51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fb51-104">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fb51-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5fb51-105">Attributes and Elements</span></span>  

 <span data-ttu-id="5fb51-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5fb51-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fb51-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb51-107">Attributes</span></span>  
  
|<span data-ttu-id="5fb51-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="5fb51-108">**Attribute**</span></span>|<span data-ttu-id="5fb51-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5fb51-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="5fb51-110">**address**</span><span class="sxs-lookup"><span data-stu-id="5fb51-110">**address**</span></span>|<span data-ttu-id="5fb51-111">Регулярное выражение, описывающее IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="5fb51-111">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fb51-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5fb51-112">Child Elements</span></span>  

 <span data-ttu-id="5fb51-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5fb51-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5fb51-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5fb51-114">Parent Elements</span></span>  
  
|<span data-ttu-id="5fb51-115">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="5fb51-115">**Element**</span></span>|<span data-ttu-id="5fb51-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5fb51-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5fb51-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="5fb51-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="5fb51-118">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="5fb51-118">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fb51-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="5fb51-119">Remarks</span></span>  

 <span data-ttu-id="5fb51-120">`add`Элемент вставляет регулярные выражения, описывающие IP-адреса или имена DNS-серверов, в список адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="5fb51-120">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="5fb51-121">Значение `address` атрибута должно быть регулярным выражением, описывающим набор IP-адресов или имен узлов.</span><span class="sxs-lookup"><span data-stu-id="5fb51-121">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="5fb51-122">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="5fb51-122">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="5fb51-123">Регулярное выражение "[a-z] + \\ . contoso \\ . com" соответствует любому узлу в домене contoso.com, но также соответствует любому узлу в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="5fb51-123">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="5fb51-124">Чтобы сопоставить только узел в домене contoso.com, используйте привязку ("$"): "[a-z] + \\ . contoso \\ . com $".</span><span class="sxs-lookup"><span data-stu-id="5fb51-124">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="5fb51-125">Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5fb51-125">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5fb51-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="5fb51-126">Configuration Files</span></span>  

 <span data-ttu-id="5fb51-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5fb51-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb51-128">Пример</span><span class="sxs-lookup"><span data-stu-id="5fb51-128">Example</span></span>  

 <span data-ttu-id="5fb51-129">В следующем примере в список обхода добавляется два адреса.</span><span class="sxs-lookup"><span data-stu-id="5fb51-129">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="5fb51-130">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором пропускается прокси-сервер для всех серверов, IP-адрес которых начинается с 192,168.</span><span class="sxs-lookup"><span data-stu-id="5fb51-130">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5fb51-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5fb51-131">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="5fb51-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="5fb51-132">Network Settings Schema</span></span>](index.md)
