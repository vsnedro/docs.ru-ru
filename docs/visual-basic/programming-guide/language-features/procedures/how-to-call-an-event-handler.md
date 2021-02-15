---
description: Дополнительные сведения о том, как вызвать обработчик событий в Visual Basic
title: Вызов обработчика событий
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
no-loc:
- WithEvents
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 7e65b36d392211be533bb4881658b1cdb8057d5d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476258"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Вызов обработчика событий в Visual Basic

*Событие* — это действие или ситуация (например, превышение щелчка мыши или предела кредита), которые распознаются некоторым компонентом программы и для которых можно написать код для ответа. *Обработчик событий* — это код, который вы пишете для реагирования на событие.

Обработчик событий в Visual Basic является `Sub` процедурой. Однако обычно он не вызывается так же, как другие `Sub` процедуры. Вместо этого вы определяете процедуру как обработчик для события. Это можно сделать с помощью [`Handles`](../../../language-reference/statements/handles-clause.md) предложения и [`WithEvents`](../../../language-reference/modifiers/withevents.md) переменной или с помощью [оператора AddHandler](../../../language-reference/statements/addhandler-statement.md). Использование `Handles` предложения по умолчанию является способом объявления обработчика событий в Visual Basic. Это способ, которым обработчики событий пишутся конструкторами при программировании в интегрированной среде разработки (IDE). `AddHandler`Оператор подходит для динамического вызова событий во время выполнения.

Когда происходит событие, Visual Basic автоматически вызывает процедуру обработчика событий. Любой код, имеющий доступ к событию, может привести к его возникновению, выполнив [оператор RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).

Можно связать более одного обработчика событий с одним и тем же событием. В некоторых случаях можно отменить связь обработчика с событием. Дополнительные сведения см. в статье [Events (Visual Basic)](../events/index.md) (События в Visual Basic).

## <a name="call-an-event-handler-using-no-loc-texthandles-and-withevents"></a>Вызовите обработчик событий с помощью :::no-loc text="Handles"::: и WithEvents

1. Убедитесь, что событие объявлено с помощью [оператора Event](../../../language-reference/statements/event-statement.md).

2. Объявите переменную объекта на уровне модуля или класса с помощью [`WithEvents`](../../../language-reference/modifiers/withevents.md) ключевого слова. `As`Предложение для этой переменной должно указывать класс, который вызывает событие.

3. В объявлении процедуры обработки событий `Sub` добавьте [`Handles`](../../../language-reference/statements/handles-clause.md) предложение, указывающее `WithEvents` переменную и имя события.

4. Когда происходит событие, Visual Basic автоматически вызывает `Sub` процедуру. В коде можно использовать `RaiseEvent` инструкцию для выполнения события.

    В следующем примере определяется событие и `WithEvents` переменная, которая ссылается на класс, который вызывает событие. Процедура обработки событий `Sub` использует `Handles` предложение для указания класса и события, которые он обрабатывает.

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="4":::

## <a name="call-an-event-handler-using-addhandler"></a>Вызов обработчика событий с помощью AddHandler

1. Убедитесь, что событие объявлено с помощью `Event` оператора.

2. Выполните [оператор AddHandler](../../../language-reference/statements/addhandler-statement.md) , чтобы динамически подключить процедуру обработки событий `Sub` с событием.

3. Когда происходит событие, Visual Basic автоматически вызывает `Sub` процедуру. В коде можно использовать `RaiseEvent` инструкцию для выполнения события.

    В следующем примере используется [оператор AddHandler](../../../language-reference/statements/addhandler-statement.md) в конструкторе, чтобы связать `OnFormClosing` процедуру как обработчик событий для <xref:System.Windows.Forms.Form.FormClosing> .

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="5":::

    Можно отменить связь между обработчиком событий и событием, выполнив [оператор RemoveHandler](../../../language-reference/statements/removehandler-statement.md).

## <a name="see-also"></a>См. также раздел

- [Процедуры](index.md)
- [Подпрограммы](sub-procedures.md)
- [Оператор Sub](../../../language-reference/statements/sub-statement.md)
- [Оператор AddressOf](../../../language-reference/operators/addressof-operator.md)
- [Практическое руководство. Создание процедуры](how-to-create-a-procedure.md)
- [Практическое руководство. Вызов процедуры, которая не возвращает значение](how-to-call-a-procedure-that-does-not-return-a-value.md)
