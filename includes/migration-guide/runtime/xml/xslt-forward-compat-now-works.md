---
ms.openlocfilehash: 8c8477ae3719cfcc2060459ba85bcc9e76f11c41
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497927"
---
### <a name="xslt-forward-compat-now-works"></a><span data-ttu-id="11b80-101">Теперь обеспечивается прямая совместимость с XSLT</span><span class="sxs-lookup"><span data-stu-id="11b80-101">XSLT forward compat now works</span></span>

#### <a name="details"></a><span data-ttu-id="11b80-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="11b80-102">Details</span></span>

<span data-ttu-id="11b80-103">В .NET Framework 4 XSLT 1.0 имелись следующие проблемы с прямой совместимостью:</span><span class="sxs-lookup"><span data-stu-id="11b80-103">In the .NET Framework 4, XSLT 1.0 forward compatibility had the following issues:</span></span><ul><li><span data-ttu-id="11b80-104">Загрузка таблицы стилей завершалась сбоем, если ее версия была установлена равной 2.0, и средство синтаксического анализа обнаруживало нераспознанную конструкцию XSLT 1.0.</span><span class="sxs-lookup"><span data-stu-id="11b80-104">Loading a style sheet failed if its version was set to 2.0 and the parser encountered an unrecognized XSLT 1.0 construct.</span></span></li><li><span data-ttu-id="11b80-105">Конструкции <code>xsl:sort</code> не удавалось сортировать данные, если версия таблицы стилей была установлена равной 1.1.</span><span class="sxs-lookup"><span data-stu-id="11b80-105">The <code>xsl:sort</code> construct failed to sort data if the style sheet version was set to 1.1.</span></span></li></ul><span data-ttu-id="11b80-106">В .NET Framework 4.5 эти проблемы исправлены, и режим прямой совместимости с XSLT 1.0 работает нормально.</span><span class="sxs-lookup"><span data-stu-id="11b80-106">In the .NET Framework 4.5, these issues have been fixed, and XSLT 1.0 forward compatibility mode works properly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="11b80-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="11b80-107">Suggestion</span></span>

<span data-ttu-id="11b80-108">Эта проблема не затрагивает большинство приложений, однако в некоторых случаях сортировка данных теперь будет выполняться по-другому с учетом конструкции xsl:sort.</span><span class="sxs-lookup"><span data-stu-id="11b80-108">Most apps should be unaffected, however data will be sorted differently in some cases now that xsl:sort is respected.</span></span> <span data-ttu-id="11b80-109">Если в таблицах стилей версии 1.1 используется конструкция <code>xsl:sort</code>, убедитесь, что приложения не зависят от порядка данных без сортировки.</span><span class="sxs-lookup"><span data-stu-id="11b80-109">If <code>xsl:sort</code> is used in 1.1 style sheets, confirm that apps were not depending on the unsorted order of data.</span></span> <span data-ttu-id="11b80-110">Если приложения зависят от параметров сортировки версии 4.0, удалите конструкцию <code>xsl:sort</code> из таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="11b80-110">If apps rely on the 4.0 sorting behavior, remove <code>xsl:sort</code> from the style sheet.</span></span>

| <span data-ttu-id="11b80-111">name</span><span class="sxs-lookup"><span data-stu-id="11b80-111">Name</span></span>    | <span data-ttu-id="11b80-112">Значение</span><span class="sxs-lookup"><span data-stu-id="11b80-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="11b80-113">Область</span><span class="sxs-lookup"><span data-stu-id="11b80-113">Scope</span></span>   |<span data-ttu-id="11b80-114">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="11b80-114">Edge</span></span>|
|<span data-ttu-id="11b80-115">Version</span><span class="sxs-lookup"><span data-stu-id="11b80-115">Version</span></span>|<span data-ttu-id="11b80-116">4.5</span><span class="sxs-lookup"><span data-stu-id="11b80-116">4.5</span></span>|
|<span data-ttu-id="11b80-117">Type</span><span class="sxs-lookup"><span data-stu-id="11b80-117">Type</span></span>|<span data-ttu-id="11b80-118">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="11b80-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="11b80-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="11b80-119">Affected APIs</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Xml.Xsl.XslCompiledTransform`

-->
