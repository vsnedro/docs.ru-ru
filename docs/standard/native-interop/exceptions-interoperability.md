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
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="a30fd-102">Работа с исключениями взаимодействия в неуправляемом коде</span><span class="sxs-lookup"><span data-stu-id="a30fd-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="a30fd-103">Взаимодействие исключений неуправляемого кода поддерживается только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="a30fd-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="a30fd-104">На других платформах возникают проблемы переносимости.</span><span class="sxs-lookup"><span data-stu-id="a30fd-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="a30fd-105">Поскольку в ABI для UNIX нет определения для обработки исключений, управляемый код не может понять, как работают механизмы исключений.</span><span class="sxs-lookup"><span data-stu-id="a30fd-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="a30fd-106">Таким образом, исключения могут приводить к непредсказуемым поведению и сбоям.</span><span class="sxs-lookup"><span data-stu-id="a30fd-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="a30fd-107">Поведение setjmp/longjmp</span><span class="sxs-lookup"><span data-stu-id="a30fd-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="a30fd-108">Взаимодействие с функциями C `setjmp` и `longjmp` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a30fd-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="a30fd-109">Нельзя использовать `longjmp` для пропуска управляемых кадров.</span><span class="sxs-lookup"><span data-stu-id="a30fd-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="a30fd-110">Дополнительные сведения см. в [документации по longjmp](/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="a30fd-110">For more information, see [longjmp documentation](/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="a30fd-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a30fd-111">See also</span></span>

- [<span data-ttu-id="a30fd-112">Исключения</span><span class="sxs-lookup"><span data-stu-id="a30fd-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="a30fd-113">Взаимодействие с собственными библиотеками</span><span class="sxs-lookup"><span data-stu-id="a30fd-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
