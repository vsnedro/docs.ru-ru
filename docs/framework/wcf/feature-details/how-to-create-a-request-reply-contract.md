---
description: Дополнительные сведения о том, как создать контракт Request-Reply.
title: Практическое руководство. Создание контракта типа "запрос — ответ"
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: f5e63538a405aa451ffd3be114485604c00fa407
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734702"
---
# <a name="how-to-create-a-request-reply-contract"></a>Практическое руководство. Создание контракта типа "запрос — ответ"

Контракт «запрос-ответ» указывает метод, который возвращает ответ. Необходима отправка ответа и его корреляция запросу согласно условиям этого контракта. Даже если метод не возвращает ответ (`void` в C# или `Sub` в Visual Basic), инфраструктура создает и отправляет вызывающему объекту пустое сообщение. Чтобы запретить отправку пустого ответного сообщения, используйте для операции односторонний контракт.  
  
### <a name="to-create-a-request-reply-contract"></a>Создание контракта типа запрос-ответ  
  
1. Создайте интерфейс на любом языке программирования.  
  
2. Примените атрибут <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.  
  
3. Примените атрибут <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который могут вызывать клиенты.  
  
4. Необязательный элемент. Установите свойство <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> в значение `true`, чтобы избежать отправки пустого ответного сообщения. По умолчанию все операции используют контракты «запрос-ответ».  
  
## <a name="example"></a>Пример  

 В следующем примере определяется контракт для службы калькулятора, предоставляющей методы `Add` и `Subtract`. Метод `Multiply` не является частью контракта, поскольку он не отмечен классом <xref:System.ServiceModel.OperationContractAttribute>, а потому недоступен клиентам.  
  
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
  
- Дополнительные сведения об указании контрактов операций см. в разделе <xref:System.ServiceModel.OperationContractAttribute> класс и <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> свойство.  
  
- Применение атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> вызывает автоматическое создание определений контракта службы в документе WSDL после развертывания службы. Документ загружается путем добавления `?wsdl` к базовому адресу HTTP для службы, Например: `http://microsoft/CalculatorService?wsdl`  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.OperationContractAttribute>
- [Создание контрактов служб](../designing-service-contracts.md)
- [Практическое руководство. Создание двухстороннего контракта](how-to-create-a-duplex-contract.md)
