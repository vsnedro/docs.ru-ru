---
title: Практическое руководство. Создание базового контракта данных для класса или структуры
description: Выполните приведенный ниже пример, чтобы узнать, как создать контракт данных с помощью класса или структуры в WCF с помощью атрибута DataContractAttribute.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: a45fde58795947c3e46fa45750ae1a3faddd8849
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247173"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a>Практическое руководство. Создание базового контракта данных для класса или структуры
В этом разделе приведены основные этапы создания контракта данных с использованием класса или структуры. Дополнительные сведения о контрактах данных и их использовании см. в разделе [использование контрактов данных](using-data-contracts.md).  
  
 Инструкции по созданию службы Basic Windows Communication Foundation (WCF) и клиента см. в [руководстве по начало работы](../getting-started-tutorial.md). Рабочий пример приложения, состоящего из базовой службы и клиента, см. в разделе [базовый контракт данных](../samples/basic-data-contract.md).  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a>Создание базового контракта данных для класса или структуры  
  
1. Объявите, что типы имеют контракт данных, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу. Обратите внимание, что все открытые типы, включая типы без атрибутов, сериализуемы. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных при отсутствии атрибута <xref:System.Runtime.Serialization.DataContractAttribute>. Дополнительные сведения см. в разделе [сериализуемые типы](serializable-types.md).  
  
2. Определите члены (свойства, поля или события), сериализуемые путем применения атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> к каждому члену. Эти члены называются членами данных. По умолчанию все открытые типы сериализуемы. Дополнительные сведения см. в разделе [сериализуемые типы](serializable-types.md).  
  
    > [!NOTE]
    > Можно применить атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к закрытым полям, в результате чего данные будут предоставлены другим пользователям. Убедитесь, что член не содержит конфиденциальных данных.  
  
## <a name="example"></a>Пример  
 В следующем примере показано создание контракта данных для типа `Person` путем применения атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> к классу и его членам.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Использование контрактов данных](using-data-contracts.md)
- [Учебник по начало работы](../getting-started-tutorial.md)
- [Начало работы](../samples/getting-started-sample.md)
