---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: c5e8b8de3477147fc3174cdbee401c89753004ad
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159954"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Объект или класс не поддерживает набор событий

Предпринята попытка использовать `WithEvents` переменную с компонентом, который не может работать в качестве источника событий для указанного набора событий. Например, необходимо принять события объекта, а затем создать другой объект, который является `Implements` первым объектом. Хотя можно подумать о том, что вы можете передавать события из реализованного объекта, это не всегда так. `Implements` реализует интерфейс только для методов и свойств. `WithEvents` не поддерживается для Private `UserControls` , так как сведения о типе, необходимые для вызова, недоступны `ObjectEvent` во время выполнения.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Вы не можете заменять события для компонента, который не является источником событий.

## <a name="see-also"></a>См. также

- [WithEvents](../modifiers/withevents.md)
- [Оператор Implements](../statements/implements-statement.md)
