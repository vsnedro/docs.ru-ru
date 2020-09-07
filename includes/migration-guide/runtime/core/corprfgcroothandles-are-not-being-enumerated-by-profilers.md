---
ms.openlocfilehash: 25437dcc0c814ed2265b2efb34316af48b372ebd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496179"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>Профилировщики не перечисляют COR_PRF_GC_ROOT_HANDLE

#### <a name="details"></a>Подробнее

В .NET Framework 4.5.1 API профилирования <code>RootReferences2()</code> по ошибке никогда не возвращает <code>COR_PRF_GC_ROOT_HANDLE</code> (вместо этого возвращается <code>COR_PRF_GC_ROOT_OTHER</code>). Эта проблема решена в .NET Framework 4.6.

#### <a name="suggestion"></a>Предложение

Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
