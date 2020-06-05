---
title: 'Невозможно завершить операцию: конечный каталог находится внутри исходного'
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 46ec7ae452d4f8259d0f8ca3a896d1b29151ed61
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376746"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Невозможно завершить операцию: конечный каталог находится внутри исходного
Циклическая операция не удалась. Циклические операции являются бесконечными циклами и поэтому не могут завершиться. Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- При наследовании убедитесь в отсутствии циклических ссылок.  
  
## <a name="see-also"></a>См. также раздел

- [Типы ошибок](../programming-guide/language-features/error-types.md)
- [Использование точек останова в отладчике Visual Studio](/visualstudio/debugger/using-breakpoints)
