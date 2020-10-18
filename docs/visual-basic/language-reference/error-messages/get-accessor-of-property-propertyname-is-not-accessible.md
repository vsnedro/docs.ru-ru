---
title: Метод доступа Get свойства <propertyname> недоступен
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: bd6830e16ba3d1f76c61519b4456832a2efec716
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162912"
---
# <a name="bc31103-get-accessor-of-property-propertyname-is-not-accessible"></a>BC31103: метод доступа get свойства " \<propertyname> " недоступен

Оператор пытается получить значение свойства, если оно не имеет доступа к `Get` процедуре свойства.

 Если [Инструкция Get](../statements/get-statement.md) помечена более ограниченным уровнем доступа, чем его [Инструкция Property](../statements/property-statement.md), попытка чтения значения свойства может завершиться ошибкой в следующих случаях:

- `Get`Инструкция помечена как [закрытая](../modifiers/private.md) , а вызывающий код находится за пределами класса или структуры, в которой определено свойство.

- `Get`Инструкция помечена как [protected](../modifiers/protected.md) и вызывающий код не находится в классе или структуре, в которой определено свойство, и в производном классе.

- `Get`Инструкция помечена как [Friend](../modifiers/friend.md) , а вызывающий код — не в той сборке, в которой определено свойство.

 **Идентификатор ошибки:** BC31103

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если вы управляете исходным кодом, определяющим свойство, попробуйте объявить `Get` процедуру с тем же уровнем доступа, что и само свойство.

- Если у вас нет контроля над исходным кодом, определяющим свойство, или необходимо ограничить `Get` уровень доступа к процедуре больше, чем само свойство, попробуйте переместить инструкцию, считывающую значение свойства, в область кода, имеющую Улучшенный доступ к свойству.

## <a name="see-also"></a>См. также

- [Процедуры свойств](../../programming-guide/language-features/procedures/property-procedures.md)
- [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
