---
title: Формулировка проекций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f0bc6dfcff7778ebc7156cbb039e13570c90467b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194405"
---
# <a name="formulate-projections"></a>Формулировка проекций

В следующих примерах показано, как `select` инструкция в C# и `Select` инструкции в Visual Basic можно сочетать с другими функциями для формирования проекций запросов.  
  
## <a name="example"></a>Пример  

 В следующем примере `Select` предложение в Visual Basic ( `select` предложение в C#) используется для возврата последовательности имен контактов для `Customers` .  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Пример  

 В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *анонимные типы* для возврата последовательности имен контактов и телефонных номеров для `Customers` .  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Пример  

 В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *анонимные типы* для возврата последовательности имен и телефонных номеров сотрудникам. `FirstName`Поля и `LastName` объединяются в одно поле ( `Name` ), а `HomePhone` поле переименовывается в `Phone` результирующую последовательность.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Пример  

 В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *анонимные типы* для возврата последовательности всех объектов `ProductID` и вычисляемого значения с именем `HalfPrice` . В качестве значения устанавливается `UnitPrice`, разделенная на 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Пример  

 В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *Условный оператор* для возврата последовательности названия продукта и доступности продукта.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Пример  

 В следующем примере используется предложение Visual Basic `Select` ( `select` предложение в C#) и *известный тип* (Name) для возврата последовательности имен сотрудников.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Пример  

 В следующем примере с помощью `Select` и `Where` в Visual Basic ( `select` и `where` в C#) возвращается *отфильтрованная последовательность* имен контактов для клиентов в Лондоне.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Пример  

 В следующем примере предложение используется `Select` в Visual Basic ( `select` предложение в C#) и *анонимные типы* для возврата в *форме подмножества* данных о клиентах.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Пример  

 В следующем примере вложенные запросы используется для возврата следующих результатов.  
  
- Последовательность всех заказов и их соответствующие `OrderID`.  
  
- Последовательность элементов, упорядоченных по наличию скидки.  
  
- Количество сэкономленных средств при отсутствии расходов на доставку.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>См. также раздел

- [Примеры запросов](query-examples.md)
