---
title: Элемент <authenticationModules> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: b502cc4a0958f074018d4b0ce6b3fb118b811c2f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154976"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="8245b-102">Элемент \<authenticationModules> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="8245b-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="8245b-103">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="8245b-103">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="8245b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8245b-104">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8245b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8245b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8245b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8245b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8245b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8245b-107">Attributes</span></span>  
 <span data-ttu-id="8245b-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8245b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8245b-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8245b-109">Child Elements</span></span>  
  
|<span data-ttu-id="8245b-110">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8245b-110">**Element**</span></span>|<span data-ttu-id="8245b-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8245b-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8245b-112">добавление</span><span class="sxs-lookup"><span data-stu-id="8245b-112">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="8245b-113">Добавляет модуль проверки подлинности в приложение.</span><span class="sxs-lookup"><span data-stu-id="8245b-113">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="8245b-114">открытым</span><span class="sxs-lookup"><span data-stu-id="8245b-114">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="8245b-115">Удаляет из приложения все модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8245b-115">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="8245b-116">remove</span><span class="sxs-lookup"><span data-stu-id="8245b-116">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="8245b-117">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="8245b-117">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8245b-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8245b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8245b-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8245b-119">**Element**</span></span>|<span data-ttu-id="8245b-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8245b-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8245b-121">system.net</span><span class="sxs-lookup"><span data-stu-id="8245b-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="8245b-122">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="8245b-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8245b-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="8245b-123">Remarks</span></span>  
 <span data-ttu-id="8245b-124">`authenticationModule`Элемент указывает модули проверки подлинности, которые выполняют процесс проверки подлинности с сервером.</span><span class="sxs-lookup"><span data-stu-id="8245b-124">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="8245b-125">Модуль проверки подлинности должен реализовывать <xref:System.Net.IAuthenticationModule> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8245b-125">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8245b-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="8245b-126">Configuration Files</span></span>  
 <span data-ttu-id="8245b-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8245b-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8245b-128">Пример</span><span class="sxs-lookup"><span data-stu-id="8245b-128">Example</span></span>  
 <span data-ttu-id="8245b-129">В следующем примере включается модуль проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8245b-129">The following example enables an authentication module.</span></span> <span data-ttu-id="8245b-130">Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="8245b-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8245b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8245b-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="8245b-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="8245b-132">Network Settings Schema</span></span>](index.md)
