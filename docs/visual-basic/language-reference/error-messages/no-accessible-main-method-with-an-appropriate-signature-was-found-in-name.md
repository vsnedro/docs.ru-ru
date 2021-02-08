---
description: 'Дополнительные сведения о: BC30737: не удалось найти доступный метод "Main" с подходящей сигнатурой в "<name>'
title: В <name> не найдено доступного метода Main с подходящей подписью
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 1865d6baea824c435d276aa9c160bcd282abf4ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795655"
---
# <a name="bc30737-no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>BC30737: в "" не найден доступный метод "Main" с подходящей сигнатурой. \<name>

Приложения командной строки должны иметь `Sub Main` определенные. `Main` должен быть объявлен как `Public Shared` , если он определен в классе, или как, `Public` если он определен в модуле.

 **Идентификатор ошибки:** BC30737

## <a name="to-correct-this-error"></a>Исправление ошибки

- Определите `Public Sub Main` процедуру для проекта. Объявите его как `Shared` If и только в том случае, если оно определено внутри класса.

## <a name="see-also"></a>См. также

- [Структура программы Visual Basic](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
