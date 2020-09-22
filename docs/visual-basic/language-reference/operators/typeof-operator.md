---
title: Оператор TypeOf
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 0a01b49cf1e0bf9ad7b2ce541cee39cba83025ca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875300"
---
# <a name="typeof-operator-visual-basic"></a>Оператор TypeOf (Visual Basic)

Проверяет, совместим ли тип среды выполнения результата выражения с указанным типом.
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Компоненты  

 `result`  
 Возвращено. Значение `Boolean`.  
  
 `objectexpression`  
 Обязательный элемент. Любое выражение, результатом которого является тип ссылки.  
  
 `typename`  
 Обязательный элемент. Любое имя типа данных.  
  
## <a name="remarks"></a>Remarks  

 Оператор `TypeOf` определяет, совместим ли тип времени выполнения `objectexpression` с `typename`. Совместимость зависит от категории типа `typename`. В следующей таблице показано, как определяется совместимость.  
  
|Категория типа `typename`|Критерий совместимости|  
|---------------------------------|-----------------------------|  
|Класс|`objectexpression` типа `typename` или наследует от `typename`|  
|structure|`objectexpression` типа `typename`|  
|Интерфейс|`objectexpression` реализует `typename` или наследует от класса, реализующего `typename`|  
  
 Если тип времени выполнения `objectexpression` удовлетворяет критерию совместимости, `result` является `True`. В противном случае `result` является `False`.  Если `objectexpression` имеет значение null, то `TypeOf`...`Is` возвращает `False`, а ...`IsNot` возвращает `True`.  
  
 `TypeOf` всегда используется с ключевым словом `Is` для создания выражения `TypeOf`...`Is` или с ключевым словом `IsNot` для создания выражения `TypeOf`...`IsNot`.  
  
## <a name="example"></a>Пример  

 В следующем примере выражение `TypeOf`...`Is` используется для проверки на совместимость типов двух переменных ссылок на объекты с различными типами данных.  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 Переменная `refInteger` имеет тип времени выполнения `Integer`. Она совместима с `Integer`, но не с `Double`. Переменная `refForm` имеет тип времени выполнения <xref:System.Windows.Forms.Form>. Она совместима с <xref:System.Windows.Forms.Form>, так как это ее тип, с <xref:System.Windows.Forms.Control>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.Windows.Forms.Control>, и с <xref:System.ComponentModel.IComponent>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.ComponentModel.Component>, который реализует <xref:System.ComponentModel.IComponent>. Однако `refForm` несовместима с <xref:System.Windows.Forms.Label>.  
  
## <a name="see-also"></a>См. также

- [Оператор Is](is-operator.md)
- [Оператор IsNot](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы и выражения](../../programming-guide/language-features/operators-and-expressions/index.md)
