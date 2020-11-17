---
title: Предупреждение SYSLIB0006
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0006.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 222b669a8a0260713e85721e6031144bb7bda5cc
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440664"
---
# <a name="syslib0006-threadabort-is-not-supported"></a>SYSLIB0006. Thread.Abort не поддерживается

Следующие API помечены как устаревшие, начиная с версии .NET 5.0. При использовании этих API во время компиляции создается предупреждение `SYSLIB0006`.

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workarounds"></a>Обходные пути

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

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>См. также

- [Thread.Abort устарел — критическое изменение](3.1-5.0.md#threadabort-is-obsolete)
- [Отмена в управляемых потоках](../../standard/threading/cancellation-in-managed-threads.md)
