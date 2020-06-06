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
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155081"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="144a6-102">Элемент \<add> для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="144a6-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="144a6-103">Добавление в список обхода прокси IP-адреса или DNS-имени.</span><span class="sxs-lookup"><span data-stu-id="144a6-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="144a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="144a6-104">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="144a6-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="144a6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="144a6-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="144a6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="144a6-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="144a6-107">Attributes</span></span>  
  
|<span data-ttu-id="144a6-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="144a6-108">**Attribute**</span></span>|<span data-ttu-id="144a6-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="144a6-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="144a6-110">**address**</span><span class="sxs-lookup"><span data-stu-id="144a6-110">**address**</span></span>|<span data-ttu-id="144a6-111">Регулярное выражение, описывающее IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="144a6-111">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="144a6-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="144a6-112">Child Elements</span></span>  
 <span data-ttu-id="144a6-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="144a6-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="144a6-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="144a6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="144a6-115">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="144a6-115">**Element**</span></span>|<span data-ttu-id="144a6-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="144a6-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="144a6-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="144a6-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="144a6-118">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="144a6-118">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="144a6-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="144a6-119">Remarks</span></span>  
 <span data-ttu-id="144a6-120">`add`Элемент вставляет регулярные выражения, описывающие IP-адреса или имена DNS-серверов, в список адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="144a6-120">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="144a6-121">Значение `address` атрибута должно быть регулярным выражением, описывающим набор IP-адресов или имен узлов.</span><span class="sxs-lookup"><span data-stu-id="144a6-121">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="144a6-122">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="144a6-122">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="144a6-123">Регулярное выражение "[a-z] + \\ . contoso \\ . com" соответствует любому узлу в домене contoso.com, но также соответствует любому узлу в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="144a6-123">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="144a6-124">Чтобы сопоставить только узел в домене contoso.com, используйте привязку ("$"): "[a-z] + \\ . contoso \\ . com $".</span><span class="sxs-lookup"><span data-stu-id="144a6-124">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="144a6-125">Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="144a6-125">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="144a6-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="144a6-126">Configuration Files</span></span>  
 <span data-ttu-id="144a6-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="144a6-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="144a6-128">Пример</span><span class="sxs-lookup"><span data-stu-id="144a6-128">Example</span></span>  
 <span data-ttu-id="144a6-129">В следующем примере в список обхода добавляется два адреса.</span><span class="sxs-lookup"><span data-stu-id="144a6-129">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="144a6-130">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором пропускается прокси-сервер для всех серверов, IP-адрес которых начинается с 192,168.</span><span class="sxs-lookup"><span data-stu-id="144a6-130">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="144a6-131">См. также</span><span class="sxs-lookup"><span data-stu-id="144a6-131">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="144a6-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="144a6-132">Network Settings Schema</span></span>](index.md)
