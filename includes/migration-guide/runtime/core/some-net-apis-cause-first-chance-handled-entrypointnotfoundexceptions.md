---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622140"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a><span data-ttu-id="18069-101">Некоторые интерфейсы API .NET создают первый экземпляр (обрабатываемый) EntryPointNotFoundExceptions</span><span class="sxs-lookup"><span data-stu-id="18069-101">Some .NET APIs cause first chance (handled) EntryPointNotFoundExceptions</span></span>

#### <a name="details"></a><span data-ttu-id="18069-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="18069-102">Details</span></span>

<span data-ttu-id="18069-103">В .NET Framework 4.5 несколько методов .NET начали создавать первый экземпляр <xref:System.EntryPointNotFoundException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="18069-103">In the .NET Framework 4.5, a small number of .NET methods began throwing first chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span> <span data-ttu-id="18069-104">Эти исключения обрабатывались в .NET Framework, но могли нарушать работу службы автоматизации тестирования, которая не ожидала первых экземпляров исключений.</span><span class="sxs-lookup"><span data-stu-id="18069-104">These exceptions were handled within the .NET Framework, but could break test automation that did not expect the first chance exceptions.</span></span> <span data-ttu-id="18069-105">Те же интерфейсы API препятствуют работе некоторых сценариев ApiVerifier, если включен тест HighVersionLie.</span><span class="sxs-lookup"><span data-stu-id="18069-105">These same APIs break some ApiVerifier scenarios when HighVersionLie is enabled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="18069-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="18069-106">Suggestion</span></span>

<span data-ttu-id="18069-107">Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="18069-107">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="18069-108">Кроме того, службу автоматизации тестирования можно обновить, чтобы она не прерывала свое выполнение при создании первого экземпляра <xref:System.EntryPointNotFoundException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="18069-108">Alternatively, test automation can be updated to not break on first-chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="18069-109">name</span><span class="sxs-lookup"><span data-stu-id="18069-109">Name</span></span>    | <span data-ttu-id="18069-110">Значение</span><span class="sxs-lookup"><span data-stu-id="18069-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="18069-111">Область</span><span class="sxs-lookup"><span data-stu-id="18069-111">Scope</span></span>   |<span data-ttu-id="18069-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="18069-112">Edge</span></span>|
|<span data-ttu-id="18069-113">Version</span><span class="sxs-lookup"><span data-stu-id="18069-113">Version</span></span>|<span data-ttu-id="18069-114">4.5</span><span class="sxs-lookup"><span data-stu-id="18069-114">4.5</span></span>|
|<span data-ttu-id="18069-115">Type</span><span class="sxs-lookup"><span data-stu-id="18069-115">Type</span></span>|<span data-ttu-id="18069-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="18069-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="18069-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="18069-117">Affected APIs</span></span>

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|
