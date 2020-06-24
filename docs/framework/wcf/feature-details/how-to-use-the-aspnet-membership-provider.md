---
title: Практическое руководство. Использование поставщика членства ASP.NET
description: Узнайте, как поставщик членства ASP.NET поддерживает веб-сайты, позволяющие пользователям создавать имя пользователя и пароль для доступа без учетной записи домена Windows.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 6d527993dcf1fc5d5cd39bf22c3e772baf60e62f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246731"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="a81a2-103">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a81a2-103">How to: Use the ASP.NET Membership Provider</span></span>

<span data-ttu-id="a81a2-104">Поставщик членства ASP.NET — это функция, позволяющая разработчикам ASP.NET создавать веб-сайты, позволяющие пользователям создавать уникальные сочетания имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="a81a2-104">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="a81a2-105">Эта функция позволяет любому пользователю создавать на узле учетную запись и при входе получать монопольный доступ к узлу и его службам.</span><span class="sxs-lookup"><span data-stu-id="a81a2-105">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="a81a2-106">В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="a81a2-106">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="a81a2-107">Вместо этого любой пользователь, предоставляющий свои учетные данные (сочетание имени пользователя и пароля), может использовать сайт и его службы.</span><span class="sxs-lookup"><span data-stu-id="a81a2-107">Instead, any user that supplies their credentials (the user name/password combination) can use the site and its services.</span></span>

