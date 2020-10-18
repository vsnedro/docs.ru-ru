---
title: Аргументы типа не могут быть выведены от делегата
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: f7937a34ab425da684f892250884d21e020e4c57
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161248"
---
# <a name="bc36564-type-arguments-could-not-be-inferred-from-the-delegate"></a>BC36564: аргументы типа не могут быть выведены из делегата

Оператор назначения использует `AddressOf` для назначения делегату адреса универсальной процедуры, но он не предоставляет универсальной процедуре никакие аргументы типа.

 Как правило, при вызове универсального типа указывается аргумент типа для каждого параметра типа, определяемого этим универсальным типом. Если вы не предоставляете никакие аргументы типов, компилятор пытается вывести типы, которые должны быть переданы в параметры типов. Если контекст не предоставляет достаточно сведений, чтобы компилятор мог вывести типы, возникает ошибка.

 **Идентификатор ошибки:** BC36564

## <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите аргументы типа для универсальной процедуры в выражении `AddressOf` .

## <a name="see-also"></a>См. также

- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Оператор AddressOf](../operators/addressof-operator.md)
- [Generic Procedures in Visual Basic](../../programming-guide/language-features/data-types/generic-procedures.md)
- [Type List](../statements/type-list.md)
- [Методы расширения](../../programming-guide/language-features/procedures/extension-methods.md)
