---
title: <add> из <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398379"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="bad34-102">\<add> из \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="bad34-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="bad34-103">Указывает учетную запись пользователя для процессов, на которых размещаются службы WCF, и им предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="bad34-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="bad34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bad34-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bad34-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bad34-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bad34-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bad34-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bad34-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bad34-107">Attributes</span></span>  
  
|<span data-ttu-id="bad34-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bad34-108">Attribute</span></span>|<span data-ttu-id="bad34-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="bad34-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bad34-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="bad34-110">securityIdentifier</span></span>|<span data-ttu-id="bad34-111">Строка, задающая уникальный идентификатор, который используется для идентификации учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="bad34-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="bad34-112">Значениями по умолчанию являются LocalSystem, Administrators, NS, LS и IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="bad34-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bad34-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bad34-113">Child Elements</span></span>  
 <span data-ttu-id="bad34-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bad34-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bad34-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bad34-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bad34-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="bad34-116">Element</span></span>|<span data-ttu-id="bad34-117">Описание</span><span class="sxs-lookup"><span data-stu-id="bad34-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="bad34-118">Коллекция элементов конфигурации, которая содержит `securityIdentifier` атрибут для указания учетных записей пользователей для процессов, размещающий службы WCF, и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="bad34-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bad34-119">Пример</span><span class="sxs-lookup"><span data-stu-id="bad34-119">Example</span></span>  
 <span data-ttu-id="bad34-120">В следующем примере конфигурации к данной коллекции добавляется пять идентификаторов по умолчанию для учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="bad34-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="bad34-121">См. также</span><span class="sxs-lookup"><span data-stu-id="bad34-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
