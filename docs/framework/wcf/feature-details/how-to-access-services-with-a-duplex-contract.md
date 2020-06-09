---
title: Руководство. доступ к службам с помощью дуплексного контракта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: bc42792b827b49265a0b1addf959de2fa1a041e3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597219"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Руководство. доступ к службам с помощью дуплексного контракта

Одной из функций Windows Communication Foundation (WCF) является возможность создания службы, использующей шаблон двустороннего обмена сообщениями. Такой шаблон позволяет службе взаимодействовать с клиентом с помощью обратного вызова. В этом разделе описаны действия по созданию клиента WCF в клиентском классе, реализующем интерфейс обратного вызова.

Двойная привязка предоставляет службе IP-адрес клиента. Клиент должен использовать механизм безопасности, чтобы обеспечить подключение только к доверенным службам.

Руководство по созданию базовой службы WCF и клиента см. в разделе [Начало работы учебник](../getting-started-tutorial.md).

## <a name="to-access-a-duplex-service"></a>Доступ к дуплексной службе

1. Создайте службу, содержащую два интерфейса. Первый интерфейс предназначен для службы, второй - для обратного вызова. Дополнительные сведения о создании дуплексной службы см. [в разделе инструкции. Создание дуплексного контракта](how-to-create-a-duplex-contract.md).

2. Запустите службу.

3. Используйте [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контрактов (интерфейсов) для клиента. Сведения о том, как это сделать, см. [в разделе инструкции. Создание клиента](../how-to-create-a-wcf-client.md).

4. Реализуйте в классе клиента интерфейс обратного вызова, как показано в следующем примере.

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. Создайте экземпляр класса <xref:System.ServiceModel.InstanceContext>. Конструктору требуется экземпляр класса клиента.

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. Создайте экземпляр клиента WCF с помощью конструктора, для которого требуется <xref:System.ServiceModel.InstanceContext> объект. Вторым параметром конструктора является имя конечной точки, определенное в файле конфигурации.

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. При необходимости вызывайте методы клиента WCF.

## <a name="example"></a>Пример

В следующем примере кода показано, как создать класс клиента, обращающийся к дуплексному контракту.

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a>Дополнительно

- [Учебник по начало работы](../getting-started-tutorial.md)
- [Практическое руководство. Создание двухстороннего контракта](how-to-create-a-duplex-contract.md)
- [Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Практическое руководство. Создание клиента](../how-to-create-a-wcf-client.md)
- [Практическое руководство. Использование ChannelFactory](how-to-use-the-channelfactory.md)
