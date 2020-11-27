---
title: Практическое руководство. Создание контракта типа "запрос — ответ"
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 506ce527348286bb53223c64245c74e4cb21879a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286556"
---
# <a name="how-to-create-a-request-reply-contract"></a><span data-ttu-id="30e45-102">Практическое руководство. Создание контракта типа "запрос — ответ"</span><span class="sxs-lookup"><span data-stu-id="30e45-102">How to: Create a Request-Reply Contract</span></span>

<span data-ttu-id="30e45-103">Контракт «запрос-ответ» указывает метод, который возвращает ответ.</span><span class="sxs-lookup"><span data-stu-id="30e45-103">A request-reply contract specifies a method that returns a reply.</span></span> <span data-ttu-id="30e45-104">Необходима отправка ответа и его корреляция запросу согласно условиям этого контракта.</span><span class="sxs-lookup"><span data-stu-id="30e45-104">The reply must be sent and correlated to the request under the terms of this contract.</span></span> <span data-ttu-id="30e45-105">Даже если метод не возвращает ответ (`void` в C# или `Sub` в Visual Basic), инфраструктура создает и отправляет вызывающему объекту пустое сообщение.</span><span class="sxs-lookup"><span data-stu-id="30e45-105">Even if the method returns no reply (`void` in C#, or a `Sub` in Visual Basic), the infrastructure creates and sends an empty message to the caller.</span></span> <span data-ttu-id="30e45-106">Чтобы запретить отправку пустого ответного сообщения, используйте для операции односторонний контракт.</span><span class="sxs-lookup"><span data-stu-id="30e45-106">To prevent the sending of an empty reply message, use a one-way contract for the operation.</span></span>  
  
### <a name="to-create-a-request-reply-contract"></a><span data-ttu-id="30e45-107">Создание контракта типа запрос-ответ</span><span class="sxs-lookup"><span data-stu-id="30e45-107">To create a request-reply contract</span></span>  
  
1. <span data-ttu-id="30e45-108">Создайте интерфейс на любом языке программирования.</span><span class="sxs-lookup"><span data-stu-id="30e45-108">Create an interface in the programming language of your choice.</span></span>  
  
2. <span data-ttu-id="30e45-109">Примените атрибут <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="30e45-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
3. <span data-ttu-id="30e45-110">Примените атрибут <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который могут вызывать клиенты.</span><span class="sxs-lookup"><span data-stu-id="30e45-110">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to each method that clients can invoke.</span></span>  
  
4. <span data-ttu-id="30e45-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="30e45-111">Optional.</span></span> <span data-ttu-id="30e45-112">Установите свойство <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> в значение `true`, чтобы избежать отправки пустого ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="30e45-112">Set the value of the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true` to prevent the sending of an empty reply message.</span></span> <span data-ttu-id="30e45-113">По умолчанию все операции используют контракты «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="30e45-113">By default, all operations are request-reply contracts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30e45-114">Пример</span><span class="sxs-lookup"><span data-stu-id="30e45-114">Example</span></span>  

 <span data-ttu-id="30e45-115">В следующем примере определяется контракт для службы калькулятора, предоставляющей методы `Add` и `Subtract`.</span><span class="sxs-lookup"><span data-stu-id="30e45-115">The following sample defines a contract for a calculator service that provides `Add` and `Subtract` methods.</span></span> <span data-ttu-id="30e45-116">Метод `Multiply` не является частью контракта, поскольку он не отмечен классом <xref:System.ServiceModel.OperationContractAttribute>, а потому недоступен клиентам.</span><span class="sxs-lookup"><span data-stu-id="30e45-116">The `Multiply` method is not part of the contract because it is not marked by the <xref:System.ServiceModel.OperationContractAttribute> class and so it is not accessible to clients.</span></span>  
  
```csharp
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);

    [OperationContract]
    int Subtract(int a, int b);

    int Multiply(int a, int b)
}
```
  
- <span data-ttu-id="30e45-117">Дополнительные сведения об указании контрактов операций см. в разделе <xref:System.ServiceModel.OperationContractAttribute> класс и <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="30e45-117">For more information about how to specify operation contracts, see the <xref:System.ServiceModel.OperationContractAttribute> class and the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property.</span></span>  
  
- <span data-ttu-id="30e45-118">Применение атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> вызывает автоматическое создание определений контракта службы в документе WSDL после развертывания службы.</span><span class="sxs-lookup"><span data-stu-id="30e45-118">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes causes the automatic generation of service contract definitions in a Web Services Description Language (WSDL) document once the service is deployed.</span></span> <span data-ttu-id="30e45-119">Документ загружается путем добавления `?wsdl` к базовому адресу HTTP для службы,</span><span class="sxs-lookup"><span data-stu-id="30e45-119">The document is downloaded by appending `?wsdl` to the HTTP base address for the service.</span></span> <span data-ttu-id="30e45-120">например `http://microsoft/CalculatorService?wsdl`</span><span class="sxs-lookup"><span data-stu-id="30e45-120">For example, `http://microsoft/CalculatorService?wsdl`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e45-121">См. также</span><span class="sxs-lookup"><span data-stu-id="30e45-121">See also</span></span>

- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="30e45-122">Создание контрактов служб</span><span class="sxs-lookup"><span data-stu-id="30e45-122">Designing Service Contracts</span></span>](../designing-service-contracts.md)
- [<span data-ttu-id="30e45-123">Практическое руководство. Создание двухстороннего контракта</span><span class="sxs-lookup"><span data-stu-id="30e45-123">How to: Create a Duplex Contract</span></span>](how-to-create-a-duplex-contract.md)
