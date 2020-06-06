---
title: Элемент <connectionManagement> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 9f1e382bbbaad2cb95e2c33bbbdfb4c505378c9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154898"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="5ea4b-102">Элемент \<connectionManagement> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="5ea4b-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="5ea4b-103">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-103">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="5ea4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ea4b-104">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ea4b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5ea4b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5ea4b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ea4b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ea4b-107">Attributes</span></span>  
 <span data-ttu-id="5ea4b-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5ea4b-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5ea4b-109">Child Elements</span></span>  
  
|<span data-ttu-id="5ea4b-110">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="5ea4b-110">**Element**</span></span>|<span data-ttu-id="5ea4b-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5ea4b-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5ea4b-112">добавление</span><span class="sxs-lookup"><span data-stu-id="5ea4b-112">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="5ea4b-113">Добавляет IP-адрес или DNS-имя в список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-113">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="5ea4b-114">открытым</span><span class="sxs-lookup"><span data-stu-id="5ea4b-114">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="5ea4b-115">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-115">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="5ea4b-116">remove</span><span class="sxs-lookup"><span data-stu-id="5ea4b-116">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="5ea4b-117">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-117">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ea4b-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5ea4b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5ea4b-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="5ea4b-119">**Element**</span></span>|<span data-ttu-id="5ea4b-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5ea4b-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5ea4b-121">system.net</span><span class="sxs-lookup"><span data-stu-id="5ea4b-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="5ea4b-122">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ea4b-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ea4b-123">Remarks</span></span>  
 <span data-ttu-id="5ea4b-124">`connectionManagement`Элемент определяет максимальное число подключений к серверу или группе серверов.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-124">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5ea4b-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="5ea4b-125">Configuration Files</span></span>  
 <span data-ttu-id="5ea4b-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5ea4b-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ea4b-127">Пример</span><span class="sxs-lookup"><span data-stu-id="5ea4b-127">Example</span></span>  
 <span data-ttu-id="5ea4b-128">В следующем примере приложение настраивается для использования четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="5ea4b-128">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ea4b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="5ea4b-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="5ea4b-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="5ea4b-130">Network Settings Schema</span></span>](index.md)
