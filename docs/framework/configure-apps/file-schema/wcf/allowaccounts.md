---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398407"
---
# \<allowAccounts>
<span data-ttu-id="8e118-101">Содержит коллекцию элементов конфигурации, указывающих учетные записи пользователей для процессов, на которых размещены службы Windows Communication Foundation (WCF) и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="8e118-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="8e118-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e118-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e118-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e118-103">Attributes and Elements</span></span>  
 <span data-ttu-id="8e118-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8e118-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e118-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e118-105">Attributes</span></span>  
 <span data-ttu-id="8e118-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8e118-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8e118-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e118-107">Child Elements</span></span>  
  
|<span data-ttu-id="8e118-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8e118-108">Attribute</span></span>|<span data-ttu-id="8e118-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="8e118-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="8e118-110">Добавляет учетную запись пользователя для процессов, на которых размещаются службы WCF, и предоставляет доступ к подключению к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="8e118-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e118-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e118-111">Parent Elements</span></span>  
  
|<span data-ttu-id="8e118-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e118-112">Element</span></span>|<span data-ttu-id="8e118-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8e118-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e118-114">[\<net.pipe>](net-pipe.md)ни[\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="8e118-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="8e118-115">Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.</span><span class="sxs-lookup"><span data-stu-id="8e118-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e118-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8e118-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
