---
title: Безопасность транспорта с проверкой подлинности Windows
description: Ознакомьтесь с этим сценарием, в котором показан клиент или служба WCF, защищенные системой безопасности Windows. В этом примере служба интрасети отображает сведения о персонале.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 9b81f2f2fb6352af254146951ed35ad4fdca8caa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545211"
---
# <a name="transport-security-with-windows-authentication"></a>Безопасность транспорта с проверкой подлинности Windows
В следующем сценарии показан клиент Windows Communication Foundation (WCF) и служба, защищенная системой безопасности Windows. Дополнительные сведения о программировании см. [в разделе как защитить службу с помощью учетных данных Windows](../how-to-secure-a-service-with-windows-credentials.md).  
  
 Веб-служба интрасети отображает информацию о персонале. Клиентом является приложение Windows Forms. Приложение развернуто на домене с защищающем его контроллером Kerberos.  
  
 ![Безопасность транспорта с аутентификацией Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Режим безопасности|Транспорт|  
|Совместимость|Только WCF|  
|Проверка подлинности (сервера)<br /><br /> Проверка подлинности (клиента)|Да (при помощи встроенной проверки подлинности Windows)<br /><br /> Да (при помощи встроенной проверки подлинности Windows)|  
|Целостность|Да|  
|Конфиденциальность|Да|  
|Транспорт|NET.TCP|  
|Привязка|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a>Служба  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.  
  
- Создайте автономную службу, используя код без конфигурации.  
  
- Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.  
  
### <a name="code"></a>Код  
 В следующем коде показано, как создать конечную точку службы, которая использует безопасность Windows.  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a>Конфигурация  
 Вместо кода для настройки конечной точки службы можно использовать следующую конфигурацию.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
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
 Следующий код служит для создания клиента. Привязка настроена на использование безопасности транспортного режима с транспортом TCP, с типом учетных данных клиента, установленных на Windows.  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a>Конфигурация  
 Вместо кода для создания клиента можно использовать следующую конфигурацию.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Обзор безопасности](security-overview.md)
- [Практическое руководство. Защита службы с использованием учетных данных Windows](../how-to-secure-a-service-with-windows-credentials.md)
- [Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
