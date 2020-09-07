---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496752"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="6ca5f-101">Исключение ObjectDisposedException, создаваемое средством проверки орфографии WPF</span><span class="sxs-lookup"><span data-stu-id="6ca5f-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="6ca5f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="6ca5f-102">Details</span></span>

<span data-ttu-id="6ca5f-103">В некоторых случаях при завершении работы приложений WPF происходит сбой с исключением <xref:System.ObjectDisposedException?displayProperty=fullName>, создаваемым средством проверки орфографии.</span><span class="sxs-lookup"><span data-stu-id="6ca5f-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="6ca5f-104">Эта ошибка исправлена в WPF .NET Framework 4.7 за счет правильной обработки этого исключения, что позволяет исключить подобное нежелательное поведение приложений.</span><span class="sxs-lookup"><span data-stu-id="6ca5f-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="6ca5f-105">Следует отметить, что случайные первичные исключения могут по-прежнему наблюдаться в приложениях, выполняемых в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="6ca5f-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6ca5f-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="6ca5f-106">Suggestion</span></span>

<span data-ttu-id="6ca5f-107">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="6ca5f-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="6ca5f-108">name</span><span class="sxs-lookup"><span data-stu-id="6ca5f-108">Name</span></span>    | <span data-ttu-id="6ca5f-109">Значение</span><span class="sxs-lookup"><span data-stu-id="6ca5f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6ca5f-110">Область</span><span class="sxs-lookup"><span data-stu-id="6ca5f-110">Scope</span></span>   |<span data-ttu-id="6ca5f-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="6ca5f-111">Edge</span></span>|
|<span data-ttu-id="6ca5f-112">Version</span><span class="sxs-lookup"><span data-stu-id="6ca5f-112">Version</span></span>|<span data-ttu-id="6ca5f-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="6ca5f-113">4.6.1</span></span>|
|<span data-ttu-id="6ca5f-114">Type</span><span class="sxs-lookup"><span data-stu-id="6ca5f-114">Type</span></span>|<span data-ttu-id="6ca5f-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="6ca5f-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6ca5f-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="6ca5f-116">Affected APIs</span></span>

<span data-ttu-id="6ca5f-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="6ca5f-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
