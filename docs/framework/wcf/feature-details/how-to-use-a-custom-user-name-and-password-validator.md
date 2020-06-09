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
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля

По умолчанию, если для проверки подлинности используется имя пользователя и пароль, Windows Communication Foundation (WCF) использует Windows для проверки имени пользователя и пароля. Однако WCF позволяет создавать пользовательские схемы проверки подлинности имени пользователя и пароля, которые также называются *проверяющими*. Чтобы внедрить пользовательский проверяющий элемент управления для проверки подлинности имени пользователя и пароля, необходимо создать класс, унаследованный от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, и настроить его.

Пример приложения см. в разделе [средство проверки пароля для имени пользователя](../samples/user-name-password-validator.md).

### <a name="to-create-a-custom-user-name-and-password-validator"></a>Создание пользовательского проверяющего элемента управления для имени пользователя и пароля

1. Создайте класс, наследующий от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. Реализуйте пользовательскую схему проверки подлинности, переопределив метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.

    Не используйте код следующего примера, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде. Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.

    Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Настройка службы для использования пользовательского проверяющего элемента управления для проверки имени пользователя и пароля

1. Настройте привязку, использующую безопасность сообщений с любым транспортом или безопасность на уровне транспорта по HTTP(S).

    При использовании безопасности сообщений добавьте одну из предоставляемых системой привязок, например [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , или [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) , которая поддерживает безопасность сообщений и `UserName` тип учетных данных.

    При использовании безопасности на транспортном уровне через HTTP (S) добавьте либо [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) или [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) , [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) либо, с [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) использованием HTTP (S), и `Basic` схему проверки подлинности.

    > [!NOTE]
    > При использовании .NET Framework 3,5 или более поздних версий можно использовать пользовательское средство проверки имени пользователя и пароля с защитой сообщений и транспорта. С помощью WinFX пользовательское средство проверки имени пользователя и пароля может использоваться только с защитой сообщений.

    > [!TIP]
    > Дополнительные сведения об использовании \<netTcpBinding> в этом контексте см. в разделе [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md) .

    1. В файле конфигурации в [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) элементе добавьте [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) элемент.

    2. Добавьте [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) элемент или [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) в раздел привязок. Дополнительные сведения о создании элемента привязки WCF см. в разделе [инструкции. Указание привязки службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).

    3. Задайте `mode` для атрибута или значение [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) `Message` , `Transport` или `TransportWithMessageCredential` .

    4. Задайте `clientCredentialType` атрибут [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) или [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) .

        При использовании безопасности сообщений установите атрибут в значение `clientCredentialType` [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) `UserName` .

        При использовании безопасности на транспортном уровне через HTTP (S) задайте `clientCredentialType` [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) для атрибута или значение [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) `Basic` .

        > [!NOTE]
        > Если служба WCF размещается в службы IIS (IIS) с использованием безопасности на транспортном уровне <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> , а свойство имеет значение <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> , настраиваемая схема проверки подлинности использует подмножество проверки подлинности Windows. Это связано с тем, что в этом случае IIS выполняет проверку подлинности Windows перед тем, как WCF вызовет настраиваемую проверку подлинности.

    Дополнительные сведения о создании элемента привязки WCF см. в разделе [инструкции. Указание привязки службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).

    В следующем примере показан код конфигурации для привязки:

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

2. Настройте поведение, которое будет указывать, что для проверки пар имени пользователя и пароля для входящих маркеров безопасности <xref:System.IdentityModel.Tokens.UserNameSecurityToken> будет использоваться пользовательский проверяющий элемент управления.

    1. Добавьте элемент в качестве дочернего [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) элемента [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) .

    2. Добавьте в [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) элемент.

    3. Добавьте [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемент и присвойте `name` атрибуту соответствующее значение.

    4. Добавьте в [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемент.

    5. Добавьте в [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .

    6. Измените `userNamePasswordValidationMode` на `Custom`.

        > [!IMPORTANT]
        > Если `userNamePasswordValidationMode` значение не задано, WCF использует проверку подлинности Windows вместо настраиваемого средства проверки имени пользователя и пароля.

    7. Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.

    В следующем примере `<serviceCredentials>` фрагмент кода показан на этом этапе:

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a>Пример

В следующем примере кода показано, как создать пользовательский проверяющий элемент управления для проверки имени пользователя и пароля. Не используйте код, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде. Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a>Дополнительно

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [Практическое руководство. Использование поставщика членства ASP.NET](how-to-use-the-aspnet-membership-provider.md)
- [Аутентификация](authentication-in-wcf.md)
