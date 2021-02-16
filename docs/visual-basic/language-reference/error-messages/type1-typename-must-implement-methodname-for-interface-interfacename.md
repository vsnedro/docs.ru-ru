---
description: 'Дополнительные сведения о: BC30149: <type1> " <typename> " должен реализовывать " <methodname> " для интерфейса " <interfacename> "'
title: <type1>Тип <typename> должен реализовать <methodname> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: b2fb7f5ea019a86b18ea89456e353778e5246d2d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100473441"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a>BC30149: \<type1> " \<typename> " должен реализовывать " \<methodname> " для интерфейса " \<interfacename> "

Класс или структура требует реализации интерфейса, но не реализует процедуру, определенную интерфейсом. Каждый член интерфейса должен быть реализован.

 **Идентификатор ошибки:** BC30149

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Объявите процедуру с тем же именем и сигнатурой, как определено в интерфейсе. Обязательно включите по крайней мере `End Function` оператор или `End Sub` .

2. Добавьте `Implements` предложение в конец `Function` `Sub` оператора или. Пример:

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a>См. также раздел

- [Оператор Implements](../statements/implements-statement.md)
- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