<span data-ttu-id="a81a2-108">Пример приложения см. в разделе [поставщик членства и роли](../samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="a81a2-108">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="a81a2-109">Сведения об использовании функции поставщика ролей ASP.NET см. в разделе [как использовать поставщик ролей ASP.NET со службой](how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="a81a2-109">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>

<span data-ttu-id="a81a2-110">Возможность членства требует использования базы данных SQL Server для хранения сведений о пользователе.</span><span class="sxs-lookup"><span data-stu-id="a81a2-110">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="a81a2-111">Эта возможность также включает методы напоминания пользователю его пароля с помощью специального вопроса.</span><span class="sxs-lookup"><span data-stu-id="a81a2-111">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>

<span data-ttu-id="a81a2-112">Разработчики Windows Communication Foundation (WCF) могут воспользоваться преимуществами этих функций в целях обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="a81a2-112">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="a81a2-113">При интеграции в приложение WCF пользователи должны указать сочетание имени пользователя и пароля для клиентского приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="a81a2-113">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="a81a2-114">Чтобы переместить данные в службу WCF, используйте привязку, которая поддерживает учетные данные имени пользователя и пароля, например <xref:System.ServiceModel.WSHttpBinding> (в конфигурации [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ), и задайте для параметра Тип учетных данных клиента значение `UserName` .</span><span class="sxs-lookup"><span data-stu-id="a81a2-114">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="a81a2-115">В службе безопасность WCF проверяет подлинность пользователя на основе имени пользователя и пароля, а также назначает роль, заданную ролью ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a81a2-115">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>

> [!NOTE]
> <span data-ttu-id="a81a2-116">WCF не предоставляет методы для заполнения базы данных сочетаниями имени пользователя и пароля или других сведений о пользователе.</span><span class="sxs-lookup"><span data-stu-id="a81a2-116">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>

### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="a81a2-117">Настройка поставщика членства</span><span class="sxs-lookup"><span data-stu-id="a81a2-117">To configure the membership provider</span></span>

1. <span data-ttu-id="a81a2-118">В файле Web.config в `system.web` элементе <> создайте `membership` элемент <>.</span><span class="sxs-lookup"><span data-stu-id="a81a2-118">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>

2. <span data-ttu-id="a81a2-119">В элементе `<membership>`.</span><span class="sxs-lookup"><span data-stu-id="a81a2-119">Under the `<membership>` element, create a `<providers>` element.</span></span>

3. <span data-ttu-id="a81a2-120">В качестве дочернего элемента для <`providers`> добавьте `<clear />` элемент для очистки коллекции поставщиков.</span><span class="sxs-lookup"><span data-stu-id="a81a2-120">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>

4. <span data-ttu-id="a81a2-121">В `<clear />` элементе создайте `add` элемент <> со следующими атрибутами, для которых заданы соответствующие значения: `name` , `type` ,,,, `connectionStringName` `applicationName` `enablePasswordRetrieval` `enablePasswordReset` , `requiresQuestionAndAnswer` , `requiresUniqueEmail` и `passwordFormat` .</span><span class="sxs-lookup"><span data-stu-id="a81a2-121">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="a81a2-122">Атрибут `name` используется далее в качестве значения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a81a2-122">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="a81a2-123">В следующем примере задается значение `SqlMembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="a81a2-123">The following example sets it to `SqlMembershipProvider`.</span></span>

    <span data-ttu-id="a81a2-124">В следующем примере демонстрируется раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a81a2-124">The following example shows the configuration section.</span></span>

    ```xml
    <!-- Configure the Sql Membership Provider -->
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">
      <providers>
        <clear />
          <add
            name="SqlMembershipProvider"
            type="System.Web.Security.SqlMembershipProvider"
            connectionStringName="SqlConn"
            applicationName="MembershipAndRoleProviderSample"
            enablePasswordRetrieval="false"
            enablePasswordReset="false"
            requiresQuestionAndAnswer="false"
            requiresUniqueEmail="true"
            passwordFormat="Hashed" />
      </providers>
    </membership>
    ```

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="a81a2-125">Настройка системы безопасности службы на прием сочетания имя/пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="a81a2-125">To configure service security to accept the user name/password combination</span></span>

1. <span data-ttu-id="a81a2-126">В файле конфигурации в [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) элементе добавьте [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="a81a2-126">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

2. <span data-ttu-id="a81a2-127">Добавьте в [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) раздел привязок.</span><span class="sxs-lookup"><span data-stu-id="a81a2-127">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="a81a2-128">Дополнительные сведения о создании элемента привязки WCF см. в разделе [инструкции. Указание привязки службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a81a2-128">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

3. <span data-ttu-id="a81a2-129">Задайте атрибуту `mode` элемента `<security>` значение `Message`.</span><span class="sxs-lookup"><span data-stu-id="a81a2-129">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>

4. <span data-ttu-id="a81a2-130">Задайте `clientCredentialType` `message` для атрибута элемента> <значение `UserName` .</span><span class="sxs-lookup"><span data-stu-id="a81a2-130">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="a81a2-131">В этом случае пара "имя пользователя и пароль" будет использоваться в качестве учетной записи клиента.</span><span class="sxs-lookup"><span data-stu-id="a81a2-131">This specifies that a user name/password pair will be used as the client's credential.</span></span>

    <span data-ttu-id="a81a2-132">В следующем примере показан код конфигурации для привязки.</span><span class="sxs-lookup"><span data-stu-id="a81a2-132">The following example shows the configuration code for the binding.</span></span>

    ```xml
    <system.serviceModel>
    <bindings>
      <wsHttpBinding>
      <!-- Set up a binding that uses UserName as the client credential type -->
        <binding name="MembershipBinding">
          <security mode ="Message">
            <message clientCredentialType ="UserName"/>
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    </system.serviceModel>
    ```

### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="a81a2-133">Настройка службы на использование поставщика членства</span><span class="sxs-lookup"><span data-stu-id="a81a2-133">To configure a service to use the membership provider</span></span>

1. <span data-ttu-id="a81a2-134">`<system.serviceModel>`Добавьте элемент в качестве дочернего элемента [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a81a2-134">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element</span></span>

2. <span data-ttu-id="a81a2-135">Добавьте в [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) `behaviors` элемент> <.</span><span class="sxs-lookup"><span data-stu-id="a81a2-135">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>

3. <span data-ttu-id="a81a2-136">Добавьте [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и задайте `name` для атрибута соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="a81a2-136">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>

4. <span data-ttu-id="a81a2-137">Добавьте в [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) `behavior` элемент> <.</span><span class="sxs-lookup"><span data-stu-id="a81a2-137">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>

5. <span data-ttu-id="a81a2-138">Добавьте в [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) `<serviceCredentials>` элемент.</span><span class="sxs-lookup"><span data-stu-id="a81a2-138">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>

6. <span data-ttu-id="a81a2-139">Задайте для атрибута `userNamePasswordValidationMode` значение `MembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="a81a2-139">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a81a2-140">Если `userNamePasswordValidationMode` значение не задано, WCF использует проверку подлинности Windows вместо поставщика членства ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a81a2-140">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>

7. <span data-ttu-id="a81a2-141">Задайте для атрибута `membershipProviderName` значение "имя поставщика" (указывается при добавлении поставщика в первой процедуре данного раздела).</span><span class="sxs-lookup"><span data-stu-id="a81a2-141">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="a81a2-142">В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.</span><span class="sxs-lookup"><span data-stu-id="a81a2-142">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

    ```xml
    <behaviors>
       <serviceBehaviors>
          <behavior name="MyServiceBehavior">
             <serviceCredentials>
                <userNameAuthentication
                userNamePasswordValidationMode="MembershipProvider"
                membershipProviderName="SqlMembershipProvider" />
             </serviceCredentials>
          </behavior>
       </serviceBehaviors>
    </behaviors>
    ```

## <a name="example"></a><span data-ttu-id="a81a2-143">Пример</span><span class="sxs-lookup"><span data-stu-id="a81a2-143">Example</span></span>

<span data-ttu-id="a81a2-144">В следующем коде показана конфигурация службы, использующей возможность членства в ASP.</span><span class="sxs-lookup"><span data-stu-id="a81a2-144">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">
        <endpoint address="http://microsoft.com/WCFservices/Calculator"
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior name="MyServiceBehavior">
          <serviceCredentials>
            <userNameAuthentication
              userNamePasswordValidationMode="MembershipProvider"
              membershipProviderName="SqlMembershipProvider" />
          </serviceCredentials>
        </behavior>
          </serviceBehaviors>
    </behaviors>
    <bindings>
      <wsHttpBinding>
        <binding name="MembershipBinding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a81a2-145">См. также</span><span class="sxs-lookup"><span data-stu-id="a81a2-145">See also</span></span>

- [<span data-ttu-id="a81a2-146">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="a81a2-146">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="a81a2-147">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="a81a2-147">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
