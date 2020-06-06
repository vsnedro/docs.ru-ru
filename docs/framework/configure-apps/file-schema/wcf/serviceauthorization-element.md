---
title: <serviceAuthorization> - элемент
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834013"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="5bf0d-102">Элемент \<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="5bf0d-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="5bf0d-103">Задает параметры авторизации доступа к операциям службы.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-103">Specifies settings that authorize access to service operations</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**  

## <a name="syntax"></a><span data-ttu-id="5bf0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bf0d-104">Syntax</span></span>

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5bf0d-105">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="5bf0d-105">Attributes and elements</span></span>

<span data-ttu-id="5bf0d-106">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-106">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="5bf0d-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5bf0d-107">Attributes</span></span>

|<span data-ttu-id="5bf0d-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5bf0d-108">Attribute</span></span>|<span data-ttu-id="5bf0d-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="5bf0d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5bf0d-110">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="5bf0d-110">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="5bf0d-111">Логическое значение, которое определяет, должны ли все операции службы олицетворять вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-111">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="5bf0d-112">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-112">The default is `false`.</span></span><br /><br /> <span data-ttu-id="5bf0d-113">Если конкретная операция службы олицетворяет вызывающий объект, контекст потока переключается на контекст вызывающего объекта перед выполнением указанной службы.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-113">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="5bf0d-114">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="5bf0d-114">principalPermissionMode</span></span>|<span data-ttu-id="5bf0d-115">Определяет участников, используемых для выполнения операций на сервере.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-115">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="5bf0d-116">В эти значения входят:</span><span class="sxs-lookup"><span data-stu-id="5bf0d-116">Values include the following:</span></span><br /><br /> <span data-ttu-id="5bf0d-117">— Нет</span><span class="sxs-lookup"><span data-stu-id="5bf0d-117">-   None</span></span><br /><span data-ttu-id="5bf0d-118">-Усевиндовсграупс</span><span class="sxs-lookup"><span data-stu-id="5bf0d-118">-   UseWindowsGroups</span></span><br /><span data-ttu-id="5bf0d-119">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="5bf0d-119">-   UseAspNetRoles</span></span><br /><span data-ttu-id="5bf0d-120">— Пользовательский</span><span class="sxs-lookup"><span data-stu-id="5bf0d-120">-   Custom</span></span><br /><br /> <span data-ttu-id="5bf0d-121">Значение по умолчанию - «UseWindowsGroups».</span><span class="sxs-lookup"><span data-stu-id="5bf0d-121">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="5bf0d-122">Это значение типа <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-122">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="5bf0d-123">Дополнительные сведения об использовании этого атрибута см. в разделе [как ограничить доступ с помощью класса PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="5bf0d-123">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="5bf0d-124">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="5bf0d-124">roleProviderName</span></span>|<span data-ttu-id="5bf0d-125">Строка, указывающая имя поставщика роли, который предоставляет сведения о роли для приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5bf0d-125">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="5bf0d-126">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="5bf0d-127">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="5bf0d-127">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="5bf0d-128">Строка, содержащая имя типа диспетчера авторизации служб.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-128">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="5bf0d-129">Для получения дополнительной информации см. <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-129">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="5bf0d-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5bf0d-130">Child elements</span></span>

|<span data-ttu-id="5bf0d-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="5bf0d-131">Element</span></span>|<span data-ttu-id="5bf0d-132">Описание</span><span class="sxs-lookup"><span data-stu-id="5bf0d-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5bf0d-133">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="5bf0d-133">authorizationPolicies</span></span>|<span data-ttu-id="5bf0d-134">Содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова`add`.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-134">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="5bf0d-135">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-135">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="5bf0d-136">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-136">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="5bf0d-137">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-137">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="5bf0d-138">Для получения дополнительной информации см. <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-138">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="5bf0d-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5bf0d-139">Parent elements</span></span>

|<span data-ttu-id="5bf0d-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="5bf0d-140">Element</span></span>|<span data-ttu-id="5bf0d-141">Описание</span><span class="sxs-lookup"><span data-stu-id="5bf0d-141">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5bf0d-142">Содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-142">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="5bf0d-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="5bf0d-143">Remarks</span></span>

<span data-ttu-id="5bf0d-144">Этот раздел содержит элементы, влияющие на авторизацию, поставщики пользовательских ролей и олицетворение.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-144">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="5bf0d-145">Атрибут `principalPermissionMode` указывает группы пользователей, которые следует использовать при авторизации использования защищенного метода.</span><span class="sxs-lookup"><span data-stu-id="5bf0d-145">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="5bf0d-146">Значение по умолчанию - `UseWindowsGroups`. Оно указывает, что при попытке доступа к ресурсу поиск удостоверения выполняется в таких группах Windows, как «Администраторы» или «Пользователи».</span><span class="sxs-lookup"><span data-stu-id="5bf0d-146">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="5bf0d-147">Можно также указать, `UseAspNetRoles` чтобы использовать пользовательский поставщик ролей, настроенный под \<system.web> элементом, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="5bf0d-147">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
<span data-ttu-id="5bf0d-148">В следующем коде показан объект, `roleProviderName` используемый с `principalPermissionMode` атрибутом:</span><span class="sxs-lookup"><span data-stu-id="5bf0d-148">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="5bf0d-149">Подробный пример использования этого элемента конфигурации см. в разделе [авторизация доступа к операциям службы](../../../wcf/samples/authorizing-access-to-service-operations.md) и [политикам авторизации](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="5bf0d-149">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5bf0d-150">См. также</span><span class="sxs-lookup"><span data-stu-id="5bf0d-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="5bf0d-151">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="5bf0d-151">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5bf0d-152">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="5bf0d-152">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="5bf0d-153">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="5bf0d-153">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="5bf0d-154">Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="5bf0d-154">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="5bf0d-155">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="5bf0d-155">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
