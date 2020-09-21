---
title: Взаимодействие исключений
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 90774b5d1b64feb34e01f48708d94f8f841a7c9d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550876"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Работа с исключениями взаимодействия в неуправляемом коде

Взаимодействие исключений неуправляемого кода поддерживается только на платформах Windows. На других платформах возникают проблемы переносимости. Поскольку в ABI для UNIX нет определения для обработки исключений, управляемый код не может понять, как работают механизмы исключений. Таким образом, исключения могут приводить к непредсказуемым поведению и сбоям.

## <a name="setjmplongjmp-behaviors"></a>Поведение setjmp/longjmp

Взаимодействие с функциями C `setjmp` и `longjmp` не поддерживается. Нельзя использовать `longjmp` для пропуска управляемых кадров.

Дополнительные сведения см. в [документации по longjmp](/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>См. также

- [Исключения](index.md)
- [Взаимодействие с собственными библиотеками](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
