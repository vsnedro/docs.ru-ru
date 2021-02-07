---
description: Дополнительные сведения о безопасности сообщений с анонимным клиентом
title: Безопасность сообщений с анонимным клиентом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
ms.openlocfilehash: 921ddd9e8e7d2a860f3516c452870bc2bb150911
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726979"
---
# <a name="message-security-with-an-anonymous-client"></a>Безопасность сообщений с анонимным клиентом

В следующем сценарии показан клиент и служба, защищенные с помощью защиты сообщений Windows Communication Foundation (WCF). Задача, поставленная при разработке, заключается в использовании безопасности сообщений, а не безопасности транспорта, чтобы в будущем возможно было использование более глубокой модели, использующей утверждения. Дополнительные сведения об использовании расширенных утверждений для авторизации см. [в статье Управление утверждениями и авторизацией с помощью модели удостоверений](managing-claims-and-authorization-with-the-identity-model.md).

Пример приложения см. в разделе [безопасность сообщений анонимно](../samples/message-security-anonymous.md).

![Безопасность сообщений с анонимным клиентом](media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")

|Характеристика|Описание|
|--------------------|-----------------|
|Режим безопасности|Сообщение|
|Совместимость|Только WCF|
|Проверка подлинности (сервера)|Первоначальное согласование возможно только после проверки подлинности сервера, но не клиента|
|Проверка подлинности (клиента)|None|
|Целостность|Да, используется общий контекст безопасности|
|Конфиденциальность|Да, используется общий контекст безопасности|
|Транспорт|HTTP|

## <a name="service"></a>Служба

Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.

- Создайте автономную службу, используя код без конфигурации.

- Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.

### <a name="code"></a>Код

В следующем коде показано, как создать конечную точку службы, которая использует безопасность сообщений.

[!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
[!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]

### <a name="configuration"></a>Конфигурация

Вместо кода можно использовать следующую конфигурацию. Элемент поведения службы используется для указания сертификата, который используется для проверки подлинности службы для клиента. Элемент службы должен задавать поведение с помощью атрибута `behaviorConfiguration`. Элемент привязки указывает, что типу учетных данных клиента присвоено значение `None`, позволяя анонимному клиенту использовать службу.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="ServiceCredentialsBehavior">
          <serviceCredentials>
            <serviceCertificate findValue="contoso.com"
                                storeLocation="LocalMachine"
                                storeName="My" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <services>
      <service behaviorConfiguration="ServiceCredentialsBehavior"
               name="ServiceModel.Calculator">
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="CalculatorService"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a>Клиент

Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.

- Создайте автономный клиент, используя код (и код клиента).

- Создайте клиент, который не определяет никаких адресов конечных точек. Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации. Пример:

    [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
    [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a>Код

В следующем примере кода создается экземпляр клиента. Привязка использует безопасность режима сообщений, и тип учетных данных клиента задан как None.

[!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
[!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]

### <a name="configuration"></a>Конфигурация

Следующий код служит для настройки клиента.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://machineName/Calculator"
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_ICalculator"
        contract="ICalculator"
        name="WSHttpBinding_ICalculator">
        <identity>
          <dns value="contoso.com" />
        </identity>
      </endpoint>
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>См. также

- [Обзор безопасности](security-overview.md)
- [Защита распределенных приложений](distributed-application-security.md)
- [Безопасность сообщений с возможностью анонимного доступа](../samples/message-security-anonymous.md)
- [Идентификация и проверка подлинности службы](service-identity-and-authentication.md)
- [Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
