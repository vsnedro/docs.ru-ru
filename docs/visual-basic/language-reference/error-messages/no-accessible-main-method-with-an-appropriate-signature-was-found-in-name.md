---
title: В <name> не найдено доступного метода Main с подходящей подписью
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: e1f95484a153bdcac9543508b7f2708dc6b7d942
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160045"
---
# <a name="bc30737-no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>BC30737: в "" не найден доступный метод "Main" с подходящей сигнатурой. \<name>

Приложения командной строки должны иметь `Sub Main` определенные. `Main` должен быть объявлен как `Public Shared` , если он определен в классе, или как, `Public` если он определен в модуле.

 **Идентификатор ошибки:** BC30737

## <a name="to-correct-this-error"></a>Исправление ошибки

- Определите `Public Sub Main` процедуру для проекта. Объявите его как `Shared` If и только в том случае, если оно определено внутри класса.

## <a name="see-also"></a>См. также

- [Структура программы Visual Basic](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
