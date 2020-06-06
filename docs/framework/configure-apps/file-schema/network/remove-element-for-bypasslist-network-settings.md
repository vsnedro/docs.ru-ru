---
title: Элемент <remove> для bypasslist (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 97b49a8a520d6a4f72945366874991d2deb18710
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697896"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="3988e-102">Элемент \<remove> для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="3988e-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="3988e-103">Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="3988e-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  

## <a name="syntax"></a><span data-ttu-id="3988e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3988e-104">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3988e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3988e-105">Attributes and Elements</span></span>

<span data-ttu-id="3988e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3988e-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3988e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3988e-107">Attributes</span></span>

|<span data-ttu-id="3988e-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="3988e-108">**Attribute**</span></span>|<span data-ttu-id="3988e-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3988e-109">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="3988e-110">Регулярное выражение, описывающее IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="3988e-110">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3988e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3988e-111">Child Elements</span></span>

<span data-ttu-id="3988e-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3988e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3988e-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3988e-113">Parent Elements</span></span>

|<span data-ttu-id="3988e-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="3988e-114">**Element**</span></span>|<span data-ttu-id="3988e-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3988e-115">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="3988e-116">bypasslist</span><span class="sxs-lookup"><span data-stu-id="3988e-116">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="3988e-117">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="3988e-117">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3988e-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="3988e-118">Remarks</span></span>

<span data-ttu-id="3988e-119">`remove`Элемент удаляет регулярные выражения, описывающие IP-адреса или имена DNS-серверов, из списка адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="3988e-119">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="3988e-120">Адреса были определены ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3988e-120">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="3988e-121">Значение `address` атрибута должно быть регулярным выражением, описывающим набор IP-адресов или имен узлов.</span><span class="sxs-lookup"><span data-stu-id="3988e-121">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="3988e-122">Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3988e-122">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="3988e-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="3988e-123">Configuration Files</span></span>

<span data-ttu-id="3988e-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3988e-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="3988e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="3988e-125">Example</span></span>

<span data-ttu-id="3988e-126">В следующем примере удаляется предыдущее определение для домена adventure-works.com, а затем домен contoso.com добавляется в список обхода.</span><span class="sxs-lookup"><span data-stu-id="3988e-126">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="3988e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3988e-127">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="3988e-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3988e-128">Network Settings Schema</span></span>](index.md)
