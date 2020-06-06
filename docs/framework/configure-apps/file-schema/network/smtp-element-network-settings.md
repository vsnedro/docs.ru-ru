---
title: Элемент <smtp> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 625c3cb82a8659c742b540724e5cf31be65a705e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089102"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="29a03-102">Элемент \<smtp> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="29a03-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="29a03-103">Настраивает формат доставки, метод доставки и адрес отправителя для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="29a03-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="29a03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29a03-104">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29a03-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29a03-105">Attributes and Elements</span></span>  
 <span data-ttu-id="29a03-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="29a03-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29a03-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29a03-107">Attributes</span></span>  
  
|<span data-ttu-id="29a03-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="29a03-108">Attribute</span></span>|<span data-ttu-id="29a03-109">Описание</span><span class="sxs-lookup"><span data-stu-id="29a03-109">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="29a03-110">Указывает формат доставки исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="29a03-110">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="29a03-111">Допустимые значения: SevenBit и International.</span><span class="sxs-lookup"><span data-stu-id="29a03-111">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="29a03-112">Указывает метод доставки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="29a03-112">Specifies the delivery method for emails.</span></span> <span data-ttu-id="29a03-113">Допустимые значения: Network, Пиккупдиректорифромиис и СпеЦифиедпиккупдиректори.</span><span class="sxs-lookup"><span data-stu-id="29a03-113">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="29a03-114">Указывает адрес отсылаемых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="29a03-114">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29a03-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29a03-115">Child Elements</span></span>  
  
|<span data-ttu-id="29a03-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="29a03-116">Attribute</span></span>|<span data-ttu-id="29a03-117">Описание</span><span class="sxs-lookup"><span data-stu-id="29a03-117">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="29a03-118">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="29a03-118">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="29a03-119">Настраивает параметры сети для внешнего SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="29a03-119">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29a03-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29a03-120">Parent Elements</span></span>  
  
|<span data-ttu-id="29a03-121">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="29a03-121">**Element**</span></span>|<span data-ttu-id="29a03-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="29a03-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="29a03-123">\<mailSettings>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="29a03-123">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="29a03-124">Настраивает параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="29a03-124">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="29a03-125">Пример</span><span class="sxs-lookup"><span data-stu-id="29a03-125">Example</span></span>  
 <span data-ttu-id="29a03-126">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="29a03-126">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29a03-127">См. также</span><span class="sxs-lookup"><span data-stu-id="29a03-127">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="29a03-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="29a03-128">Network Settings Schema</span></span>](index.md)
