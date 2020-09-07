---
ms.openlocfilehash: d4e60f2a59980263916718ebcc71cc359952c031
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496717"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="d4327-101">Проверка орфографии WPF завершается сбоем непредвиденным образом</span><span class="sxs-lookup"><span data-stu-id="d4327-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="d4327-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d4327-102">Details</span></span>

<span data-ttu-id="d4327-103">Сюда относится целый ряд проблем, связанных со средством проверки орфографии WPF:</span><span class="sxs-lookup"><span data-stu-id="d4327-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="d4327-104">В некоторых случаях средство проверки орфографии WPF создает исключение <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d4327-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="d4327-105">Средство проверки орфографии WPF завершается сбоем с исключением <xref:System.UnauthorizedAccessException> при запуске приложений с использованием параметра "Запуск от имени другого пользователя"</span><span class="sxs-lookup"><span data-stu-id="d4327-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="d4327-106">Средство проверки орфографии WPF неверно определяет орфографические ошибки в составных словах, например "Hausnummer" в немецком языке.</span><span class="sxs-lookup"><span data-stu-id="d4327-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="d4327-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="d4327-107">Suggestion</span></span>

<span data-ttu-id="d4327-108">Проблема 1. Эта проблема исправлена в .NET Framework 4.6.2. Проблема 2. Средство проверки орфографии WPF больше не поддерживается при запуске приложений с использованием параметра "Запуск от имени другого пользователя".</span><span class="sxs-lookup"><span data-stu-id="d4327-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="d4327-109">Начиная с версии .NET Framework 4.6.2, работа запускаемых таким образом приложений не завершается непредвиденным сбоем. Вместо этого средство проверки орфографии автоматически отключается.</span><span class="sxs-lookup"><span data-stu-id="d4327-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="d4327-110">Проблема 3. Эта проблема была исправлена в версии .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="d4327-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="d4327-111">name</span><span class="sxs-lookup"><span data-stu-id="d4327-111">Name</span></span>    | <span data-ttu-id="d4327-112">Значение</span><span class="sxs-lookup"><span data-stu-id="d4327-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d4327-113">Область</span><span class="sxs-lookup"><span data-stu-id="d4327-113">Scope</span></span>   |<span data-ttu-id="d4327-114">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="d4327-114">Edge</span></span>|
|<span data-ttu-id="d4327-115">Version</span><span class="sxs-lookup"><span data-stu-id="d4327-115">Version</span></span>|<span data-ttu-id="d4327-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="d4327-116">4.6.1</span></span>|
|<span data-ttu-id="d4327-117">Type</span><span class="sxs-lookup"><span data-stu-id="d4327-117">Type</span></span>|<span data-ttu-id="d4327-118">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d4327-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d4327-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d4327-119">Affected APIs</span></span>

<span data-ttu-id="d4327-120">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="d4327-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
