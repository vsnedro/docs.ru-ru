---
title: <type1>Тип <typename> должен реализовать <membername> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 4ffe18e11c388a8c69ef0592bde1b78f5b219680
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386858"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1>Тип \<typename> должен реализовать \<membername> для интерфейса \<interfacename>
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
