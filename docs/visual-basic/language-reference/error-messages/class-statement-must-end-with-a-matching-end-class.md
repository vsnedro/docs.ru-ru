---
description: 'Дополнительные сведения о: BC30481: оператор Class должен заканчиваться соответствующим оператором End'
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: b0d2d89e9e3549b24f9c923e271b15b3b02026b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796785"
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
