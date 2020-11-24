---
title: Взаимодействие исключений
ms.date: 01/16/2020
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: db7c9943c298607aa91a4bd08ddc12bbafc872be
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830627"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Работа с исключениями взаимодействия в неуправляемом коде

Взаимодействие исключений неуправляемого кода поддерживается только на платформах Windows. На других платформах возникают проблемы переносимости. Поскольку в ABI для UNIX нет определения для обработки исключений, управляемый код не может понять, как работают механизмы исключений. Таким образом, исключения могут приводить к непредсказуемым поведению и сбоям.

## <a name="setjmplongjmp-behaviors"></a>Поведение setjmp/longjmp

Взаимодействие с функциями C `setjmp` и `longjmp` не поддерживается. Нельзя использовать `longjmp` для пропуска управляемых кадров.

Дополнительные сведения см. в [документации по longjmp](/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>См. также

- [Исключения](index.md)
- [Взаимодействие с собственными библиотеками](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
