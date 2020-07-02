---
ms.openlocfilehash: d4f0095bc9fde98087dce528c8154d9c9ac6ddb7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621838"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="63805-101">Проверка орфографии WPF завершается сбоем непредвиденным образом</span><span class="sxs-lookup"><span data-stu-id="63805-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="63805-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="63805-102">Details</span></span>

<span data-ttu-id="63805-103">Сюда относится целый ряд проблем, связанных со средством проверки орфографии WPF:</span><span class="sxs-lookup"><span data-stu-id="63805-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="63805-104">В некоторых случаях средство проверки орфографии WPF создает исключение <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="63805-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="63805-105">Средство проверки орфографии WPF завершается сбоем с исключением <xref:System.UnauthorizedAccessException> при запуске приложений с использованием параметра "Запуск от имени другого пользователя"</span><span class="sxs-lookup"><span data-stu-id="63805-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="63805-106">Средство проверки орфографии WPF неверно определяет орфографические ошибки в составных словах, например "Hausnummer" в немецком языке.</span><span class="sxs-lookup"><span data-stu-id="63805-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="63805-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="63805-107">Suggestion</span></span>

<span data-ttu-id="63805-108">Проблема 1. Эта проблема исправлена в .NET Framework 4.6.2. Проблема 2. Средство проверки орфографии WPF больше не поддерживается при запуске приложений с использованием параметра "Запуск от имени другого пользователя".</span><span class="sxs-lookup"><span data-stu-id="63805-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="63805-109">Начиная с версии .NET Framework 4.6.2, работа запускаемых таким образом приложений не завершается непредвиденным сбоем. Вместо этого средство проверки орфографии автоматически отключается.</span><span class="sxs-lookup"><span data-stu-id="63805-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="63805-110">Проблема 3. Эта проблема была исправлена в версии .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="63805-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="63805-111">name</span><span class="sxs-lookup"><span data-stu-id="63805-111">Name</span></span>    | <span data-ttu-id="63805-112">Значение</span><span class="sxs-lookup"><span data-stu-id="63805-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="63805-113">Область</span><span class="sxs-lookup"><span data-stu-id="63805-113">Scope</span></span>   |<span data-ttu-id="63805-114">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="63805-114">Edge</span></span>|
|<span data-ttu-id="63805-115">Version</span><span class="sxs-lookup"><span data-stu-id="63805-115">Version</span></span>|<span data-ttu-id="63805-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="63805-116">4.6.1</span></span>|
|<span data-ttu-id="63805-117">Type</span><span class="sxs-lookup"><span data-stu-id="63805-117">Type</span></span>|<span data-ttu-id="63805-118">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="63805-118">Runtime</span></span>|
