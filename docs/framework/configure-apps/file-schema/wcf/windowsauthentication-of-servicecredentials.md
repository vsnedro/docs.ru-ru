---
title: <windowsAuthentication> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: bda375959b535ce5f2996d594f719893164b0bd4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195003"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="9c79b-102">\<windowsAuthentication> из \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9c79b-102">\<windowsAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="9c79b-103">Задает параметры учетной записи службы Windows.</span><span class="sxs-lookup"><span data-stu-id="9c79b-103">Specifies the settings of a Windows service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="9c79b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c79b-104">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c79b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9c79b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9c79b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9c79b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c79b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9c79b-107">Attributes</span></span>  
  
|<span data-ttu-id="9c79b-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9c79b-108">Attribute</span></span>|<span data-ttu-id="9c79b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9c79b-109">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="9c79b-110">Необязательный логический атрибут, который задает, включает ли система группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="9c79b-110">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="9c79b-111">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="9c79b-111">The default is `true`.</span></span><br /><br /> <span data-ttu-id="9c79b-112">Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="9c79b-112">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="9c79b-113">Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9c79b-113">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="9c79b-114">Необязательный логический атрибут, который указывает, разрешены ли анонимные, не прошедшие проверку подлинности вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="9c79b-114">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="9c79b-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="9c79b-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9c79b-116">Когда атрибуту `clientCredentialType` привязки задано значение `Windows`, система не разрешает анонимные вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="9c79b-116">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="9c79b-117">Это значит, что доступ к системе разрешен только прошедшим проверку подлинности вызывающим объектам домена или рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="9c79b-117">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="9c79b-118">Это поведение можно переопределить с помощью данного атрибута.</span><span class="sxs-lookup"><span data-stu-id="9c79b-118">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="9c79b-119">Используйте этот режим с особой осторожностью.</span><span class="sxs-lookup"><span data-stu-id="9c79b-119">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c79b-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9c79b-120">Child Elements</span></span>  

 <span data-ttu-id="9c79b-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9c79b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c79b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9c79b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9c79b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="9c79b-123">Element</span></span>|<span data-ttu-id="9c79b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="9c79b-124">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="9c79b-125">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="9c79b-125">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c79b-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c79b-126">Remarks</span></span>  

 <span data-ttu-id="9c79b-127">Этот элемент используется, чтобы указать, разрешается ли доступ анонимных пользователей Windows путем установки атрибута `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="9c79b-127">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="9c79b-128">Также можно указать, включать ли сведения о группе, к которой принадлежат пользователи в AuthorizationContext, путем установки атрибута `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="9c79b-128">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="9c79b-129">Если атрибуту задано значение `true` (по умолчанию), служба может определить группы Windows, к которым принадлежит клиент.</span><span class="sxs-lookup"><span data-stu-id="9c79b-129">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c79b-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9c79b-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
