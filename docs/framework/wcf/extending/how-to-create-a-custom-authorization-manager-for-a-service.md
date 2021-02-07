---
description: Дополнительные сведения о том, как создать пользовательский диспетчер авторизации для службы.
title: Практическое руководство. Создание пользовательского диспетчера авторизации для службы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
ms.openlocfilehash: e5b5655bb8cd087e2c5140f45e80f8b079cf06c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743724"
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a>Практическое руководство. Создание пользовательского диспетчера авторизации для службы

Инфраструктура модели удостоверений в Windows Communication Foundation (WCF) поддерживает расширяемую модель авторизации на основе утверждений. Утверждения извлекаются из маркеров, дополнительно обрабатываемых пользовательской политикой авторизации, и затем помещаются в контекст <xref:System.IdentityModel.Policy.AuthorizationContext>. Диспетчер авторизации проверяет утверждения в контексте <xref:System.IdentityModel.Policy.AuthorizationContext> для принятия решений об авторизации.

По умолчанию решения об авторизации принимаются классом <xref:System.ServiceModel.ServiceAuthorizationManager>; однако эти решения можно переопределить, создав пользовательский диспетчер авторизации. Чтобы создать пользовательский диспетчер авторизации, создайте класс, наследующий от класса <xref:System.ServiceModel.ServiceAuthorizationManager>, и реализуйте метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Решения об авторизации принимаются в методе <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>, который возвращает `true`, если доступ предоставлен, и `false`, если в доступе отказано.

Если решение об авторизации зависит от содержимого тела сообщения, используйте метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.

В связи с вопросами производительности при возможности следует внести изменения в приложение, чтобы решение об авторизации не требовало доступа к телу сообщения.

Пользовательский диспетчер авторизации для службы можно зарегистрировать в коде или конфигурации.

### <a name="to-create-a-custom-authorization-manager"></a>Создание пользовательского диспетчера авторизации

1. Создайте класс, производный от класса <xref:System.ServiceModel.ServiceAuthorizationManager>.

    [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
    [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]

2. Переопределите метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> .

    Для принятия решения об авторизации используйте метод <xref:System.ServiceModel.OperationContext>, передаваемый в метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>.

    В следующем примере кода метод <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> используется для поиска пользовательского утверждения `http://www.contoso.com/claims/allowedoperation` и принятия решения об авторизации.

    [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
    [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]

### <a name="to-register-a-custom-authorization-manager-using-code"></a>Регистрация пользовательского диспетчера авторизации с помощью кода

1. Создайте экземпляр пользовательского диспетчера авторизации и назначьте его свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.

    Доступ к поведению <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> возможен с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.

    В следующем примере кода регистрируется пользовательский диспетчер авторизации `MyServiceAuthorizationManager`.

    [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
    [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]

### <a name="to-register-a-custom-authorization-manager-using-configuration"></a>Регистрация пользовательского диспетчера авторизации с помощью конфигурации

1. Откройте файл конфигурации службы.

2. Добавьте в [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) .

    В [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) добавьте `serviceAuthorizationManagerType` атрибут и задайте для его значения тип, представляющий пользовательский диспетчер авторизации.

3. Добавьте привязку, обеспечивающую безопасность связи между клиентом и службой.

    Привязка, выбранная для этой связи, определяет утверждения, добавляемые в контекст <xref:System.IdentityModel.Policy.AuthorizationContext> и используемые пользовательским диспетчером авторизации для принятия решений об авторизации. Дополнительные сведения о привязках, предоставляемых системой, см. в разделе [привязки, предоставляемые системой](../system-provided-bindings.md).

4. Свяжите поведение с конечной точкой службы, добавив [\<service>](../../configure-apps/file-schema/wcf/service.md) элемент и задав `behaviorConfiguration` для атрибута значение атрибута Name для [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемента.

    Дополнительные сведения о настройке конечной точки службы см. в разделе [инструкции. Создание конечной точки службы в конфигурации](../feature-details/how-to-create-a-service-endpoint-in-configuration.md).

    В следующем примере кода регистрируется пользовательский диспетчер авторизации `Samples.MyServiceAuthorizationManager`.

    ```xml
    <configuration>
      <system.serviceModel>
        <services>
          <service
              name="Microsoft.ServiceModel.Samples.CalculatorService"
              behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <endpoint address=""
                      binding="wsHttpBinding_Calculator"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
          </service>
        </services>
        <bindings>
          <WSHttpBinding>
           <binding name = "wsHttpBinding_Calculator">
             <security mode="Message">
               <message clientCredentialType="Windows"/>
             </security>
            </binding>
          </WSHttpBinding>
        </bindings>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceAuthorization serviceAuthorizationManagerType="Samples.MyServiceAuthorizationManager,MyAssembly" />
             </behavior>
         </serviceBehaviors>
       </behaviors>
      </system.serviceModel>
    </configuration>
    ```

    > [!WARNING]
    > Обратите внимание, что при указании serviceAuthorizationManagerType строка должна содержать полное имя типа. запятая и имя сборки, в которой определен тип. Если опустить имя сборки, WCF попытается загрузить тип из System.ServiceModel.dll.

## <a name="example"></a>Пример

В следующем образце кода показана базовая реализация класса <xref:System.ServiceModel.ServiceAuthorizationManager>, которая содержит переопределение метода <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. В этом примере кода производится проверка <xref:System.IdentityModel.Policy.AuthorizationContext> на наличие пользовательского утверждения и возвращается `true`, если ресурс для этого пользовательского утверждения соответствует значению действия из контекста <xref:System.ServiceModel.OperationContext>. Более полную реализацию <xref:System.ServiceModel.ServiceAuthorizationManager> класса см. в разделе [Политика авторизации](../samples/authorization-policy.md).

[!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
[!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Политика авторизации](../samples/authorization-policy.md)
