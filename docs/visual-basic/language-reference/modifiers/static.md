---
title: Статические
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 2b7113424969b0b18c981b0c8932aeef3795ca4a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867677"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)

Указывает, что одна или несколько объявленных локальных переменных должны продолжать существовать и сохранить их последние значения после завершения процедуры, в которой они объявляются.  
  
## <a name="remarks"></a>Remarks  

 Как правило, локальная переменная в процедуре прекращает свое существование сразу после остановки процедуры. Статическая переменная продолжает существовать и сохраняет ее Последнее значение. В следующий раз, когда код вызывает процедуру, переменная не инициализируется повторно, и она по-прежнему содержит Последнее назначенное ей значение. Статическая переменная будет существовать в течение времени существования класса или модуля, в котором он определен.  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** Можно использовать `Static` только для локальных переменных. Это означает, что контекст объявления для `Static` переменной должен быть процедурой или блоком в процедуре и не может быть исходным файлом, пространством имен, классом, структурой или модулем.  
  
     Нельзя использовать `Static` внутри процедуры структуры.  
  
- Типы данных `Static` локальных переменных не могут быть определены. Дополнительные сведения см. в разделе [определение локального типа](../../programming-guide/language-features/variables/local-type-inference.md).  
  
- **Комбинированные модификаторы.** Нельзя указывать `Static` вместе с `ReadOnly` , `Shadows` или `Shared` в одном объявлении.  
  
## <a name="behavior"></a>Поведение  

 При объявлении статической переменной в `Shared` процедуре для всего приложения доступна только одна копия статической переменной. Процедура вызывается с `Shared` помощью имени класса, а не переменной, указывающей на экземпляр класса.  
  
 При объявлении статической переменной в процедуре, которая не `Shared` имеет, для каждого экземпляра класса доступна только одна копия переменной. Для вызова процедуры, которая не является общей, используется переменная, указывающая на конкретный экземпляр класса.  
  
## <a name="example"></a>Пример  

 В следующем примере показано использование функции `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 `Static`Переменная `totalSales` инициализируется значением 0 только один раз. При каждом вводе `updateSales` `totalSales` по-прежнему будет присвоено самое последнее значение, вычисленное для него.  
  
 `Static`Модификатор можно использовать в этом контексте:  
  
 [Оператор Dim](../statements/dim-statement.md)  
  
## <a name="see-also"></a>См. также

- [Shadows](shadows.md)
- [Общий](shared.md)
- [Время существования в Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md)
- [Объявление переменной](../../programming-guide/language-features/variables/variable-declaration.md)
- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Вывод локального типа](../../programming-guide/language-features/variables/local-type-inference.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
