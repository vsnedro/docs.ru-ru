---
ms.openlocfilehash: 004e2d1883b631e88ab5e164b1120c3b081b7041
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496477"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek может возвращать ошибочные значения NULL в выходном параметре

#### <a name="details"></a>Подробнее

В некоторых сценариях с несколькими потоками <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> может возвращать значение true, но заполнять выходной параметр значением NULL (вместо правильного значения).

#### <a name="suggestion"></a>Предложение

Эта проблема решена в EntityFramework 4.5.1. Чтобы устранить проблему, выполните обновление до этой версии платформы.

| name    | Значение       |
|:--------|:------------|
| Область   |Значительно|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.ConcurrentQueue`1.TryPeek(`0@)``

-->
