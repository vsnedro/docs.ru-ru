---
title: Критическое изменение. Thread.Abort устарел
description: Сведения о критическом изменении .NET 5.0 в основных библиотеках .NET, в которых устарел API Thread.Abort.
ms.date: 11/01/2020
ms.openlocfilehash: 6d7dfce8fda393bfd88c9b4cf0c59d53942cee25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759637"
---
# <a name="threadabort-is-obsolete"></a>Thread.Abort устарел

API <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> являются устаревшими. В проектах, предназначенных для .NET 5.0 или более поздней версии, можно столкнуться с предупреждениями во время компиляции `SYSLIB0006` при вызове этих методов.

## <a name="change-description"></a>Описание изменений

Ранее вызовы <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> не создавали предупреждения во время компиляции, однако метод вызывал <xref:System.PlatformNotSupportedException> во время выполнения.

Начиная с .NET 5.0 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> помечен как устаревший с отображением соответствующего предупреждения. При вызове этого метода выдается предупреждение компилятора `SYSLIB0006`. Реализация метода остается неизменной, и по-прежнему возникнет исключение <xref:System.PlatformNotSupportedException>.

## <a name="reason-for-change"></a>Причина изменения

Учитывая, что <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> всегда создает <xref:System.PlatformNotSupportedException> для всех реализаций .NET, кроме .NET Framework, был добавлен в метод <xref:System.ObsoleteAttribute>, чтобы привлечь внимание к местам, где он вызывается.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="recommended-action"></a>Рекомендованное действие

- Используйте <xref:System.Threading.CancellationToken>, чтобы прервать обработку единицы работы вместо вызова <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. В следующем примере демонстрируется применение <xref:System.Threading.CancellationToken>.

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

  Подробные сведения см. в статье [Отмена в управляемых потоках](../../../../standard/threading/cancellation-in-managed-threads.md).

- Чтобы отключить предупреждение во время компиляции, отключите код предупреждения `SYSLIB0006`. Код предупреждения относится только к <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>, и подавление не влияет на другие предупреждения об устаревании в коде. Однако рекомендуется удалить вызовы <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> вместо того, чтобы подавлять предупреждение.

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  Предупреждение можно также отключить в файле проекта.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
