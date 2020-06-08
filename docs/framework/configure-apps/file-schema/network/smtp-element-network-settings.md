---
title: Элемент <smtp> (параметры сети)
description: <smtp>Элемент Параметры сети настраивает формат доставки, метод доставки и адрес отправителя для отправки параметров электронной почты в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: b30b82922a69ea660f4c4abfd808e89fa9945183
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504515"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="4d46a-103">Элемент \<smtp> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="4d46a-103">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="4d46a-104">Настраивает формат доставки, метод доставки и адрес отправителя для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4d46a-104">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="4d46a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d46a-105">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d46a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4d46a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="4d46a-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4d46a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d46a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4d46a-108">Attributes</span></span>  
  
|<span data-ttu-id="4d46a-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4d46a-109">Attribute</span></span>|<span data-ttu-id="4d46a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4d46a-110">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="4d46a-111">Указывает формат доставки исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4d46a-111">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="4d46a-112">Допустимые значения: SevenBit и International.</span><span class="sxs-lookup"><span data-stu-id="4d46a-112">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="4d46a-113">Указывает метод доставки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4d46a-113">Specifies the delivery method for emails.</span></span> <span data-ttu-id="4d46a-114">Допустимые значения: Network, Пиккупдиректорифромиис и СпеЦифиедпиккупдиректори.</span><span class="sxs-lookup"><span data-stu-id="4d46a-114">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="4d46a-115">Указывает адрес отсылаемых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4d46a-115">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d46a-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4d46a-116">Child Elements</span></span>  
  
|<span data-ttu-id="4d46a-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4d46a-117">Attribute</span></span>|<span data-ttu-id="4d46a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="4d46a-118">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="4d46a-119">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="4d46a-119">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="4d46a-120">Настраивает параметры сети для внешнего SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="4d46a-120">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d46a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4d46a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4d46a-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="4d46a-122">**Element**</span></span>|<span data-ttu-id="4d46a-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4d46a-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4d46a-124">\<mailSettings>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="4d46a-124">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="4d46a-125">Настраивает параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="4d46a-125">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4d46a-126">Пример</span><span class="sxs-lookup"><span data-stu-id="4d46a-126">Example</span></span>  
 <span data-ttu-id="4d46a-127">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d46a-127">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d46a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="4d46a-128">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="4d46a-129">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="4d46a-129">Network Settings Schema</span></span>](index.md)
