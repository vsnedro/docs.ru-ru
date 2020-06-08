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
ms.openlocfilehash: f0c4c1845e9542d0f3b836ff03f16bdf2979ebd8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504502"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="13547-103">Элемент \<specifiedPickupDirectory> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="13547-103">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="13547-104">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="13547-104">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="13547-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13547-105">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13547-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13547-106">Attributes and Elements</span></span>  
 <span data-ttu-id="13547-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="13547-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13547-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13547-108">Attributes</span></span>  
  
|<span data-ttu-id="13547-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="13547-109">Attribute</span></span>|<span data-ttu-id="13547-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="13547-110">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="13547-111">Каталог, в котором приложения сохраняют электронную почту для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="13547-111">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13547-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13547-112">Child Elements</span></span>  
 <span data-ttu-id="13547-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="13547-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13547-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13547-114">Parent Elements</span></span>  
  
|<span data-ttu-id="13547-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="13547-115">Element</span></span>|<span data-ttu-id="13547-116">Описание</span><span class="sxs-lookup"><span data-stu-id="13547-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13547-117">\<smtp>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="13547-117">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="13547-118">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="13547-118">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13547-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="13547-119">Remarks</span></span>  
 <span data-ttu-id="13547-120">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="13547-120">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13547-121">Пример</span><span class="sxs-lookup"><span data-stu-id="13547-121">Example</span></span>  
 <span data-ttu-id="13547-122">В следующем примере в качестве каталога подбора почты указывается к:\маилдроп.</span><span class="sxs-lookup"><span data-stu-id="13547-122">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="13547-123">См. также</span><span class="sxs-lookup"><span data-stu-id="13547-123">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="13547-124">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="13547-124">Network Settings Schema</span></span>](index.md)
