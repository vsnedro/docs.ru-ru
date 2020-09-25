---
title: Элемент <specifiedPickupDirectory> (параметры сети)
description: <specifiedPickupDirectory>Элемент Параметры сети настраивает локальный каталог для параметров SMTP-сервера в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 5bb7fc5405b1ee2f0f054bc6e9f043a3f9fcd1ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176166"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="f35bc-103">Элемент \<specifiedPickupDirectory> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f35bc-103">\<specifiedPickupDirectory> Element (Network Settings)</span></span>

<span data-ttu-id="f35bc-104">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="f35bc-104">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="f35bc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f35bc-105">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f35bc-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f35bc-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f35bc-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f35bc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f35bc-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f35bc-108">Attributes</span></span>  
  
|<span data-ttu-id="f35bc-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f35bc-109">Attribute</span></span>|<span data-ttu-id="f35bc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f35bc-110">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="f35bc-111">Каталог, в котором приложения сохраняют электронную почту для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="f35bc-111">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f35bc-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f35bc-112">Child Elements</span></span>  

 <span data-ttu-id="f35bc-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f35bc-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f35bc-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f35bc-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f35bc-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f35bc-115">Element</span></span>|<span data-ttu-id="f35bc-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f35bc-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f35bc-117">Элемент \<smtp> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f35bc-117">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="f35bc-118">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="f35bc-118">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f35bc-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="f35bc-119">Remarks</span></span>  

 <span data-ttu-id="f35bc-120">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="f35bc-120">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f35bc-121">Пример</span><span class="sxs-lookup"><span data-stu-id="f35bc-121">Example</span></span>  

 <span data-ttu-id="f35bc-122">В следующем примере в качестве каталога подбора почты указывается к:\маилдроп.</span><span class="sxs-lookup"><span data-stu-id="f35bc-122">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f35bc-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f35bc-123">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="f35bc-124">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f35bc-124">Network Settings Schema</span></span>](index.md)
