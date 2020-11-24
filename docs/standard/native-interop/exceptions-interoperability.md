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
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="43d89-102">Работа с исключениями взаимодействия в неуправляемом коде</span><span class="sxs-lookup"><span data-stu-id="43d89-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="43d89-103">Взаимодействие исключений неуправляемого кода поддерживается только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="43d89-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="43d89-104">На других платформах возникают проблемы переносимости.</span><span class="sxs-lookup"><span data-stu-id="43d89-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="43d89-105">Поскольку в ABI для UNIX нет определения для обработки исключений, управляемый код не может понять, как работают механизмы исключений.</span><span class="sxs-lookup"><span data-stu-id="43d89-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="43d89-106">Таким образом, исключения могут приводить к непредсказуемым поведению и сбоям.</span><span class="sxs-lookup"><span data-stu-id="43d89-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="43d89-107">Поведение setjmp/longjmp</span><span class="sxs-lookup"><span data-stu-id="43d89-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="43d89-108">Взаимодействие с функциями C `setjmp` и `longjmp` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="43d89-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="43d89-109">Нельзя использовать `longjmp` для пропуска управляемых кадров.</span><span class="sxs-lookup"><span data-stu-id="43d89-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="43d89-110">Дополнительные сведения см. в [документации по longjmp](/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="43d89-110">For more information, see [longjmp documentation](/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="43d89-111">См. также</span><span class="sxs-lookup"><span data-stu-id="43d89-111">See also</span></span>

- [<span data-ttu-id="43d89-112">Исключения</span><span class="sxs-lookup"><span data-stu-id="43d89-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="43d89-113">Взаимодействие с собственными библиотеками</span><span class="sxs-lookup"><span data-stu-id="43d89-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
