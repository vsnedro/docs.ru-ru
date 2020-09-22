---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: d67f0e71dbdbf97420ec5b5ba4b6f06acfba1bd9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874620"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>Оператор Class должен заканчиваться соответствующим End Class

`Class` используется для запуска `Class` блока, поэтому он может находиться только в начале блока, при этом `End Class` блоку соответствует оператор сопоставления. Либо имеется избыточный `Class` оператор, либо вы не закончили `Class` блок с помощью `End Class` .  
  
 **Идентификатор ошибки:** BC30481  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Найдите и удалите ненужный оператор `Class` .  
  
- Заключение `Class` блока с соответствующим `End Class` .  
  
## <a name="see-also"></a>См. также

- [End, \<keyword> Инструкция](../statements/end-keyword-statement.md)
- [Оператор Class](../statements/class-statement.md)
