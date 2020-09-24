---
title: Вычисление суммы значений в числовой последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: 3d160e2cce5f3e0a7eea305657260b6fa4ded7fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164445"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a>Вычисление суммы значений в числовой последовательности

Для вычисления суммы значений в последовательности чисел используется оператор <xref:System.Linq.Enumerable.Sum%2A>.  
  
 Обратите внимание на следующие характеристики оператора `Sum` в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
- Для пустой последовательности или последовательности, содержащей только значения NULL, значением агрегатного оператора стандартного оператора запроса `Sum` является ноль. В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] семантики SQL остаются неизменными. Поэтому для пустой последовательности или последовательности, содержащей только значения NULL, значением`Sum` является NULL.  
  
- Ограничения SQL для промежуточных результатов применяются к агрегатным выражениям в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Сумма 32-разрядных целых чисел не вычисляется с помощью 64-разрядных результатов, а переполнение может произойти для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] перевода `Sum` . Такая возможность существует, даже если реализация стандартного оператора запроса не вызывает переполнения для соответствующей последовательности в памяти.  
  
## <a name="example"></a>Пример  

 В следующем примере вычисляется общая стоимость доставки всех заказов в таблице `Order`.  
  
 Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `64942.6900`.  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a>Пример  

 В следующем примере вычисляется общее число заказанных элементов для всех продуктов.  
  
 Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `780`.  
  
 Обратите внимание на необходимость приведения типов `short` (например, `UnitsOnOrder`), поскольку `Sum` не имеет перегрузки для коротких типов.  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a>См. также раздел

- [Статистические запросы](aggregate-queries.md)
- [Загрузка примеров баз данных](downloading-sample-databases.md)
