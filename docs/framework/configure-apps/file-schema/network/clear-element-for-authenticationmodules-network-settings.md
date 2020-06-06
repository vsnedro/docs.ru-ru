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
ms.openlocfilehash: e3abd1b4c76ebda885703ccf961d58657b582f19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087514"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="3104b-102">Элемент \<clear> для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="3104b-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="3104b-103">Удаляет из приложения все модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3104b-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="3104b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3104b-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3104b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3104b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3104b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3104b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3104b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3104b-107">Attributes</span></span>  
 <span data-ttu-id="3104b-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3104b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3104b-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3104b-109">Child Elements</span></span>  
 <span data-ttu-id="3104b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="3104b-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3104b-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3104b-111">Parent Elements</span></span>  
  
|<span data-ttu-id="3104b-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="3104b-112">**Element**</span></span>|<span data-ttu-id="3104b-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3104b-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3104b-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="3104b-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="3104b-115">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="3104b-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3104b-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="3104b-116">Remarks</span></span>  
 <span data-ttu-id="3104b-117">`clear`Элемент удаляет все модули проверки подлинности, определенные ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3104b-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3104b-118">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="3104b-118">Configuration Files</span></span>  
 <span data-ttu-id="3104b-119">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3104b-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3104b-120">Пример</span><span class="sxs-lookup"><span data-stu-id="3104b-120">Example</span></span>  
 <span data-ttu-id="3104b-121">В следующем примере удаляются все настроенные модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3104b-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3104b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3104b-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="3104b-123">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3104b-123">Network Settings Schema</span></span>](index.md)
