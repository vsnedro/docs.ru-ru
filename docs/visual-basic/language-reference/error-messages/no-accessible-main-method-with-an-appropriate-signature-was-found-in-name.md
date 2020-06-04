---
title: В <name> не найдено доступного метода Main с подходящей подписью
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6760b931ceb2ad5c2c04169d664da8629badc487
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409417"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>В \<name> не найдено доступного метода Main с подходящей подписью
Приложения командной строки должны иметь `Sub Main` определенные. `Main`должен быть объявлен как `Public Shared` , если он определен в классе, или как, `Public` если он определен в модуле.  
  
 **Идентификатор ошибки:** BC30737  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Определите `Public Sub Main` процедуру для проекта. Объявите его как `Shared` If и только в том случае, если оно определено внутри класса.  
  
## <a name="see-also"></a>См. также раздел

- [Структура программы Visual Basic](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Процедуры](../../programming-guide/language-features/procedures/index.md)
