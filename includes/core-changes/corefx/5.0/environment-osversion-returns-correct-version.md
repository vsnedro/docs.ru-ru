---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558191"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="2fea4-101">Environment.OSVersion возвращает правильную версию операционной системы</span><span class="sxs-lookup"><span data-stu-id="2fea4-101">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="2fea4-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает фактическую версию операционной системы (ОС), а не, например, ту ОС, которая выбрана для совместимости приложений.</span><span class="sxs-lookup"><span data-stu-id="2fea4-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2fea4-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="2fea4-103">Change description</span></span>

<span data-ttu-id="2fea4-104">В предыдущих версиях .NET <xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает версию ОС, которая может быть неверной, если приложение работает в режиме совместимости Windows.</span><span class="sxs-lookup"><span data-stu-id="2fea4-104">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="2fea4-105">Дополнительные сведения см. в [примечаниях к функции GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="2fea4-105">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="2fea4-106">Начиная с .NET 5.0 <xref:System.Environment.OSVersion?displayProperty=nameWithType> возвращает фактическую версию операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2fea4-106">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2fea4-107">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="2fea4-107">Reason for change</span></span>

<span data-ttu-id="2fea4-108">Пользователи этого свойства предполагают, что оно будет возвращать фактическую версию операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2fea4-108">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="2fea4-109">Большинство приложений .NET не указывают поддерживаемую версию в манифесте приложения и поэтому получают поддерживаемую по умолчанию версию из узла dotnet.</span><span class="sxs-lookup"><span data-stu-id="2fea4-109">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="2fea4-110">В результате оболочка совместимости редко применяется для работающего приложения.</span><span class="sxs-lookup"><span data-stu-id="2fea4-110">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="2fea4-111">Когда Windows выпускает новую версию, а более старый узел dotnet по-прежнему используется, эти приложения могут получить неверную версию ОС.</span><span class="sxs-lookup"><span data-stu-id="2fea4-111">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="2fea4-112">Возврат фактической версии более соответствует ожиданиям разработчиков этого API.</span><span class="sxs-lookup"><span data-stu-id="2fea4-112">Returning the actual version is more inline with developers' expectations of this API.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2fea4-113">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="2fea4-113">Version introduced</span></span>

<span data-ttu-id="2fea4-114">5.0</span><span class="sxs-lookup"><span data-stu-id="2fea4-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2fea4-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="2fea4-115">Recommended action</span></span>

<span data-ttu-id="2fea4-116">Проверьте и протестируйте код, который использует <xref:System.Environment.OSVersion?displayProperty=nameWithType>, чтобы убедиться, что он ведет себя должным образом.</span><span class="sxs-lookup"><span data-stu-id="2fea4-116">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

#### <a name="category"></a><span data-ttu-id="2fea4-117">Категория</span><span class="sxs-lookup"><span data-stu-id="2fea4-117">Category</span></span>

<span data-ttu-id="2fea4-118">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="2fea4-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2fea4-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2fea4-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
