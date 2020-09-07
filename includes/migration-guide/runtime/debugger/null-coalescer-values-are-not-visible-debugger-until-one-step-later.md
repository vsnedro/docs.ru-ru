---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497580"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>Значения NULL операции объединения отображаются в отладчике с запаздыванием на один шаг

#### <a name="details"></a>Подробнее

Из-за ошибки в .NET Framework 4.5 значения, заданные с использованием операции объединения NULL, не отображаются в отладчике немедленно после выполнения операции присваивания в 64-разрядной версии платформы.

#### <a name="suggestion"></a>Предложение

После выполнения одного дополнительного шага в отладчике локальные значения или значения поля корректно обновляются. Эта проблема также была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
