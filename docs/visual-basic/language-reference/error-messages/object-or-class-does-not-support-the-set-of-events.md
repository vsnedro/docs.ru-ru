---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: e55a5515d88bd2782e31fdea7c07e16c595d43b5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873658"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Объект или класс не поддерживает набор событий

Предпринята попытка использовать `WithEvents` переменную с компонентом, который не может работать в качестве источника событий для указанного набора событий. Например, необходимо принять события объекта, а затем создать другой объект, который является `Implements` первым объектом. Хотя можно подумать о том, что вы можете передавать события из реализованного объекта, это не всегда так. `Implements` реализует интерфейс только для методов и свойств. `WithEvents` не поддерживается для Private `UserControls` , так как сведения о типе, необходимые для вызова, недоступны `ObjectEvent` во время выполнения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Вы не можете заменять события для компонента, который не является источником событий.  
  
## <a name="see-also"></a>См. также

- [WithEvents](../modifiers/withevents.md)
- [Оператор Implements](../statements/implements-statement.md)
