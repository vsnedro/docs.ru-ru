---
title: <type1>Тип <typename> должен реализовать <membername> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a036097d778daae59ef3bbd74ab8507cd16e6e24
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161859"
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

## <a name="see-also"></a>См. также

- [Оператор Implements](../statements/implements-statement.md)
- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
