---
title: Элемент <specifiedPickupDirectory> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 4b0cbaf9a7bfe2a9b1610811f4201253d219a6b2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154612"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="8fa30-102">Элемент \<specifiedPickupDirectory> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="8fa30-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="8fa30-103">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="8fa30-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="8fa30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fa30-104">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fa30-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8fa30-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8fa30-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8fa30-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fa30-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8fa30-107">Attributes</span></span>  
  
|<span data-ttu-id="8fa30-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8fa30-108">Attribute</span></span>|<span data-ttu-id="8fa30-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="8fa30-109">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="8fa30-110">Каталог, в котором приложения сохраняют электронную почту для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="8fa30-110">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fa30-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8fa30-111">Child Elements</span></span>  
 <span data-ttu-id="8fa30-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8fa30-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fa30-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8fa30-113">Parent Elements</span></span>  
  
|<span data-ttu-id="8fa30-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8fa30-114">Element</span></span>|<span data-ttu-id="8fa30-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8fa30-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fa30-116">\<smtp>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="8fa30-116">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="8fa30-117">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="8fa30-117">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fa30-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="8fa30-118">Remarks</span></span>  
 <span data-ttu-id="8fa30-119">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="8fa30-119">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fa30-120">Пример</span><span class="sxs-lookup"><span data-stu-id="8fa30-120">Example</span></span>  
 <span data-ttu-id="8fa30-121">В следующем примере в качестве каталога подбора почты указывается к:\маилдроп.</span><span class="sxs-lookup"><span data-stu-id="8fa30-121">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8fa30-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8fa30-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="8fa30-123">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="8fa30-123">Network Settings Schema</span></span>](index.md)
