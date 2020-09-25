---
title: Элемент <clear> для connectionManagement (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
ms.openlocfilehash: 446bec116118ee8b604ef3664a6eb0452e6d5a38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184109"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="5a69e-102">Элемент \<clear> для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="5a69e-102">\<clear> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="5a69e-103">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="5a69e-103">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="5a69e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a69e-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a69e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5a69e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="5a69e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5a69e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a69e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5a69e-107">Attributes</span></span>  

 <span data-ttu-id="5a69e-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5a69e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a69e-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5a69e-109">Child Elements</span></span>  

 <span data-ttu-id="5a69e-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5a69e-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a69e-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5a69e-111">Parent Elements</span></span>  
  
|<span data-ttu-id="5a69e-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="5a69e-112">**Element**</span></span>|<span data-ttu-id="5a69e-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5a69e-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5a69e-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="5a69e-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="5a69e-115">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="5a69e-115">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a69e-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="5a69e-116">Remarks</span></span>  

 <span data-ttu-id="5a69e-117">`clear`Элемент удаляет все записи из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="5a69e-117">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5a69e-118">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="5a69e-118">Configuration Files</span></span>  

 <span data-ttu-id="5a69e-119">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5a69e-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a69e-120">Пример</span><span class="sxs-lookup"><span data-stu-id="5a69e-120">Example</span></span>  

 <span data-ttu-id="5a69e-121">В следующем примере очищается список управления подключениями, а затем добавляются новые записи управления подключениями для сервера `www.contoso.com` и всех остальных сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="5a69e-121">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a69e-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5a69e-122">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="5a69e-123">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="5a69e-123">Network Settings Schema</span></span>](index.md)
