---
description: 'Дополнительные сведения о: BC30154: <type1> " <typename> " должен реализовывать " <membername> " для интерфейса " <interfacename> "'
title: <type1>Тип <typename> должен реализовать <membername> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: fc0cf8544984ddf41f1f91cb0bca90b630d9614d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100473567"
---
# <a name="bc30154-type1typename-must-implement-membername-for-interface-interfacename"></a>BC30154: \<type1> " \<typename> " должен реализовывать " \<membername> " для интерфейса " \<interfacename> "

" \<typename> " должен реализовывать " \<membername> " для интерфейса " \<interfacename> ". Реализация свойства должна иметь соответствующие описатели "ReadOnly"/"WriteOnly".

 Класс или структура объявляет о необходимости реализации интерфейса, но не реализует процедуру, свойство или событие, определенные интерфейсом. Каждый член интерфейса должен быть реализован.

 **Идентификатор ошибки:** BC30154

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Объявите член с таким же именем и сигнатурой, как определено в интерфейсе. Обязательно включите по крайней мере `End Function` оператор, `End Sub` или `End Property` .

2. Добавьте `Implements` предложение в конец `Function` оператора,, `Sub` `Property` или `Event` . Пример:

    ```vb
    Public Event ItHappened() Implements IBaseInterface.ItHappened
    ```

3. При реализации свойства убедитесь, что `ReadOnly` или используется так `WriteOnly` же, как и в определении интерфейса.

4. При реализации свойства, объявите `Get` и `Set` процедуры, если это уместно.

## <a name="see-also"></a>См. также раздел

- [Оператор Implements](../statements/implements-statement.md)
- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
