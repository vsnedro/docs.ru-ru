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
ms.openlocfilehash: 58f496b4a07f7d5531df897dd54bb6176111f1c4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178324"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="ccad3-103">Элемент \<smtp> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ccad3-103">\<smtp> Element (Network Settings)</span></span>

<span data-ttu-id="ccad3-104">Настраивает формат доставки, метод доставки и адрес отправителя для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ccad3-104">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="ccad3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccad3-105">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccad3-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ccad3-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ccad3-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ccad3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccad3-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ccad3-108">Attributes</span></span>  
  
|<span data-ttu-id="ccad3-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ccad3-109">Attribute</span></span>|<span data-ttu-id="ccad3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ccad3-110">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="ccad3-111">Указывает формат доставки исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ccad3-111">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="ccad3-112">Допустимые значения: SevenBit и International.</span><span class="sxs-lookup"><span data-stu-id="ccad3-112">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="ccad3-113">Указывает метод доставки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ccad3-113">Specifies the delivery method for emails.</span></span> <span data-ttu-id="ccad3-114">Допустимые значения: Network, Пиккупдиректорифромиис и СпеЦифиедпиккупдиректори.</span><span class="sxs-lookup"><span data-stu-id="ccad3-114">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="ccad3-115">Указывает адрес отсылаемых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ccad3-115">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccad3-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ccad3-116">Child Elements</span></span>  
  
|<span data-ttu-id="ccad3-117">attribute</span><span class="sxs-lookup"><span data-stu-id="ccad3-117">Attribute</span></span>|<span data-ttu-id="ccad3-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ccad3-118">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="ccad3-119">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="ccad3-119">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="ccad3-120">Настраивает параметры сети для внешнего SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="ccad3-120">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ccad3-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ccad3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ccad3-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ccad3-122">**Element**</span></span>|<span data-ttu-id="ccad3-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ccad3-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ccad3-124">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ccad3-124">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="ccad3-125">Настраивает параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="ccad3-125">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ccad3-126">Пример</span><span class="sxs-lookup"><span data-stu-id="ccad3-126">Example</span></span>  

 <span data-ttu-id="ccad3-127">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ccad3-127">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ccad3-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ccad3-128">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="ccad3-129">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ccad3-129">Network Settings Schema</span></span>](index.md)
