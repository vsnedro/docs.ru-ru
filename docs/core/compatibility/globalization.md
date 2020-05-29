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
# <a name="globalization-breaking-changes"></a><span data-ttu-id="c5344-103">Критические изменения в области глобализации</span><span class="sxs-lookup"><span data-stu-id="c5344-103">Globalization breaking changes</span></span>

<span data-ttu-id="c5344-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="c5344-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="c5344-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="c5344-105">Breaking change</span></span> | <span data-ttu-id="c5344-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c5344-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="c5344-107">API-интерфейсы глобализации, которые используют библиотеки ICU в Windows</span><span class="sxs-lookup"><span data-stu-id="c5344-107">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="c5344-108">5.0</span><span class="sxs-lookup"><span data-stu-id="c5344-108">5.0</span></span> |
| [<span data-ttu-id="c5344-109">Теперь StringInfo и TextElementEnumerator совместимы с UAX29</span><span class="sxs-lookup"><span data-stu-id="c5344-109">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="c5344-110">5.0</span><span class="sxs-lookup"><span data-stu-id="c5344-110">5.0</span></span> |
| [<span data-ttu-id="c5344-111">Языковой стандарт "C" сопоставляется с инвариантным языковым стандартом</span><span class="sxs-lookup"><span data-stu-id="c5344-111">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="c5344-112">3.0</span><span class="sxs-lookup"><span data-stu-id="c5344-112">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="c5344-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5344-113">.NET 5.0</span></span>

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="c5344-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5344-114">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
