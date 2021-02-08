---
description: 'Дополнительные сведения: оператор AddressOf (Visual Basic)'
title: Оператор AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 2aba8c26aa9581fe1070574b8c408e09bf063d1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774386"
---
# <a name="addressof-operator-visual-basic"></a>Оператор AddressOf (Visual Basic)

Создает экземпляр делегата, который ссылается на определенную процедуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Компоненты  

 `procedurename`  
 Обязательный элемент. Задает процедуру, на которую ссылается только что созданный делегат.  
  
## <a name="remarks"></a>Remarks  

 `AddressOf`Оператор создает делегат, указывающий на подпрограмму или функцию, заданную параметром `procedurename` . Если указанная процедура является методом экземпляра, то делегат ссылается на экземпляр и метод. Затем при вызове делегата вызывается указанный метод указанного экземпляра.  
  
 `AddressOf`Оператор можно использовать в качестве операнда конструктора делегата или его можно использовать в контексте, в котором тип делегата может быть определен компилятором.  
  
## <a name="example"></a>Пример  

 В этом примере `AddressOf` оператор используется для обозначения делегата, обрабатывающего `Click` событие кнопки.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `AddressOf` для назначения функции Startup для потока.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Declare Statement](../statements/declare-statement.md)
- [Оператор Function](../statements/function-statement.md)
- [Оператор Sub](../statements/sub-statement.md)
- [Делегаты](../../programming-guide/language-features/delegates/index.md)
