---
title: Критические изменения в области глобализации
description: Список критических изменений в области глобализации в .NET Core.
ms.date: 04/07/2020
ms.openlocfilehash: 93990d89204df1b2d7498e1d748378fae05598c3
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065073"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="c0dd0-103">Критические изменения в области глобализации</span><span class="sxs-lookup"><span data-stu-id="c0dd0-103">Globalization breaking changes</span></span>

<span data-ttu-id="c0dd0-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="c0dd0-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="c0dd0-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="c0dd0-105">Breaking change</span></span> | <span data-ttu-id="c0dd0-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c0dd0-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="c0dd0-107">Для некоторых символов латиницы-1 изменилась категория Юникода</span><span class="sxs-lookup"><span data-stu-id="c0dd0-107">Unicode category changed for some Latin-1 characters</span></span>](#unicode-category-changed-for-some-latin-1-characters) | <span data-ttu-id="c0dd0-108">5.0</span><span class="sxs-lookup"><span data-stu-id="c0dd0-108">5.0</span></span> |
| [<span data-ttu-id="c0dd0-109">API-интерфейсы глобализации, которые используют библиотеки ICU в Windows</span><span class="sxs-lookup"><span data-stu-id="c0dd0-109">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="c0dd0-110">5.0</span><span class="sxs-lookup"><span data-stu-id="c0dd0-110">5.0</span></span> |
| [<span data-ttu-id="c0dd0-111">Теперь StringInfo и TextElementEnumerator совместимы с UAX29</span><span class="sxs-lookup"><span data-stu-id="c0dd0-111">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="c0dd0-112">5.0</span><span class="sxs-lookup"><span data-stu-id="c0dd0-112">5.0</span></span> |
| [<span data-ttu-id="c0dd0-113">Языковой стандарт "C" сопоставляется с инвариантным языковым стандартом</span><span class="sxs-lookup"><span data-stu-id="c0dd0-113">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="c0dd0-114">3.0</span><span class="sxs-lookup"><span data-stu-id="c0dd0-114">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="c0dd0-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c0dd0-115">.NET 5.0</span></span>

[!INCLUDE [unicode-categories-for-latin1-chars](../../../includes/core-changes/globalization/5.0/unicode-categories-for-latin1-chars.md)]

***

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="c0dd0-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c0dd0-116">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
