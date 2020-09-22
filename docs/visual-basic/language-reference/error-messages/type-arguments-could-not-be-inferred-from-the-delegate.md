---
title: Аргументы типа не могут быть выведены от делегата
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 51b0bbf2e346acdd84a1bc2283db4a71adc9f7dc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870425"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>Аргументы типа не могут быть выведены от делегата

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
