---
title: Элемент <remove> для authenticationModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: d171fea193bbae068e69b8976abb8e56a5623f02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154781"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="7c12f-102">Элемент \<remove> для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="7c12f-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="7c12f-103">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="7c12f-103">Removes an authentication module from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="7c12f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c12f-104">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c12f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7c12f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7c12f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7c12f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c12f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7c12f-107">Attributes</span></span>  
  
|<span data-ttu-id="7c12f-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="7c12f-108">**Attribute**</span></span>|<span data-ttu-id="7c12f-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7c12f-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="7c12f-110">**type**</span><span class="sxs-lookup"><span data-stu-id="7c12f-110">**type**</span></span>|<span data-ttu-id="7c12f-111">Имя удаляемого модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7c12f-111">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c12f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7c12f-112">Child Elements</span></span>  
 <span data-ttu-id="7c12f-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7c12f-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c12f-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7c12f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7c12f-115">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="7c12f-115">**Element**</span></span>|<span data-ttu-id="7c12f-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7c12f-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7c12f-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="7c12f-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="7c12f-118">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="7c12f-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c12f-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c12f-119">Remarks</span></span>  
 <span data-ttu-id="7c12f-120">`remove`Элемент удаляет модули проверки подлинности, которые были определены ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7c12f-120">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="7c12f-121">Значение `type` атрибута должно быть допустимым именем класса.</span><span class="sxs-lookup"><span data-stu-id="7c12f-121">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7c12f-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="7c12f-122">Configuration Files</span></span>  
 <span data-ttu-id="7c12f-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7c12f-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c12f-124">Пример</span><span class="sxs-lookup"><span data-stu-id="7c12f-124">Example</span></span>  
 <span data-ttu-id="7c12f-125">В следующем примере удаляется модуль проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7c12f-125">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c12f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7c12f-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="7c12f-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="7c12f-127">Network Settings Schema</span></span>](index.md)
