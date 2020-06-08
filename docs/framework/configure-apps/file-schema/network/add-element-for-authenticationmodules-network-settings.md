---
title: Элемент <add> для authenticationModules (параметры сети)
description: <add>Элемент Network Settings для элемент connectionManagement добавляет IP-адрес или имя DNS в список управления подключениями в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: 1a6d0f79f076a69cec33ac14f0e0f33f7c3c6577
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504645"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="d24a4-103">Элемент \<add> для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="d24a4-103">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="d24a4-104">Добавляет модуль проверки подлинности в приложение.</span><span class="sxs-lookup"><span data-stu-id="d24a4-104">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="d24a4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d24a4-105">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d24a4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d24a4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d24a4-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d24a4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d24a4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d24a4-108">Attributes</span></span>  
  
|<span data-ttu-id="d24a4-109">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="d24a4-109">**Attribute**</span></span>|<span data-ttu-id="d24a4-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d24a4-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="d24a4-111">Полное имя типа (обозначенное <xref:System.Type.FullName%2A> свойством) и имя сборки (указывается <xref:System.Reflection.Assembly.FullName%2A> свойством), разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="d24a4-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d24a4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d24a4-112">Child Elements</span></span>  
 <span data-ttu-id="d24a4-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d24a4-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d24a4-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d24a4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d24a4-115">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="d24a4-115">**Element**</span></span>|<span data-ttu-id="d24a4-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d24a4-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d24a4-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="d24a4-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="d24a4-118">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="d24a4-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d24a4-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="d24a4-119">Remarks</span></span>  
 <span data-ttu-id="d24a4-120">Элемент `add` добавляет модуль проверки подлинности в конец списка зарегистрированных модулей проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d24a4-120">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="d24a4-121">Модули проверки подлинности вызываются в том порядке, в котором они были добавлены в список.</span><span class="sxs-lookup"><span data-stu-id="d24a4-121">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="d24a4-122">Значением `type` атрибута должно быть допустимое имя типа и соответствующее имя сборки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="d24a4-122">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d24a4-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="d24a4-123">Configuration Files</span></span>  
 <span data-ttu-id="d24a4-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d24a4-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d24a4-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d24a4-125">Example</span></span>  
 <span data-ttu-id="d24a4-126">В следующем примере включаются модули проверки подлинности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d24a4-126">The following example enables the default authentication modules.</span></span> <span data-ttu-id="d24a4-127">Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="d24a4-127">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d24a4-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d24a4-128">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="d24a4-129">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="d24a4-129">Network Settings Schema</span></span>](index.md)
