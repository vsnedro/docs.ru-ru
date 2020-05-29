---
title: Критические изменения в области глобализации
description: Список критических изменений в области глобализации в .NET Core.
ms.date: 04/07/2020
ms.openlocfilehash: 0c3367cb3515c6f473f53be6062b54f2e836b8c5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702309"
---
# <a name="globalization-breaking-changes"></a>Критические изменения в области глобализации

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [API-интерфейсы глобализации, которые используют библиотеки ICU в Windows](#globalization-apis-use-icu-libraries-on-windows) | 5.0 |
| [Теперь StringInfo и TextElementEnumerator совместимы с UAX29](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | 5.0 |
| [Языковой стандарт "C" сопоставляется с инвариантным языковым стандартом](#c-locale-maps-to-the-invariant-locale) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
