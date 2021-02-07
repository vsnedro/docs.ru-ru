---
description: 'Дополнительные сведения о инструкции: Throw (Visual Basic)'
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
ms.openlocfilehash: b7fa4183b5997e5dac8045502a8eed1afe66fc0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740942"
---
# <a name="throw-statement-visual-basic"></a>Оператор Throw (Visual Basic)

Создает исключение в процедуре.

## <a name="syntax"></a>Синтаксис

```vb
Throw [ expression ]
```

## <a name="part"></a>Отделение

`expression`\
Предоставляет сведения о вызываемом исключении. Необязательно, если размещен в `Catch` операторе, в противном случае является обязательным.

## <a name="remarks"></a>Remarks

`Throw`Оператор создает исключение, которое можно обработать с помощью структурированного кода обработки исключений ( `Try` ... `Catch` ...`Finally`) или неструктурированный код обработки исключений ( `On Error GoTo` ). Можно использовать `Throw` инструкцию для перехвата ошибок в коде, так как Visual Basic перемещается вверх по стеку вызовов до тех пор, пока не найдет соответствующий код обработки исключений.

`Throw`Инструкцию без выражения можно использовать только в `Catch` операторе, в этом случае инструкция повторно создает исключение, которое в настоящее время обрабатывается `Catch` инструкцией.

`Throw`Инструкция сбрасывает стек вызовов для `expression` исключения. Если `expression` параметр не указан, стек вызовов остается без изменений. Доступ к стеку вызовов для исключения можно получить с помощью <xref:System.Exception.StackTrace%2A> Свойства.

## <a name="example"></a>Пример

Следующий код использует `Throw` инструкцию для создания исключения:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>См. также раздел

- [Оператор Try...Catch...Finally](try-catch-finally-statement.md)
- [Оператор On Error](on-error-statement.md)
