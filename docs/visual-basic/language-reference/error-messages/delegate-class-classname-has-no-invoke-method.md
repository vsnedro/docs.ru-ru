---
title: В делегируемом классе <classname> отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 4e0fc61c7356008755134f670fa1fab0165cfd48
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162795"
---
# <a name="bc30220-delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>BC30220: класс делегата " \<classname> " не имеет метода Invoke, поэтому выражение этого типа не может быть целевым объектом вызова метода

Вызов `Invoke` через делегат завершился неудачей, поскольку `Invoke` не реализован в классе делегата.

 **Идентификатор ошибки:** BC30220

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что экземпляр класса делегата был создан с помощью `Dim` оператора и что процедура была назначена экземпляру делегата с помощью `AddressOf` оператора.

2. Выберите код, реализующий класс делегата, и убедитесь, что он реализует `Invoke` процедуру.

## <a name="see-also"></a>См. также

- [Делегаты](../../programming-guide/language-features/delegates/index.md)
- [Оператор Delegate](../statements/delegate-statement.md)
- [Оператор AddressOf](../operators/addressof-operator.md)
- [Оператор Dim](../statements/dim-statement.md)
