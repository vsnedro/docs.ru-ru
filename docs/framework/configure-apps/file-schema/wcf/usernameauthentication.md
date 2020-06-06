---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: dc5c00a2204646863ae2570bb97b8d70e22a72d4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399190"
---
# \<userNameAuthentication>
<span data-ttu-id="d1b04-101">Задает учетные данные службы, основанные на имени пользователя и пароле.</span><span class="sxs-lookup"><span data-stu-id="d1b04-101">Specifies a service's credentials based on user name and password.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="d1b04-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1b04-102">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1b04-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d1b04-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d1b04-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d1b04-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1b04-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1b04-105">Attributes</span></span>  
  
|<span data-ttu-id="d1b04-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d1b04-106">Attribute</span></span>|<span data-ttu-id="d1b04-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="d1b04-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="d1b04-108">Объект <xref:System.TimeSpan>, определяющий максимальный срок кэширования маркера.</span><span class="sxs-lookup"><span data-stu-id="d1b04-108">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="d1b04-109">Значение по умолчанию - 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="d1b04-109">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="d1b04-110">Логическое значение, которое указывает, кэшируются ли маркеры входа.</span><span class="sxs-lookup"><span data-stu-id="d1b04-110">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="d1b04-111">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="d1b04-111">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="d1b04-112">Строка, указывающая тип настраиваемого проверяющего элемента управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="d1b04-112">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="d1b04-113">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="d1b04-113">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="d1b04-114">Логическое значение, указывающее, включаются ли группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="d1b04-114">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="d1b04-115">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="d1b04-115">The default is `true`.</span></span><br /><br /> <span data-ttu-id="d1b04-116">Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="d1b04-116">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="d1b04-117">Если нет необходимости устанавливать список групп, которым принадлежит пользователь, установите значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d1b04-117">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="d1b04-118">Целое число, указывающее максимальное количество маркеров входа для кэширования.</span><span class="sxs-lookup"><span data-stu-id="d1b04-118">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="d1b04-119">Значение должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="d1b04-119">This value should be larger than zero.</span></span> <span data-ttu-id="d1b04-120">Значение по умолчанию — 128.</span><span class="sxs-lookup"><span data-stu-id="d1b04-120">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="d1b04-121">Если атрибуту `clientCredentialType` привязки задано значение `username`, имя пользователя сопоставляется с учетными записями Windows.</span><span class="sxs-lookup"><span data-stu-id="d1b04-121">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="d1b04-122">Такое поведение можно переопределить с помощью этого атрибута, который является строкой, содержащей имя значения <xref:System.Web.Security.MembershipProvider>, предоставляющего соответствующий механизм проверки пароля.</span><span class="sxs-lookup"><span data-stu-id="d1b04-122">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="d1b04-123">Указывает способ проверки пароля.</span><span class="sxs-lookup"><span data-stu-id="d1b04-123">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="d1b04-124">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="d1b04-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="d1b04-125">— Windows</span><span class="sxs-lookup"><span data-stu-id="d1b04-125">-   Windows</span></span><br /><span data-ttu-id="d1b04-126">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="d1b04-126">-   MembershipProvider</span></span><br /><span data-ttu-id="d1b04-127">— Пользовательский</span><span class="sxs-lookup"><span data-stu-id="d1b04-127">-   Custom</span></span><br /><br /> <span data-ttu-id="d1b04-128">По умолчанию используется Windows.</span><span class="sxs-lookup"><span data-stu-id="d1b04-128">The default is Windows.</span></span> <span data-ttu-id="d1b04-129">Это атрибут типа <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="d1b04-129">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1b04-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d1b04-130">Child Elements</span></span>  
 <span data-ttu-id="d1b04-131">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d1b04-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1b04-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d1b04-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d1b04-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1b04-133">Element</span></span>|<span data-ttu-id="d1b04-134">Описание</span><span class="sxs-lookup"><span data-stu-id="d1b04-134">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="d1b04-135">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="d1b04-135">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1b04-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1b04-136">Remarks</span></span>  
 <span data-ttu-id="d1b04-137">Если ни одна из используемых службой привязок не настроена для проверки подлинности на основании имени пользователя и пароля, атрибуты этого элемента пропускаются.</span><span class="sxs-lookup"><span data-stu-id="d1b04-137">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="d1b04-138">К ним относятся `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` и `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="d1b04-138">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="d1b04-139">Если ни одна из используемых службой привязок не настроена на использование проверки подлинности Windows для имени и пароля пользователя, параметры, относящиеся к кэшированию маркеров входа, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="d1b04-139">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="d1b04-140">К ним относятся `cacheLogonTokenLifetime`, `cacheLogonTokens` и `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="d1b04-140">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b04-141">См. также</span><span class="sxs-lookup"><span data-stu-id="d1b04-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
