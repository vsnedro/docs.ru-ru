---
title: Другие структуры управления
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c6d80b237c7c3512c2904547842fdeb3c69bef68
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402022"
---
# <a name="other-control-structures-visual-basic"></a>Другие структуры управления (Visual Basic)
Visual Basic предоставляет управляющие структуры, которые помогают удалить ресурс или сократить количество повторных ссылок на объект.  
  
## <a name="usingend-using-construction"></a>Использование... Завершить с помощью конструкции  
 `Using...End Using`Конструкция устанавливает блок инструкций, в рамках которого используется ресурс, например соединение SQL. При необходимости можно получить ресурс с помощью `Using` инструкции. При выходе из `Using` блока Visual Basic автоматически уничтожает ресурс, чтобы он был доступен для использования другим кодом. Ресурс должен быть локальным и удаляемым. Дополнительные сведения см. в разделе [оператор using](../../../language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>С помощью... Завершить конструкцию  
 `With...End With`Конструкция позволяет указать ссылку на объект один раз, а затем выполнить последовательность инструкций, обращающихся к ее членам. Это может упростить код и повысить производительность, поскольку Visual Basic не придется повторно устанавливать ссылку для каждой инструкции, которая обращается к ней. Дополнительные сведения см [. в разделе with... Конец оператора](../../../language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>См. также раздел

- [Поток управления](index.md)
- [Структуры решений](decision-structures.md)
- [Циклические структуры](loop-structures.md)
- [Вложенные структуры управления](nested-control-structures.md)
- [Оператор using](../../../language-reference/statements/using-statement.md)
- [Оператор With…End With](../../../language-reference/statements/with-end-with-statement.md)
