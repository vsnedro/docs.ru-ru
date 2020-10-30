---
title: Предупреждение SYSLIB0006
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0006.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 45d2d8ec6ad99996f8b8f46d0c2e0ac2e02cf450
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333145"
---
# <a name="syslib0006-threadabort-is-not-supported"></a>SYSLIB0006. Thread.Abort не поддерживается

Следующие API помечены как устаревшие, начиная с версии .NET 5.0. При использовании этих API во время компиляции создается предупреждение `SYSLIB0006`.

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workaround"></a>Обходной путь

Используйте <xref:System.Threading.CancellationToken>, чтобы прервать обработку единицы работы вместо вызова <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. В следующем примере демонстрируется применение <xref:System.Threading.CancellationToken>.

```csharp
void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
{
    if (QueryIsMoreWorkPending())
    {
        // If the CancellationToken is marked as "needs to cancel",
        // this will throw the appropriate exception.
        cancellationToken.ThrowIfCancellationRequested();

        WorkItem work = DequeueWorkItem();
        ProcessWorkItem(work);
    }
}
```

## <a name="see-also"></a>См. также

- [Thread.Abort устарел — критическое изменение](3.1-5.0.md#threadabort-is-obsolete)
- [Отмена в управляемых потоках](../../standard/threading/cancellation-in-managed-threads.md)
