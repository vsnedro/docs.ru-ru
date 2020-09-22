---
title: Процедура свойства let не определена, а процедура свойства get не вернула объект
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: fbeaa224ea9e095f86c37e571492d83bc98b4397
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871089"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>Процедура свойства let не определена, а процедура свойства get не вернула объект

Определенные свойства, методы и операции могут применяться только к `Collection` объектам. Вы указали операцию или свойство, которое является эксклюзивным для коллекций, но объект не является коллекцией.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Проверьте правильность написания имени объекта или свойства или убедитесь, что объект является `Collection` объектом.  
  
2. Взгляните на `Add` метод, используемый для добавления объекта в коллекцию, чтобы убедиться в правильности синтаксиса и правильности написания всех идентификаторов.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Collection>
