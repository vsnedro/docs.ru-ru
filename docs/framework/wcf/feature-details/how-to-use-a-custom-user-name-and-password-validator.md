---
title: Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 5ada34ca2d0d757ea333fed60aef179d6578356c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601183"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="060c1-102">Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="060c1-102">How to: Use a Custom User Name and Password Validator</span></span>

<span data-ttu-id="060c1-103">По умолчанию, если для проверки подлинности используется имя пользователя и пароль, Windows Communication Foundation (WCF) использует Windows для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="060c1-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="060c1-104">Однако WCF позволяет создавать пользовательские схемы проверки подлинности имени пользователя и пароля, которые также называются *проверяющими*.</span><span class="sxs-lookup"><span data-stu-id="060c1-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="060c1-105">Чтобы внедрить пользовательский проверяющий элемент управления для проверки подлинности имени пользователя и пароля, необходимо создать класс, унаследованный от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, и настроить его.</span><span class="sxs-lookup"><span data-stu-id="060c1-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>

<span data-ttu-id="060c1-106">Пример приложения см. в разделе [средство проверки пароля для имени пользователя](../samples/user-name-password-validator.md).</span><span class="sxs-lookup"><span data-stu-id="060c1-106">For a sample application, see [User Name Password Validator](../samples/user-name-password-validator.md).</span></span>

### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="060c1-107">Создание пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="060c1-107">To create a custom user name and password validator</span></span>

1. <span data-ttu-id="060c1-108">Создайте класс, наследующий от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="060c1-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <span data-ttu-id="060c1-109">Реализуйте пользовательскую схему проверки подлинности, переопределив метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="060c1-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    <span data-ttu-id="060c1-110">Не используйте код следующего примера, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="060c1-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="060c1-111">Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.</span><span class="sxs-lookup"><span data-stu-id="060c1-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

    <span data-ttu-id="060c1-112">Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="060c1-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="060c1-113">Настройка службы для использования пользовательского проверяющего элемента управления для проверки имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="060c1-113">To configure a service to use a custom user name and password validator</span></span>

