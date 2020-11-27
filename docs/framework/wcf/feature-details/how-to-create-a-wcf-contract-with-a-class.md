---
title: Практическое руководство. Создание контракта Windows Communication Foundation с помощью класса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: f2164b4f4c997de764139a7a0a2aecbf91616458
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286244"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Практическое руководство. Создание контракта Windows Communication Foundation с помощью класса

Предпочтительный способ создания контракта Windows Communication Foundation (WCF) — использование интерфейса. Дополнительные сведения см. [в разделе инструкции. определение контракта службы](../how-to-define-a-wcf-service-contract.md). Описанный здесь альтернативный способ предполагает создание класса и последующее применение атрибута <xref:System.ServiceModel.ServiceContractAttribute> непосредственно к классу, а атрибута <xref:System.ServiceModel.OperationContractAttribute> к каждому из методов класса, являющихся частью контракта.  
  
> [!WARNING]
> `[ServiceContract]` и `[ServiceContractAttribute]` выполняют то же самое. То же самое касается `[OperationContract]` и `[OperationContractAttribute]` . В каждом случае первый из них является сокращением для второго.  
  
 Дополнительные сведения о контрактах служб см. в разделе [Разработка контрактов служб](../designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Создание контракта Windows Communication Foundation с помощью класса  
  
1. Создайте новый класс, используя Visual Basic, C# или любой другой язык среды CLR.  
  
2. Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к созданному классу.  
  
3. Создайте методы класса.  
  
4. Примените <xref:System.ServiceModel.OperationContractAttribute> класс к каждому методу, который должен быть предоставлен как часть общедоступного контракта WCF.  
  
## <a name="example"></a>Пример  

 В следующем примере кода показан класс, определяющий контракт службы.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ». Дополнительные сведения об этом шаблоне сообщений см. [в разделе инструкции. создание Request-Reply контракта](how-to-create-a-request-reply-contract.md). Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута. Дополнительные примеры см. в разделе [как создать One-Wayный контракт](how-to-create-a-one-way-contract.md) и [как создать дуплексный контракт](how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
