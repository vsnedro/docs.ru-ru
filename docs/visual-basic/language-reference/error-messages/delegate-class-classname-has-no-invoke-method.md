---
description: 'Дополнительные сведения о: BC30220: класс делегата " <classname> " не имеет метода Invoke, поэтому выражение этого типа не может быть целевым объектом вызова метода'
title: В делегируемом классе <classname> отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: c0d3f6e352a98e194b2c2ddca04bfa7254ec37a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796630"
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
