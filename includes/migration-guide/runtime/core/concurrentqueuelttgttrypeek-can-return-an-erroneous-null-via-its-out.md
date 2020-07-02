---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622145"
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
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
