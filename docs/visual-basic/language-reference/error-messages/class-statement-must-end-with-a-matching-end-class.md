---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 6889e97aad913f6911ce438892752542de0d10f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163198"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a>BC30481: оператор Class должен заканчиваться соответствующим оператором End Class

`Class` используется для запуска `Class` блока, поэтому он может находиться только в начале блока, при этом `End Class` блоку соответствует оператор сопоставления. Либо имеется избыточный `Class` оператор, либо вы не закончили `Class` блок с помощью `End Class` .

 **Идентификатор ошибки:** BC30481

## <a name="to-correct-this-error"></a>Исправление ошибки

- Найдите и удалите ненужный оператор `Class` .

- Заключение `Class` блока с соответствующим `End Class` .

## <a name="see-also"></a>См. также

- [End, \<keyword> Инструкция](../statements/end-keyword-statement.md)
- [Оператор Class](../statements/class-statement.md)
