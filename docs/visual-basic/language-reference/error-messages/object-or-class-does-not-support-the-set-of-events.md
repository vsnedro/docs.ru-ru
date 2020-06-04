---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: bc75e031c2d05bea3aa64774a9d3817756e51e8b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409365"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Объект или класс не поддерживает набор событий
Предпринята попытка использовать `WithEvents` переменную с компонентом, который не может работать в качестве источника событий для указанного набора событий. Например, необходимо принять события объекта, а затем создать другой объект, который является `Implements` первым объектом. Хотя можно подумать о том, что вы можете передавать события из реализованного объекта, это не всегда так. `Implements`реализует интерфейс только для методов и свойств. `WithEvents`не поддерживается для Private `UserControls` , так как сведения о типе, необходимые для вызова, недоступны `ObjectEvent` во время выполнения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Вы не можете заменять события для компонента, который не является источником событий.  
  
## <a name="see-also"></a>См. также раздел

- [WithEvents](../modifiers/withevents.md)
- [Оператор Implements](../statements/implements-statement.md)
