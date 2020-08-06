---
ms.openlocfilehash: 74c3d3247912dcd638a9379d54e682967c5e400b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302723"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="00646-101">API-интерфейсы глобализации, которые используют библиотеки ICU в Windows</span><span class="sxs-lookup"><span data-stu-id="00646-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="00646-102">.NET 5.0 и более поздних версий использует библиотеки [ICU (международные компоненты для Юникода)](http://site.icu-project.org/home) для поддержки глобализации при работе в Windows 10 с обновлением за май 2019 года или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="00646-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="00646-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="00646-103">Change description</span></span>

<span data-ttu-id="00646-104">Ранее в библиотеках .NET для поддержки глобализации использовались API-интерфейсы [NLS (многоязыковая поддержка)](/windows/win32/intl/national-language-support).</span><span class="sxs-lookup"><span data-stu-id="00646-104">Previously, .NET libraries used [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality.</span></span> <span data-ttu-id="00646-105">Например, функции NLS применялись для получения данных о языке и региональных параметрах, таких как шаблоны формата, правила сравнения строк, а также для изменения капитализации строк.</span><span class="sxs-lookup"><span data-stu-id="00646-105">For example, NLS functions were used to get culture data, such as date and time format patterns, compare strings, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="00646-106">Начиная с .NET 5.0, для приложений в среде Windows 10 с обновлением за май 2019 года или более поздней версии библиотеки .NET используют API-интерфейсы глобализации [ICU](http://site.icu-project.org/home).</span><span class="sxs-lookup"><span data-stu-id="00646-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs.</span></span> <span data-ttu-id="00646-107">В Windows 10 с обновлением за май 2019 года и более поздних версий входит библиотека ICU.</span><span class="sxs-lookup"><span data-stu-id="00646-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="00646-108">Если среда выполнения .NET не может загрузить ICU, вместо нее используется NLS.</span><span class="sxs-lookup"><span data-stu-id="00646-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

<span data-ttu-id="00646-109">Это изменение внесено по следующим двум причинам:</span><span class="sxs-lookup"><span data-stu-id="00646-109">This change was introduced for two reasons:</span></span>

- <span data-ttu-id="00646-110">Приложения получают одинаковые стандарты глобализации на разных платформах, включая Linux, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="00646-110">Apps have the same globalization behavior across platforms, including Linux, macOS, and Windows.</span></span>
- <span data-ttu-id="00646-111">Приложения могут управлять параметрами глобализации с помощью пользовательских библиотек ICU.</span><span class="sxs-lookup"><span data-stu-id="00646-111">Apps can control globalization behavior by using custom ICU libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="00646-112">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="00646-112">Version introduced</span></span>

<span data-ttu-id="00646-113">Предварительная версия 4 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="00646-113">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="00646-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="00646-114">Recommended action</span></span>

<span data-ttu-id="00646-115">От разработчика не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="00646-115">No action is required on the part of the developer.</span></span> <span data-ttu-id="00646-116">Но если вы хотите по-прежнему использовать API-интерфейсы глобализации NLS, настройте [параметр времени выполнения](../../../../docs/core/run-time-config/globalization.md#nls), чтобы вернуться к старому поведению.</span><span class="sxs-lookup"><span data-stu-id="00646-116">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="00646-117">Дополнительные сведения о доступных параметрах см. в статье [Глобализация .NET и ICU](/dotnet/standard/globalization-localization/globalization-icu).</span><span class="sxs-lookup"><span data-stu-id="00646-117">For more information about the available switches, see the [.NET globalization and ICU](/dotnet/standard/globalization-localization/globalization-icu) article.</span></span>

#### <a name="category"></a><span data-ttu-id="00646-118">Категория</span><span class="sxs-lookup"><span data-stu-id="00646-118">Category</span></span>

<span data-ttu-id="00646-119">Глобализация</span><span class="sxs-lookup"><span data-stu-id="00646-119">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="00646-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="00646-120">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="00646-121">Почти все типы в пространстве имен <xref:System.Globalization?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="00646-121">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`

-->
