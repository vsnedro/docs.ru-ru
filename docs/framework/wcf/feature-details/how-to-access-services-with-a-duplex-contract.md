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
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="f4e1b-102">Руководство. доступ к службам с помощью дуплексного контракта</span><span class="sxs-lookup"><span data-stu-id="f4e1b-102">How to: Access services with a duplex contract</span></span>

<span data-ttu-id="f4e1b-103">Одной из функций Windows Communication Foundation (WCF) является возможность создания службы, использующей шаблон двустороннего обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="f4e1b-104">Такой шаблон позволяет службе взаимодействовать с клиентом с помощью обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="f4e1b-105">В этом разделе описаны действия по созданию клиента WCF в клиентском классе, реализующем интерфейс обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>

<span data-ttu-id="f4e1b-106">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="f4e1b-107">Клиент должен использовать механизм безопасности, чтобы обеспечить подключение только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-107">The client should use security to ensure that it connects only to services it trusts.</span></span>

<span data-ttu-id="f4e1b-108">Руководство по созданию базовой службы WCF и клиента см. в разделе [Начало работы учебник](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f4e1b-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../getting-started-tutorial.md).</span></span>

## <a name="to-access-a-duplex-service"></a><span data-ttu-id="f4e1b-109">Доступ к дуплексной службе</span><span class="sxs-lookup"><span data-stu-id="f4e1b-109">To access a duplex service</span></span>

1. <span data-ttu-id="f4e1b-110">Создайте службу, содержащую два интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="f4e1b-111">Первый интерфейс предназначен для службы, второй - для обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="f4e1b-112">Дополнительные сведения о создании дуплексной службы см. [в разделе инструкции. Создание дуплексного контракта](how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f4e1b-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>

2. <span data-ttu-id="f4e1b-113">Запустите службу.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-113">Run the service.</span></span>

3. <span data-ttu-id="f4e1b-114">Используйте [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контрактов (интерфейсов) для клиента.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="f4e1b-115">Сведения о том, как это сделать, см. [в разделе инструкции. Создание клиента](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="f4e1b-115">For information about how to do this, see  [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

4. <span data-ttu-id="f4e1b-116">Реализуйте в классе клиента интерфейс обратного вызова, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-116">Implement the callback interface in the client class, as shown in the following example.</span></span>

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

5. <span data-ttu-id="f4e1b-117">Создайте экземпляр класса <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="f4e1b-118">Конструктору требуется экземпляр класса клиента.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-118">The constructor requires an instance of the client class.</span></span>

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. <span data-ttu-id="f4e1b-119">Создайте экземпляр клиента WCF с помощью конструктора, для которого требуется <xref:System.ServiceModel.InstanceContext> объект.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="f4e1b-120">Вторым параметром конструктора является имя конечной точки, определенное в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. <span data-ttu-id="f4e1b-121">При необходимости вызывайте методы клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-121">Call the methods of the WCF client as required.</span></span>

## <a name="example"></a><span data-ttu-id="f4e1b-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f4e1b-122">Example</span></span>

<span data-ttu-id="f4e1b-123">В следующем примере кода показано, как создать класс клиента, обращающийся к дуплексному контракту.</span><span class="sxs-lookup"><span data-stu-id="f4e1b-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a><span data-ttu-id="f4e1b-124">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f4e1b-124">See also</span></span>

- [<span data-ttu-id="f4e1b-125">Учебник по начало работы</span><span class="sxs-lookup"><span data-stu-id="f4e1b-125">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="f4e1b-126">Практическое руководство. Создание двухстороннего контракта</span><span class="sxs-lookup"><span data-stu-id="f4e1b-126">How to: Create a Duplex Contract</span></span>](how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="f4e1b-127">Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="f4e1b-127">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="f4e1b-128">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="f4e1b-128">How to: Create a Client</span></span>](../how-to-create-a-wcf-client.md)
- [<span data-ttu-id="f4e1b-129">Практическое руководство. Использование ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f4e1b-129">How to: Use the ChannelFactory</span></span>](how-to-use-the-channelfactory.md)
