---
title: Элемент <remove> для connectionManagement (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 46157482d7ceb42b352c68dc9b0eab4f7688bc5c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176179"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="0f314-102">Элемент \<remove> для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="0f314-102">\<remove> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="0f314-103">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="0f314-103">Removes an IP address or DNS name from the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="0f314-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f314-104">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f314-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f314-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0f314-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0f314-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f314-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f314-107">Attributes</span></span>  
  
|<span data-ttu-id="0f314-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="0f314-108">**Attribute**</span></span>|<span data-ttu-id="0f314-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0f314-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="0f314-110">IP-адрес или имя DNS.</span><span class="sxs-lookup"><span data-stu-id="0f314-110">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f314-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f314-111">Child Elements</span></span>  

 <span data-ttu-id="0f314-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0f314-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f314-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f314-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0f314-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="0f314-114">**Element**</span></span>|<span data-ttu-id="0f314-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0f314-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0f314-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="0f314-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="0f314-117">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="0f314-117">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f314-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f314-118">Remarks</span></span>  

 <span data-ttu-id="0f314-119">`remove`Элемент удаляет запись списка управления подключениями для указанного сервера.</span><span class="sxs-lookup"><span data-stu-id="0f314-119">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="0f314-120">Значение `address` атрибута должно быть допустимым IP-адресом или именем узла.</span><span class="sxs-lookup"><span data-stu-id="0f314-120">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0f314-121">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="0f314-121">Configuration Files</span></span>  

 <span data-ttu-id="0f314-122">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0f314-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f314-123">Пример</span><span class="sxs-lookup"><span data-stu-id="0f314-123">Example</span></span>  

 <span data-ttu-id="0f314-124">В следующем примере удаляются все записи списка управления подключениями для сервера `www.adventure-works.com` , а затем настраивается приложение для использования четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="0f314-124">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f314-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0f314-125">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="0f314-126">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="0f314-126">Network Settings Schema</span></span>](index.md)
