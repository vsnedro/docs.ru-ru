---
title: Регистрация обратных вызовов для запросов на отмену
ms.date: 08/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: faa8dada5779f6eaee7a60e6210ec604f5fb4680
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608458"
---
# <a name="register-callbacks-for-cancellation-requests"></a>Регистрация обратных вызовов для запросов на отмену

Узнайте, как зарегистрировать делегат, который будет вызываться, когда свойство <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> становится истинным (true). Значение изменяется с false на true при вызове <xref:System.Threading.CancellationTokenSource.Cancel%2A> на объекте, создавшем маркер. Этот прием используется для отмены асинхронных операций, в которых отсутствует встроенная поддержка унифицированной инфраструктуры отмены, а также для разблокирования методов, ожидающих завершения асинхронной операции.

> [!NOTE]
> Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу <kbd>F5</kbd>, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис > Параметры > Отладка > Общие**.

## <a name="example"></a>Пример

В примере ниже метод <xref:System.Net.WebClient.CancelAsync%2A> регистрируется в качестве метода, вызываемого при запросе отмены с помощью токена отмены.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb":::

Если при регистрации обратного вызова отмена уже была зарегистрирована, то этот обратный вызов гарантированно будет вызван. В этом случае метод <xref:System.Net.WebClient.CancelAsync%2A> не выполняет никаких действий (при отсутствии выполняющихся асинхронных операций), поэтому этот метод можно вызывать всегда.

## <a name="see-also"></a>См. также раздел

- [Отмена в управляемых потоках](cancellation-in-managed-threads.md)
- <xref:System.Net.WebClient.DownloadStringTaskAsync(System.String)?displayProperty=nameWithType>
