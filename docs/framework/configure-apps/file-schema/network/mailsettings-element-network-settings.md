---
title: Элемент <mailSettings> (параметры сети)
description: <mailSettings>Элемент Параметры сети настраивает параметры отправки почты в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: a146874acc21f52507b37b1751c648792e23c8bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158855"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="a2fba-103">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="a2fba-103">\<mailSettings> Element (Network Settings)</span></span>

<span data-ttu-id="a2fba-104">Настраивает параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="a2fba-104">Configures mail sending options.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a><span data-ttu-id="a2fba-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2fba-105">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2fba-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a2fba-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a2fba-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a2fba-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2fba-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a2fba-108">Attributes</span></span>  

 <span data-ttu-id="a2fba-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a2fba-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2fba-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a2fba-110">Child Elements</span></span>  
  
|<span data-ttu-id="a2fba-111">attribute</span><span class="sxs-lookup"><span data-stu-id="a2fba-111">Attribute</span></span>|<span data-ttu-id="a2fba-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a2fba-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a2fba-113">Элемент \<smtp> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="a2fba-113">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="a2fba-114">Настраивает параметры протокола простого почтового транспорта.</span><span class="sxs-lookup"><span data-stu-id="a2fba-114">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2fba-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a2fba-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a2fba-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="a2fba-116">**Element**</span></span>|<span data-ttu-id="a2fba-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a2fba-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a2fba-118">Элемент \<system.Net> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="a2fba-118">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a2fba-119">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="a2fba-119">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a2fba-120">Пример</span><span class="sxs-lookup"><span data-stu-id="a2fba-120">Example</span></span>  

 <span data-ttu-id="a2fba-121">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a2fba-121">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="a2fba-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a2fba-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="a2fba-123">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="a2fba-123">Network Settings Schema</span></span>](index.md)
