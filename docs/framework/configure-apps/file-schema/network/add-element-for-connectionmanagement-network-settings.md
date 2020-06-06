---
title: Элемент <add> для connectionManagement (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 093b68d31e03094bedefa96a2f2d53eb3d84edf0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155015"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="fc7ea-102">Элемент \<add> для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="fc7ea-102">\<add> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="fc7ea-103">Добавляет IP-адрес или DNS-имя в список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-103">Adds an IP address or DNS name to the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="fc7ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc7ea-104">Syntax</span></span>  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc7ea-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fc7ea-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fc7ea-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc7ea-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fc7ea-107">Attributes</span></span>  
  
|<span data-ttu-id="fc7ea-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="fc7ea-108">**Attribute**</span></span>|<span data-ttu-id="fc7ea-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fc7ea-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="fc7ea-110">Строка, описывающая IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-110">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="fc7ea-111">Максимальное число разрешенных подключений к серверу.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-111">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="fc7ea-112">Если значение не предоставлено, используется значение по умолчанию 2.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-112">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc7ea-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fc7ea-113">Child Elements</span></span>  
 <span data-ttu-id="fc7ea-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc7ea-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fc7ea-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fc7ea-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="fc7ea-116">**Element**</span></span>|<span data-ttu-id="fc7ea-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fc7ea-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fc7ea-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="fc7ea-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="fc7ea-119">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc7ea-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc7ea-120">Remarks</span></span>  
 <span data-ttu-id="fc7ea-121">В качестве значения атрибута `address` должна быть задана либо звездочка, указывающая все подключения, либо строка в форме `<schema>://<idn_hostname>[:<port>]`.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-121">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="fc7ea-122">Если URI, переданный в какие-либо API HTTP, содержит символы Юникода, то имя будет преобразовано внутренним образом с помощью свойства <xref:System.Uri.DnsSafeHost%2A>, которое может возвращать строку Punycode (поведение, зависящее от текущей конфигурации IDN).</span><span class="sxs-lookup"><span data-stu-id="fc7ea-122">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fc7ea-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc7ea-123">Configuration Files</span></span>  
 <span data-ttu-id="fc7ea-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fc7ea-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc7ea-125">Пример</span><span class="sxs-lookup"><span data-stu-id="fc7ea-125">Example</span></span>  
 <span data-ttu-id="fc7ea-126">В следующем примере приложение настраивается для использования четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="fc7ea-126">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc7ea-127">См. также</span><span class="sxs-lookup"><span data-stu-id="fc7ea-127">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="fc7ea-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="fc7ea-128">Network Settings Schema</span></span>](index.md)
