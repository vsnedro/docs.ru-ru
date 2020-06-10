---
title: Практическое руководство. Обмен сообщениями в рамках надежного сеанса
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 5b01ddfd95db2f7e88f9481265c348f4f16fbbee
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579480"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Практическое руководство. Обмен сообщениями в рамках надежного сеанса

В этом разделе описываются действия, необходимые, чтобы разрешить надежные сеансы с помощью одной из привязок, предоставляемых системой, которая поддерживает такие сеансы, но не по умолчанию. Надежный сеанс можно включить принудительно с помощью кода или декларативно в файле конфигурации. В этой процедуре используются файлы конфигурации клиента и службы для включения надежного сеанса и указания того, что сообщения поступают в том же порядке, в котором они были отправлены.

Основная часть этой процедуры состоит в том, что элемент конфигурации конечной точки содержит `bindingConfiguration` атрибут, который ссылается на конфигурацию привязки с именем `Binding1` . [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)Элемент Configuration ссылается на это имя, чтобы включить надежные сеансы, задав `enabled` атрибуту [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) элемента значение `true` . Можно обеспечить доставку сообщений в порядке их отправки для надежного сеанса, присвоив атрибуту `ordered` значение `true`.

Исходный экземпляр этого примера см. в разделе [WS надежный сеанс](../samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Настройка службы с помощью WSHttpBinding для использования надежного сеанса

1. Определите контракт службы для данного типа службы.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Реализуйте контракт службы в классе службы. Обратите внимание, что адрес или сведения о привязке не указываются внутри реализации службы. Вам не нужно писать код для получения адреса или сведений о привязке из файла конфигурации.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Создайте файл *Web. config* , чтобы настроить конечную точку для `CalculatorService` , в которой <xref:System.ServiceModel.WSHttpBinding> включена служба с включенным надежным сеансом и упорядоченная доставка требуемых сообщений.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Создайте файл *Service. svc* , содержащий строку:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Поместите файл *Service. svc* в виртуальный каталог службы IIS (IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Настройка клиента с помощью WSHttpBinding для использования надежного сеанса

1. Используйте [средство служебной программы метаданных ServiceModel (*Svcutil. exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы.

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Созданный клиент содержит `ICalculator` интерфейс, определяющий контракт службы, которому должна соответствовать реализация клиента.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. Созданное клиентское приложение также содержит реализацию `ClientCalculator`. Обратите внимание, что адрес и сведения о привязке не указываются ни в одном месте внутри реализации службы. Вам не нужно писать код для получения адреса или сведений о привязке из файла конфигурации.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil. exe* также создает конфигурацию для клиента, использующего <xref:System.ServiceModel.WSHttpBinding> класс. Назовите файл конфигурации *app. config* при использовании Visual Studio.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Скомпилируйте и запустите клиент.

## <a name="example"></a>Пример

Некоторые привязки, предоставляемые системой, по умолчанию поддерживают надежные сеансы. Сюда входит следующее.

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Пример создания пользовательской привязки, поддерживающей надежные сеансы, см. [в разделе как создать настраиваемую привязку надежного сеанса с помощью протокола HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>Дополнительно

- [Надежные сеансы](reliable-sessions.md)
