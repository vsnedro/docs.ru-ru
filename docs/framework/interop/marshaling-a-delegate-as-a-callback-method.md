---
title: Маршалинг делегата как метода обратного вызова
description: Сведения о том, как маршалировать делегата в качестве метода обратного вызова. Здесь приведен пример того, как передавать делегатов в неуправляемую функцию, ожидающую указатели на функции.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
ms.openlocfilehash: bf9ef3b9d48c0869dcc96820c3a2fb6fb608479e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618952"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="536f2-104">Маршалинг делегата как метода обратного вызова</span><span class="sxs-lookup"><span data-stu-id="536f2-104">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="536f2-105">В этом примере показан способ передачи делегатов в неуправляемую функцию, ожидающую указатели на функции.</span><span class="sxs-lookup"><span data-stu-id="536f2-105">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="536f2-106">Делегат — это класс, который может содержать ссылку на метод. Делегат эквивалентен типобезопасному указателю на функцию или функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="536f2-106">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>

> [!NOTE]
> <span data-ttu-id="536f2-107">При использовании делегата в вызове функции общеязыковая среда выполнения защищает делегат от сборщика мусора в течение этого вызова.</span><span class="sxs-lookup"><span data-stu-id="536f2-107">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="536f2-108">Однако если неуправляемая функция сохраняет делегат для использования после завершения вызова, необходимо вручную запретить сбор мусора до того, как неуправляемая функция завершит обработку делегата.</span><span class="sxs-lookup"><span data-stu-id="536f2-108">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="536f2-109">Дополнительные сведения см. в разделах [Пример HandleRef](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) и [Пример GCHandle](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="536f2-109">For more information, see the [HandleRef Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) and [GCHandle Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span></span>

<span data-ttu-id="536f2-110">В примере обратного вызова используются следующие неуправляемые функции со своими первоначальными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="536f2-110">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="536f2-111">`TestCallBack` экспортируется из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="536f2-111">`TestCallBack` exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestCallBack(FPTR pf, int value);
    ```

- <span data-ttu-id="536f2-112">`TestCallBack2` экспортируется из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="536f2-112">`TestCallBack2` exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestCallBack2(FPTR2 pf2, char* value);
    ```

<span data-ttu-id="536f2-113">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализацию вышеуказанных функций.</span><span class="sxs-lookup"><span data-stu-id="536f2-113">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>

<span data-ttu-id="536f2-114">В этом примере класс `NativeMethods` содержит управляемые прототипы методов `TestCallBack` и `TestCallBack2`.</span><span class="sxs-lookup"><span data-stu-id="536f2-114">In this sample, the `NativeMethods` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="536f2-115">Оба метода передают делегат функции обратного вызова в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="536f2-115">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="536f2-116">Сигнатура делегата должна соответствовать сигнатуре метода, на который ссылается делегат.</span><span class="sxs-lookup"><span data-stu-id="536f2-116">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="536f2-117">Например, подписи делегатов для `FPtr` и `FPtr2` аналогичны методам `DoSomething` и `DoSomething2`.</span><span class="sxs-lookup"><span data-stu-id="536f2-117">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>

## <a name="declaring-prototypes"></a><span data-ttu-id="536f2-118">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="536f2-118">Declaring Prototypes</span></span>
[!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
[!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
[!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]

## <a name="calling-functions"></a><span data-ttu-id="536f2-119">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="536f2-119">Calling Functions</span></span>
[!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
[!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
[!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]

## <a name="see-also"></a><span data-ttu-id="536f2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="536f2-120">See also</span></span>

- <span data-ttu-id="536f2-121">[Различные примеры маршалинга](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="536f2-121">[Miscellaneous Marshaling Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span></span>
- [<span data-ttu-id="536f2-122">Типы данных в вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="536f2-122">Platform Invoke Data Types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="536f2-123">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="536f2-123">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
