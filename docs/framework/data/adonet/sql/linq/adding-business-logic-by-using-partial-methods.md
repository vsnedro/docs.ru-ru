---
description: 'Дополнительные сведения: Добавление бизнес-логики с помощью разделяемых методов'
title: Добавление бизнес-логики с использованием разделяемых методов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: c34d0d25fa9dba074f1c7ff2abe2e9e24c931a8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672274"
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Добавление бизнес-логики с использованием разделяемых методов

Можно настроить Visual Basic и код, созданный C#, в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проектах с помощью *разделяемых методов*. Код, созданный [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], определяет сигнатуры как одну часть разделяемого метода. Если необходимо реализовать метод, можно добавить собственный разделяемый метод. Если собственная реализация не добавляется, компилятор отменяет сигнатуру разделяемых методов и вызывает в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] методы по умолчанию.  
  
> [!NOTE]
> При использовании Visual Studio можно использовать реляционный конструктор объектов для добавления проверки и других настроек в классы сущностей.  
  
 Например, применяемое по умолчанию сопоставление для класса `Customer` в образце базы данных Northwind включает следующий разделяемый метод:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 Можно реализовать собственный метод путем добавления кода, подобного представленному далее, в собственный разделяемый класс `Customer`.  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Этот подход обычно используется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для переопределения методов по умолчанию для `Insert` ,, и `Update` `Delete` для проверки свойств во время событий жизненного цикла объекта.  
  
 Дополнительные сведения см. в разделе [разделяемые методы](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) или [partial (метод) (Справочник по c#](../../../../../csharp/language-reference/keywords/partial-method.md) ) (c#).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  

 В примере кода `ExampleClass` сначала отображается так, как если бы он был определен с помощью средства создания кода, например SQLMetal, а затем так, как при реализации только одного из двух методов.  
  
### <a name="code"></a>Код  

 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  

 В следующем примере используется связь между сущностями `Shipper` и `Order`. Среди прочих методов обратите внимание на разделяемые - `InsertShipper` и `DeleteShipper`. Эти методы переопределяют разделяемые методы по умолчанию, предоставляемые [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставлением.  
  
### <a name="code"></a>Код  

 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Внесение и отправка изменений данных](making-and-submitting-data-changes.md)
- [Настройка операций вставки, обновления и удаления](customizing-insert-update-and-delete-operations.md)
