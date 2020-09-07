---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496683"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="739ae-101">Улучшенные подсказки клавиш в WPF</span><span class="sxs-lookup"><span data-stu-id="739ae-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="739ae-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="739ae-102">Details</span></span>

<span data-ttu-id="739ae-103">Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="739ae-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="739ae-104">WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="739ae-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="739ae-105">Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="739ae-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="739ae-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="739ae-106">Suggestion</span></span>

<span data-ttu-id="739ae-107">Н/Д</span><span class="sxs-lookup"><span data-stu-id="739ae-107">N/A</span></span>

| <span data-ttu-id="739ae-108">name</span><span class="sxs-lookup"><span data-stu-id="739ae-108">Name</span></span>    | <span data-ttu-id="739ae-109">Значение</span><span class="sxs-lookup"><span data-stu-id="739ae-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="739ae-110">Область</span><span class="sxs-lookup"><span data-stu-id="739ae-110">Scope</span></span>   |<span data-ttu-id="739ae-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="739ae-111">Edge</span></span>|
|<span data-ttu-id="739ae-112">Version</span><span class="sxs-lookup"><span data-stu-id="739ae-112">Version</span></span>|<span data-ttu-id="739ae-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="739ae-113">4.7.2</span></span>|
|<span data-ttu-id="739ae-114">Type</span><span class="sxs-lookup"><span data-stu-id="739ae-114">Type</span></span>|<span data-ttu-id="739ae-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="739ae-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="739ae-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="739ae-116">Affected APIs</span></span>

<span data-ttu-id="739ae-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="739ae-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
