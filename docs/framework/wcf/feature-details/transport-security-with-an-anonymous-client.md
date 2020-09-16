---
title: Безопасность транспорта с анонимным клиентом
description: Ознакомьтесь с этим сценарием WCF, который использует безопасность транспорта для проверки подлинности сервера с помощью сертификата, которому доверяет клиент. Проверка подлинности клиента не выполнена.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 5e8bcab4cdd8f27e9ea27e66fe4c848ccd35e99c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556815"
---
# <a name="transport-security-with-an-anonymous-client"></a>Безопасность транспорта с анонимным клиентом

Этот сценарий Windows Communication Foundation (WCF) использует безопасность транспорта (HTTPS) для обеспечения конфиденциальности и целостности. Сервер должен пройти проверку подлинности с использованием сертификата SSL, и клиенты должны доверять сертификату сервера. Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.

Пример приложения см. в разделе [WS Transport Security](../samples/ws-transport-security.md). Дополнительные сведения о безопасности транспорта см. в статье [Общие сведения о безопасности транспорта](transport-security-overview.md).

Дополнительные сведения об использовании сертификата со службой см. в разделе [Работа с](working-with-certificates.md) сертификатами и [инструкции. Настройка порта с помощью SSL-сертификата](how-to-configure-a-port-with-an-ssl-certificate.md).

![Использование безопасности транспорта с анонимным клиентом](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|Характеристика|Описание|
|--------------------|-----------------|
|Режим безопасности|Транспорт|
|Совместимость|С существующими веб-службами и клиентами|
|Проверка подлинности (сервера)<br /><br /> Проверка подлинности (клиента)|Да<br /><br /> Уровень приложения (без поддержки WCF)|
|Целостность|Да|
|Конфиденциальность|Да|
|Транспорт|HTTPS|
|Привязка|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a>Служба

Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.

- Создайте автономную службу, используя код без конфигурации.

- Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.

### <a name="code"></a>Код

В следующем коде показано создание конечной точки с использованием безопасности транспорта:

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a>Конфигурация

В следующем коде настраивается та же конечная точка с использованием конфигурации. Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
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

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a>Код

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a>Конфигурация

Вместо кода для настройки службы можно использовать следующую конфигурацию.

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>См. также

- [Обзор безопасности](security-overview.md)
- [Безопасность транспорта WS](../samples/ws-transport-security.md)
- [Общие сведения о безопасности транспорта](transport-security-overview.md)
- [Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
