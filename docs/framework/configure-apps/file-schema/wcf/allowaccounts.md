---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 3432d33c0cd65af03d2b1ac1302ca2c8ff3e0f43
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201646"
---
# \<allowAccounts>

<span data-ttu-id="5b610-101">Содержит коллекцию элементов конфигурации, указывающих учетные записи пользователей для процессов, на которых размещены службы Windows Communication Foundation (WCF) и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="5b610-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="5b610-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b610-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b610-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5b610-103">Attributes and Elements</span></span>  

 <span data-ttu-id="5b610-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5b610-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b610-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5b610-105">Attributes</span></span>  

 <span data-ttu-id="5b610-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5b610-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b610-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5b610-107">Child Elements</span></span>  
  
|<span data-ttu-id="5b610-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5b610-108">Attribute</span></span>|<span data-ttu-id="5b610-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5b610-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="5b610-110">Добавляет учетную запись пользователя для процессов, на которых размещаются службы WCF, и предоставляет доступ к подключению к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="5b610-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b610-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5b610-111">Parent Elements</span></span>  
  
|<span data-ttu-id="5b610-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="5b610-112">Element</span></span>|<span data-ttu-id="5b610-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5b610-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b610-114">[\<net.pipe>](net-pipe.md) или [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="5b610-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="5b610-115">Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.</span><span class="sxs-lookup"><span data-stu-id="5b610-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b610-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5b610-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
