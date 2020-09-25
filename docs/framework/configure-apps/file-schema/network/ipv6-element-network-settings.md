---
title: Элемент <ipv6> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: 44ef0b8e1b6dc6ad0efde6b26ad7d4700e06f2c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178337"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="08c37-102">Элемент \<ipv6> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="08c37-102">\<ipv6> Element (Network Settings)</span></span>

<span data-ttu-id="08c37-103">Включает отклики протокола IP версии 6 (IPv6) от устаревших членов <xref:System.Net.Dns> класса.</span><span class="sxs-lookup"><span data-stu-id="08c37-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="08c37-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08c37-104">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08c37-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08c37-105">Attributes and Elements</span></span>  

 <span data-ttu-id="08c37-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08c37-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08c37-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08c37-107">Attributes</span></span>  
  
|<span data-ttu-id="08c37-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="08c37-108">**Attribute**</span></span>|<span data-ttu-id="08c37-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="08c37-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="08c37-110">Указывает, <xref:System.Net.Dns> возвращают ли члены класса IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="08c37-110">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="08c37-111">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="08c37-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08c37-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08c37-112">Child Elements</span></span>  

 <span data-ttu-id="08c37-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="08c37-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08c37-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08c37-114">Parent Elements</span></span>  
  
|<span data-ttu-id="08c37-115">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="08c37-115">**Element**</span></span>|<span data-ttu-id="08c37-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="08c37-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="08c37-117">параметры</span><span class="sxs-lookup"><span data-stu-id="08c37-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="08c37-118">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="08c37-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08c37-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="08c37-119">Remarks</span></span>  

 <span data-ttu-id="08c37-120">Этот параметр включает поддержку IPv6 для устаревших членов <xref:System.Net.Dns> класса: <xref:System.Net.Dns.BeginGetHostByName%2A> , <xref:System.Net.Dns.BeginResolve%2A> ,,, <xref:System.Net.Dns.EndGetHostByName%2A> , <xref:System.Net.Dns.EndResolve%2A> <xref:System.Net.Dns.GetHostByAddress%2A> <xref:System.Net.Dns.GetHostByName%2A> и <xref:System.Net.Dns.Resolve%2A> .</span><span class="sxs-lookup"><span data-stu-id="08c37-120">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="08c37-121">Для других членов <xref:System.Net?displayProperty=nameWithType> пространства имен IPv6-адреса могут возвращаться, если в операционной системе включен протокол IPv6.</span><span class="sxs-lookup"><span data-stu-id="08c37-121">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="08c37-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="08c37-122">Configuration Files</span></span>  

 <span data-ttu-id="08c37-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="08c37-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08c37-124">Пример</span><span class="sxs-lookup"><span data-stu-id="08c37-124">Example</span></span>  

 <span data-ttu-id="08c37-125">В следующем примере показано, как включить поддержку IPv6 для <xref:System.Net.Dns> класса.</span><span class="sxs-lookup"><span data-stu-id="08c37-125">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="08c37-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="08c37-126">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="08c37-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="08c37-127">Network Settings Schema</span></span>](index.md)
