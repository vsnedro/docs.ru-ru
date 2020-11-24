---
title: Регистрация обратных вызовов для запросов на отмену
ms.date: 08/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: f551055fc6e5e4565329201e9e0be6e4a83487a1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826408"
---
# <a name="register-callbacks-for-cancellation-requests"></a><span data-ttu-id="86396-102">Регистрация обратных вызовов для запросов на отмену</span><span class="sxs-lookup"><span data-stu-id="86396-102">Register callbacks for cancellation requests</span></span>

<span data-ttu-id="86396-103">Узнайте, как зарегистрировать делегат, который будет вызываться, когда свойство <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> становится истинным (true).</span><span class="sxs-lookup"><span data-stu-id="86396-103">Learn how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true.</span></span> <span data-ttu-id="86396-104">Значение изменяется с false на true при вызове <xref:System.Threading.CancellationTokenSource.Cancel%2A> на объекте, создавшем маркер.</span><span class="sxs-lookup"><span data-stu-id="86396-104">The value changes from false to true when a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token is made.</span></span> <span data-ttu-id="86396-105">Этот прием используется для отмены асинхронных операций, в которых отсутствует встроенная поддержка унифицированной инфраструктуры отмены, а также для разблокирования методов, ожидающих завершения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="86396-105">Use this technique for canceling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>

> [!NOTE]
> <span data-ttu-id="86396-106">Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом".</span><span class="sxs-lookup"><span data-stu-id="86396-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="86396-107">Эта ошибка не является критической.</span><span class="sxs-lookup"><span data-stu-id="86396-107">This error is benign.</span></span> <span data-ttu-id="86396-108">Вы можете нажать клавишу <kbd>F5</kbd>, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже.</span><span class="sxs-lookup"><span data-stu-id="86396-108">You can press <kbd>F5</kbd> to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="86396-109">Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис > Параметры > Отладка > Общие**.</span><span class="sxs-lookup"><span data-stu-id="86396-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>

## <a name="example"></a><span data-ttu-id="86396-110">Пример</span><span class="sxs-lookup"><span data-stu-id="86396-110">Example</span></span>

<span data-ttu-id="86396-111">В примере ниже метод <xref:System.Net.WebClient.CancelAsync%2A> регистрируется в качестве метода, вызываемого при запросе отмены с помощью токена отмены.</span><span class="sxs-lookup"><span data-stu-id="86396-111">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb":::

<span data-ttu-id="86396-112">Если при регистрации обратного вызова отмена уже была зарегистрирована, то этот обратный вызов гарантированно будет вызван.</span><span class="sxs-lookup"><span data-stu-id="86396-112">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="86396-113">В этом случае метод <xref:System.Net.WebClient.CancelAsync%2A> не выполняет никаких действий (при отсутствии выполняющихся асинхронных операций), поэтому этот метод можно вызывать всегда.</span><span class="sxs-lookup"><span data-stu-id="86396-113">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>

## <a name="see-also"></a><span data-ttu-id="86396-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="86396-114">See also</span></span>

- [<span data-ttu-id="86396-115">Отмена в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="86396-115">Cancellation in managed threads</span></span>](cancellation-in-managed-threads.md)
- <xref:System.Net.WebClient.DownloadStringTaskAsync(System.String)?displayProperty=nameWithType>
