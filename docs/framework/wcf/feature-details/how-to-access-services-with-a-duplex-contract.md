---
description: Дополнительные сведения см. в статье как получить доступ к службам с помощью дуплексного контракта.
title: Руководство. доступ к службам с помощью дуплексного контракта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: e58225e6b77115004c3c201d606e328aab184b75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742892"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Руководство. доступ к службам с помощью дуплексного контракта

Одной из функций Windows Communication Foundation (WCF) является возможность создания службы, использующей шаблон двустороннего обмена сообщениями. Такой шаблон позволяет службе взаимодействовать с клиентом с помощью обратного вызова. В этом разделе описаны действия по созданию клиента WCF в клиентском классе, реализующем интерфейс обратного вызова.

Двойная привязка предоставляет службе IP-адрес клиента. Клиент должен использовать механизм безопасности, чтобы обеспечить подключение только к доверенным службам.

Руководство по созданию базовой службы WCF и клиента см. в разделе [Начало работы учебник](../getting-started-tutorial.md).

## <a name="to-access-a-duplex-service"></a>Доступ к дуплексной службе

1. Создайте службу, содержащую два интерфейса. Первый интерфейс предназначен для службы, второй - для обратного вызова. Дополнительные сведения о создании дуплексной службы см. [в разделе инструкции. Создание дуплексного контракта](how-to-create-a-duplex-contract.md).

2. Запустите службу.

3. Используйте [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контрактов (интерфейсов) для клиента. Сведения о том, как это сделать, см.  [в разделе инструкции. Создание клиента](../how-to-create-a-wcf-client.md).

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

## <a name="see-also"></a>См. также

- [Учебник по началу работы](../getting-started-tutorial.md)
- [Практическое руководство. Создание двухстороннего контракта](how-to-create-a-duplex-contract.md)
- [Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Практическое руководство. Создание клиента](../how-to-create-a-wcf-client.md)
- [Практическое руководство. Использование ChannelFactory](how-to-use-the-channelfactory.md)
