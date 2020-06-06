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
ms.openlocfilehash: a76df48a9de084e1121a5e96b22edf7aa3acba23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088483"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="7550a-102">Элемент \<clear> для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="7550a-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="7550a-103">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="7550a-103">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="7550a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7550a-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7550a-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7550a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7550a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7550a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7550a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7550a-107">Attributes</span></span>  
 <span data-ttu-id="7550a-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7550a-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7550a-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7550a-109">Child Elements</span></span>  
 <span data-ttu-id="7550a-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="7550a-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7550a-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7550a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="7550a-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="7550a-112">**Element**</span></span>|<span data-ttu-id="7550a-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7550a-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7550a-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="7550a-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="7550a-115">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="7550a-115">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7550a-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="7550a-116">Remarks</span></span>  
 <span data-ttu-id="7550a-117">`clear`Элемент удаляет все записи из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="7550a-117">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7550a-118">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="7550a-118">Configuration Files</span></span>  
 <span data-ttu-id="7550a-119">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7550a-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7550a-120">Пример</span><span class="sxs-lookup"><span data-stu-id="7550a-120">Example</span></span>  
 <span data-ttu-id="7550a-121">В следующем примере очищается список управления подключениями, а затем добавляются новые записи управления подключениями для сервера `www.contoso.com` и всех остальных сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="7550a-121">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7550a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7550a-122">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="7550a-123">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="7550a-123">Network Settings Schema</span></span>](index.md)
