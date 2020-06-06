---
title: Элемент <clear> для bypasslist (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154937"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="3975a-102">Элемент \<clear> для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="3975a-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="3975a-103">Очищает список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="3975a-103">Clears the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="3975a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3975a-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3975a-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3975a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3975a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3975a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3975a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3975a-107">Attributes</span></span>  
 <span data-ttu-id="3975a-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3975a-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3975a-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3975a-109">Child Elements</span></span>  
 <span data-ttu-id="3975a-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="3975a-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3975a-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3975a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="3975a-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="3975a-112">**Element**</span></span>|<span data-ttu-id="3975a-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3975a-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3975a-114">bypasslist</span><span class="sxs-lookup"><span data-stu-id="3975a-114">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="3975a-115">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="3975a-115">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3975a-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="3975a-116">Remarks</span></span>  
 <span data-ttu-id="3975a-117">`clear`Элемент удаляет все записи из списка обхода.</span><span class="sxs-lookup"><span data-stu-id="3975a-117">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3975a-118">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="3975a-118">Configuration Files</span></span>  
 <span data-ttu-id="3975a-119">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3975a-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3975a-120">Пример</span><span class="sxs-lookup"><span data-stu-id="3975a-120">Example</span></span>  
 <span data-ttu-id="3975a-121">В следующем примере очищается список обхода, а затем два адреса добавляются в список обхода.</span><span class="sxs-lookup"><span data-stu-id="3975a-121">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="3975a-122">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором пропускается прокси-сервер для всех серверов, IP-адрес которых начинается с 192,168.</span><span class="sxs-lookup"><span data-stu-id="3975a-122">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="3975a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3975a-123">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="3975a-124">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3975a-124">Network Settings Schema</span></span>](index.md)
