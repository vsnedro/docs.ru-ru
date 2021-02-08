---
description: 'Дополнительные сведения о: объект или класс не поддерживает набор событий'
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: f13d47a6bb75a5e8394f5344b954afa523bedab3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795604"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Объект или класс не поддерживает набор событий

Предпринята попытка использовать `WithEvents` переменную с компонентом, который не может работать в качестве источника событий для указанного набора событий. Например, необходимо принять события объекта, а затем создать другой объект, который является `Implements` первым объектом. Хотя можно подумать о том, что вы можете передавать события из реализованного объекта, это не всегда так. `Implements` реализует интерфейс только для методов и свойств. `WithEvents` не поддерживается для Private `UserControls` , так как сведения о типе, необходимые для вызова, недоступны `ObjectEvent` во время выполнения.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Вы не можете заменять события для компонента, который не является источником событий.

## <a name="see-also"></a>См. также

- [WithEvents](../modifiers/withevents.md)
- [Оператор Implements](../statements/implements-statement.md)
