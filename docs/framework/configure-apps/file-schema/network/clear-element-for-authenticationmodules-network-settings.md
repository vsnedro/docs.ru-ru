---
title: Элемент <clear> для authenticationModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: 6ac2287ba9b17727835d43a3e3b8876f210fb5c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167331"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="3f885-102">Элемент \<clear> для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="3f885-102">\<clear> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="3f885-103">Удаляет из приложения все модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3f885-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="3f885-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f885-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f885-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3f885-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3f885-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3f885-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f885-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3f885-107">Attributes</span></span>  

 <span data-ttu-id="3f885-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3f885-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3f885-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3f885-109">Child Elements</span></span>  

 <span data-ttu-id="3f885-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3f885-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f885-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3f885-111">Parent Elements</span></span>  
  
|<span data-ttu-id="3f885-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="3f885-112">**Element**</span></span>|<span data-ttu-id="3f885-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3f885-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3f885-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="3f885-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="3f885-115">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="3f885-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f885-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="3f885-116">Remarks</span></span>  

 <span data-ttu-id="3f885-117">`clear`Элемент удаляет все модули проверки подлинности, определенные ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3f885-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3f885-118">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="3f885-118">Configuration Files</span></span>  

 <span data-ttu-id="3f885-119">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3f885-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f885-120">Пример</span><span class="sxs-lookup"><span data-stu-id="3f885-120">Example</span></span>  

 <span data-ttu-id="3f885-121">В следующем примере удаляются все настроенные модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3f885-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f885-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3f885-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="3f885-123">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3f885-123">Network Settings Schema</span></span>](index.md)
