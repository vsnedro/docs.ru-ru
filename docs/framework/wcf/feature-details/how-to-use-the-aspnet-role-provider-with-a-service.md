---
title: Практическое руководство. Использование поставщика ролей ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 45eeda046e877b4379d7d0e5edd90fac305f5e44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595301"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="9bb71-102">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="9bb71-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="9bb71-103">Поставщик ролей ASP.NET (в сочетании с поставщиком членства ASP.NET) — это функция, позволяющая разработчикам ASP.NET создавать веб-сайты, позволяющие пользователям создавать учетную запись с сайтом и назначать роли для авторизации.</span><span class="sxs-lookup"><span data-stu-id="9bb71-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="9bb71-104">Эта возможность позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам.</span><span class="sxs-lookup"><span data-stu-id="9bb71-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="9bb71-105">В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="9bb71-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="9bb71-106">Вместо этого любой пользователь, предоставляющий свои учетные данные (сочетание имени пользователя и пароля), может использовать сайт и его службы.</span><span class="sxs-lookup"><span data-stu-id="9bb71-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="9bb71-107">Пример приложения см. в разделе [поставщик членства и роли](../samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="9bb71-107">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="9bb71-108">Дополнительные сведения о функции поставщика членства в ASP.NET см. в разделе [как использовать поставщик членства ASP.NET](how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="9bb71-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="9bb71-109">Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях.</span><span class="sxs-lookup"><span data-stu-id="9bb71-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="9bb71-110">Разработчики Windows Communication Foundation (WCF) могут воспользоваться преимуществами этих функций в целях обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="9bb71-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="9bb71-111">При интеграции в приложение WCF пользователи должны указать сочетание имени пользователя и пароля для клиентского приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="9bb71-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="9bb71-112">Чтобы позволить WCF использовать базу данных, необходимо создать экземпляр <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> класса, установить его <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> свойство в значение <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> и добавить экземпляр в коллекцию поведений в <xref:System.ServiceModel.ServiceHost> , где размещена служба.</span><span class="sxs-lookup"><span data-stu-id="9bb71-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="9bb71-113">Настройка поставщика ролей</span><span class="sxs-lookup"><span data-stu-id="9bb71-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="9bb71-114">В файле Web. config в `system.web` элементе < > добавьте `roleManager` элемент < > и присвойте его `enabled` атрибуту значение `true` .</span><span class="sxs-lookup"><span data-stu-id="9bb71-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="9bb71-115">Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="9bb71-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="9bb71-116">В качестве дочернего `roleManager` элемента <> добавьте `providers` элемент <>.</span><span class="sxs-lookup"><span data-stu-id="9bb71-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="9bb71-117">В качестве дочернего `providers` элемента <> добавьте `add` элемент <> со следующими атрибутами, для которых заданы соответствующие значения: `name` , `type` , `connectionStringName` и `applicationName` , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9bb71-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="9bb71-118">Настройка службы для использования поставщика ролей</span><span class="sxs-lookup"><span data-stu-id="9bb71-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="9bb71-119">В файле Web. config добавьте [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="9bb71-119">In the Web.config file, add a [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="9bb71-120">Добавьте [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) элемент в `system.ServiceModel` элемент> <.</span><span class="sxs-lookup"><span data-stu-id="9bb71-120">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="9bb71-121">Добавьте в [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) `behaviors` элемент> <.</span><span class="sxs-lookup"><span data-stu-id="9bb71-121">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="9bb71-122">Добавьте [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемент и присвойте `name` атрибуту соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="9bb71-122">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="9bb71-123">Добавьте в [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) `behavior` элемент> <.</span><span class="sxs-lookup"><span data-stu-id="9bb71-123">Add a [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="9bb71-124">Задайте для атрибута `principalPermissionMode` значение `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="9bb71-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="9bb71-125">Задайте для атрибута `roleProviderName` значение `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="9bb71-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="9bb71-126">В следующем примере показан фрагмент файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9bb71-126">The following example shows a fragment of the configuration.</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9bb71-127">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="9bb71-127">See also</span></span>

- [<span data-ttu-id="9bb71-128">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="9bb71-128">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
- [<span data-ttu-id="9bb71-129">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9bb71-129">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
