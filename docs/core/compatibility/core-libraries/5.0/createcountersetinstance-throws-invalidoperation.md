---
title: Критическое изменение. CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует
description: Сведения о критическом изменении .NET 5,0 в основных библиотеках .NET, где CounterSet.CreateCounterSetInstance создает исключение, если счетчик уже существует.
ms.date: 11/01/2020
ms.openlocfilehash: 28042690b71f9b86e4e54748ec75467bbe232684
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759838"
---
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a>Теперь CounterSet.CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует.

Начиная с .NET 5.0 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> создает исключение <xref:System.InvalidOperationException> вместо <xref:System.ArgumentException>, если набор счетчиков уже существует.

## <a name="change-description"></a>Описание изменений

В .NET Framework и .NET Core 1.0–3.1 экземпляр набора счетчиков можно создать, вызвав <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>. Однако если набор счетчиков уже существует, метод вызывает исключение <xref:System.ArgumentException>.

В .NET 5.0 и более поздних версиях при вызове <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> и наличии набора счетчиков возникает исключение <xref:System.InvalidOperationException>.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="recommended-action"></a>Рекомендованное действие

Если при вызове <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> возникают исключения <xref:System.ArgumentException>, также следует рассмотреть перехват исключений <xref:System.InvalidOperationException>.

> [!NOTE]
> Перехват исключений <xref:System.ArgumentException> не рекомендуется.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
