---
title: Оператор Throw
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 95572b1739490e90f53da6b6ec283bfb532c46d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404139"
---
# <a name="throw-statement-visual-basic"></a>Оператор Throw (Visual Basic)

Создает исключение в процедуре.

## <a name="syntax"></a>Синтаксис

```vb
Throw [ expression ]
```

## <a name="part"></a>Часть

`expression`\
Предоставляет сведения о вызываемом исключении. Необязательно, если размещен в `Catch` операторе, в противном случае является обязательным.

## <a name="remarks"></a>Комментарии

`Throw`Оператор создает исключение, которое можно обработать с помощью структурированного кода обработки исключений ( `Try` ... `Catch` ...`Finally`) или неструктурированный код обработки исключений ( `On Error GoTo` ). Можно использовать `Throw` инструкцию для перехвата ошибок в коде, так как Visual Basic перемещается вверх по стеку вызовов до тех пор, пока не найдет соответствующий код обработки исключений.

`Throw`Инструкцию без выражения можно использовать только в `Catch` операторе, в этом случае инструкция повторно создает исключение, которое в настоящее время обрабатывается `Catch` инструкцией.

`Throw`Инструкция сбрасывает стек вызовов для `expression` исключения. Если `expression` параметр не указан, стек вызовов остается без изменений. Доступ к стеку вызовов для исключения можно получить с помощью <xref:System.Exception.StackTrace%2A> Свойства.

## <a name="example"></a>Пример

Следующий код использует `Throw` инструкцию для создания исключения:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>См. также раздел

- [Оператор Try…Catch…Finally](try-catch-finally-statement.md)
- [Оператор On Error](on-error-statement.md)
