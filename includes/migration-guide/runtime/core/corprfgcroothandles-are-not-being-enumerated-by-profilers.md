---
ms.openlocfilehash: 4f52535e54607cc824500f9c6a14964a1dec9d32
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620558"
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
