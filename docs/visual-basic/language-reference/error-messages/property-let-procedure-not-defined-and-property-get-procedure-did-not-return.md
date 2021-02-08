---
description: 'Дополнительные сведения: процедура Let для свойства не определена, а процедура Get свойства не возвращает объект.'
title: Процедура свойства let не определена, а процедура свойства get не вернула объект
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: 8376a30abb476abb1d45973e36eb086cadad0054
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795369"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>Процедура свойства let не определена, а процедура свойства get не вернула объект

Определенные свойства, методы и операции могут применяться только к `Collection` объектам. Вы указали операцию или свойство, которое является эксклюзивным для коллекций, но объект не является коллекцией.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Проверьте правильность написания имени объекта или свойства или убедитесь, что объект является `Collection` объектом.  
  
2. Взгляните на `Add` метод, используемый для добавления объекта в коллекцию, чтобы убедиться в правильности синтаксиса и правильности написания всех идентификаторов.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Collection>