1. <span data-ttu-id="060c1-114">Настройте привязку, использующую безопасность сообщений с любым транспортом или безопасность на уровне транспорта по HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="060c1-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>

    <span data-ttu-id="060c1-115">При использовании безопасности сообщений добавьте одну из предоставляемых системой привязок, например [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , или [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) , которая поддерживает безопасность сообщений и `UserName` тип учетных данных.</span><span class="sxs-lookup"><span data-stu-id="060c1-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>

    <span data-ttu-id="060c1-116">При использовании безопасности на транспортном уровне через HTTP (S) добавьте либо [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) или [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) , [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) либо, с [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) использованием HTTP (S), и `Basic` схему проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="060c1-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>

    > [!NOTE]
    > <span data-ttu-id="060c1-117">При использовании .NET Framework 3,5 или более поздних версий можно использовать пользовательское средство проверки имени пользователя и пароля с защитой сообщений и транспорта.</span><span class="sxs-lookup"><span data-stu-id="060c1-117">When using .NET Framework 3.5 or later versions, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="060c1-118">С помощью WinFX пользовательское средство проверки имени пользователя и пароля может использоваться только с защитой сообщений.</span><span class="sxs-lookup"><span data-stu-id="060c1-118">With WinFX, a custom username and password validator can only be used with message security.</span></span>

    > [!TIP]
    > <span data-ttu-id="060c1-119">Дополнительные сведения об использовании \<netTcpBinding> в этом контексте см. в разделе [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="060c1-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).</span></span>

    1. <span data-ttu-id="060c1-120">В файле конфигурации в [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) элементе добавьте [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="060c1-120">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

    2. <span data-ttu-id="060c1-121">Добавьте [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) элемент или [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) в раздел привязок.</span><span class="sxs-lookup"><span data-stu-id="060c1-121">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="060c1-122">Дополнительные сведения о создании элемента привязки WCF см. в разделе [инструкции. Указание привязки службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="060c1-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    3. <span data-ttu-id="060c1-123">Задайте `mode` для атрибута или значение [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) `Message` , `Transport` или `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="060c1-123">Set the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

    4. <span data-ttu-id="060c1-124">Задайте `clientCredentialType` атрибут [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) или [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="060c1-124">Set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>

        <span data-ttu-id="060c1-125">При использовании безопасности сообщений установите атрибут в значение `clientCredentialType` [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) `UserName` .</span><span class="sxs-lookup"><span data-stu-id="060c1-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>

        <span data-ttu-id="060c1-126">При использовании безопасности на транспортном уровне через HTTP (S) задайте `clientCredentialType` [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) для атрибута или значение [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) `Basic` .</span><span class="sxs-lookup"><span data-stu-id="060c1-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>

        > [!NOTE]
        > <span data-ttu-id="060c1-127">Если служба WCF размещается в службы IIS (IIS) с использованием безопасности на транспортном уровне <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> , а свойство имеет значение <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> , настраиваемая схема проверки подлинности использует подмножество проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="060c1-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="060c1-128">Это связано с тем, что в этом случае IIS выполняет проверку подлинности Windows перед тем, как WCF вызовет настраиваемую проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="060c1-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>

    <span data-ttu-id="060c1-129">Дополнительные сведения о создании элемента привязки WCF см. в разделе [инструкции. Указание привязки службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="060c1-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    <span data-ttu-id="060c1-130">В следующем примере показан код конфигурации для привязки:</span><span class="sxs-lookup"><span data-stu-id="060c1-130">The following example shows the configuration code for the binding:</span></span>

    ```xml
    <system.serviceModel>
      <bindings>
      <wsHttpBinding>
          <binding name="Binding1">
            <security mode="Message">
              <message clientCredentialType="UserName" />
            </security>
          </binding>
        </wsHttpBinding>
      </bindings>
    </system.serviceModel>
    ```

2. <span data-ttu-id="060c1-131">Настройте поведение, которое будет указывать, что для проверки пар имени пользователя и пароля для входящих маркеров безопасности <xref:System.IdentityModel.Tokens.UserNameSecurityToken> будет использоваться пользовательский проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="060c1-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>

    1. <span data-ttu-id="060c1-132">Добавьте элемент в качестве дочернего [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) элемента [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="060c1-132">As a child to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    2. <span data-ttu-id="060c1-133">Добавьте в [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="060c1-133">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    3. <span data-ttu-id="060c1-134">Добавьте [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемент и присвойте `name` атрибуту соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="060c1-134">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>

    4. <span data-ttu-id="060c1-135">Добавьте в [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="060c1-135">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    5. <span data-ttu-id="060c1-136">Добавьте в [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="060c1-136">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

    6. <span data-ttu-id="060c1-137">Измените `userNamePasswordValidationMode` на `Custom`.</span><span class="sxs-lookup"><span data-stu-id="060c1-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="060c1-138">Если `userNamePasswordValidationMode` значение не задано, WCF использует проверку подлинности Windows вместо настраиваемого средства проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="060c1-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>

    7. <span data-ttu-id="060c1-139">Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="060c1-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>

    <span data-ttu-id="060c1-140">В следующем примере `<serviceCredentials>` фрагмент кода показан на этом этапе:</span><span class="sxs-lookup"><span data-stu-id="060c1-140">The following example shows the `<serviceCredentials>` fragment to this point:</span></span>

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a><span data-ttu-id="060c1-141">Пример</span><span class="sxs-lookup"><span data-stu-id="060c1-141">Example</span></span>

<span data-ttu-id="060c1-142">В следующем примере кода показано, как создать пользовательский проверяющий элемент управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="060c1-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="060c1-143">Не используйте код, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="060c1-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="060c1-144">Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.</span><span class="sxs-lookup"><span data-stu-id="060c1-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a><span data-ttu-id="060c1-145">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="060c1-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="060c1-146">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="060c1-146">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="060c1-147">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="060c1-147">Authentication</span></span>](authentication-in-wcf.md)
