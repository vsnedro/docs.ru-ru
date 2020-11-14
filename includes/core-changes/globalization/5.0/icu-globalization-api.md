---
ms.openlocfilehash: 02b5dc181abe384c1a5f47c042e475f67a0afe1c
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400809"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="6eac3-101">API-интерфейсы глобализации, которые используют библиотеки ICU в Windows</span><span class="sxs-lookup"><span data-stu-id="6eac3-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="6eac3-102">.NET 5.0 и более поздних версий использует библиотеки [ICU (международные компоненты для Юникода)](http://site.icu-project.org/home) для поддержки глобализации при работе в Windows 10 с обновлением за май 2019 года или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="6eac3-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6eac3-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="6eac3-103">Change description</span></span>

<span data-ttu-id="6eac3-104">В .NET Core 1.0–3.1 и .NET Framework 4 и более поздних версий библиотеки .NET используют для функции глобализации в Windows API [Многоязыковой поддержки (NLS)](/windows/win32/intl/national-language-support).</span><span class="sxs-lookup"><span data-stu-id="6eac3-104">In .NET Core 1.0 - 3.1 and .NET Framework 4 and later, .NET libraries use [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality on Windows.</span></span> <span data-ttu-id="6eac3-105">Например, функции NLS применялись для сравнения строк, получения данных о языке и региональных параметрах, а также для изменения капитализации строк в соответствии с необходимыми языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="6eac3-105">For example, NLS functions were used to compare strings, get culture information, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="6eac3-106">Начиная с .NET 5.0, для приложений в среде Windows 10 с обновлением за май 2019 года или более поздней версии библиотеки .NET по умолчанию используют API-интерфейсы глобализации [ICU](http://site.icu-project.org/home).</span><span class="sxs-lookup"><span data-stu-id="6eac3-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs, by default.</span></span>

> [!NOTE]
> <span data-ttu-id="6eac3-107">В Windows 10 с обновлением за май 2019 года и более поздних версий входит библиотека ICU.</span><span class="sxs-lookup"><span data-stu-id="6eac3-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="6eac3-108">Если среда выполнения .NET не может загрузить ICU, вместо нее используется NLS.</span><span class="sxs-lookup"><span data-stu-id="6eac3-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

#### <a name="behavioral-differences"></a><span data-ttu-id="6eac3-109">Различия в поведении</span><span class="sxs-lookup"><span data-stu-id="6eac3-109">Behavioral differences</span></span>

<span data-ttu-id="6eac3-110">Вы можете заметить изменения в приложении, даже если не догадываетесь, что используете средства глобализации.</span><span class="sxs-lookup"><span data-stu-id="6eac3-110">You might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="6eac3-111">В этом разделе перечислено несколько из возможных изменений поведения.</span><span class="sxs-lookup"><span data-stu-id="6eac3-111">This section lists a couple of the behavioral changes you might see, but there are others too.</span></span>

##### <a name="stringindexof"></a><span data-ttu-id="6eac3-112">String.IndexOf</span><span class="sxs-lookup"><span data-stu-id="6eac3-112">String.IndexOf</span></span>

<span data-ttu-id="6eac3-113">Рассмотрим следующий код, который вызывает <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType>, чтобы найти в строке индекс символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="6eac3-113">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="6eac3-114">В предыдущих версиях .NET для Windows фрагмент кода выводит `6`.</span><span class="sxs-lookup"><span data-stu-id="6eac3-114">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="6eac3-115">В .NET 5.0 и более поздних версиях на Windows 19H1 и более поздних версий фрагмент кода выводит `-1`.</span><span class="sxs-lookup"><span data-stu-id="6eac3-115">In .NET 5.0 and later versions on Windows 19H1 and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="6eac3-116">Чтобы исправить этот код, выполняя порядковый поиск вместо поиска с учетом языка и региональных параметров, вызовите перегрузку <xref:System.String.IndexOf(System.String,System.StringComparison)> и передайте в нее в качестве аргумента <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6eac3-116">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="6eac3-117">Вы можете запустить правила анализа кода [CA1307: использование StringComparison, чтобы ясно указать намерение](../../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) и [CA1309: использование StringComparison по порядковым номерам](../../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md), чтобы найти эти точки вызова в коде.</span><span class="sxs-lookup"><span data-stu-id="6eac3-117">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="6eac3-118">Дополнительные сведения см. в статье [Изменения поведения при сравнении строк в .NET 5+](../../../../docs/standard/base-types/string-comparison-net-5-plus.md).</span><span class="sxs-lookup"><span data-stu-id="6eac3-118">For more information, see [Behavior changes when comparing strings on .NET 5+](../../../../docs/standard/base-types/string-comparison-net-5-plus.md).</span></span>

##### <a name="currency-symbol"></a><span data-ttu-id="6eac3-119">Символ валют</span><span class="sxs-lookup"><span data-stu-id="6eac3-119">Currency symbol</span></span>

<span data-ttu-id="6eac3-120">Рассмотрим следующий код, который форматирует строку с помощью указателя формата валюты `C`.</span><span class="sxs-lookup"><span data-stu-id="6eac3-120">Consider the following code that formats a string using the currency format specifier `C`.</span></span> <span data-ttu-id="6eac3-121">Для языка и региональных параметров текущего потока заданы настройки только для языка, а не страны.</span><span class="sxs-lookup"><span data-stu-id="6eac3-121">The current thread's culture is set to a culture that includes only the language and not the country.</span></span>

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- <span data-ttu-id="6eac3-122">В предыдущих версиях .NET для Windows значение text равно `"100,00 €"`.</span><span class="sxs-lookup"><span data-stu-id="6eac3-122">In previous versions of .NET on Windows, the value of text is `"100,00 €"`.</span></span>
- <span data-ttu-id="6eac3-123">В .NET 5.0 и более поздних версиях в Windows 19H1 и более поздних версий значение text равно `"100,00 ¤"`, и вместо евро в нем используется международный символ валюты.</span><span class="sxs-lookup"><span data-stu-id="6eac3-123">In .NET 5.0 and later versions on Windows 19H1 and later versions, the value of text is `"100,00 ¤"`, which uses the international currency symbol instead of the euro.</span></span> <span data-ttu-id="6eac3-124">В ICU валюта является свойством страны или региона, а не языка.</span><span class="sxs-lookup"><span data-stu-id="6eac3-124">In ICU, the design is that a currency is a property of a country or region, not a language.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6eac3-125">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="6eac3-125">Reason for change</span></span>

<span data-ttu-id="6eac3-126">Это изменение введено для унификации поведения глобализации .NET во всех поддерживаемых операционных системах.</span><span class="sxs-lookup"><span data-stu-id="6eac3-126">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="6eac3-127">Благодаря ему приложения смогут объединять собственные библиотеки глобализации и не зависеть от встроенных библиотек операционных систем.</span><span class="sxs-lookup"><span data-stu-id="6eac3-127">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the operating system's built-in libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6eac3-128">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6eac3-128">Version introduced</span></span>

<span data-ttu-id="6eac3-129">Предварительная версия 4 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="6eac3-129">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6eac3-130">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="6eac3-130">Recommended action</span></span>

<span data-ttu-id="6eac3-131">От разработчика не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="6eac3-131">No action is required on the part of the developer.</span></span> <span data-ttu-id="6eac3-132">Но если вы хотите по-прежнему использовать API-интерфейсы глобализации NLS, настройте [параметр времени выполнения](../../../../docs/core/run-time-config/globalization.md#nls), чтобы вернуться к старому поведению.</span><span class="sxs-lookup"><span data-stu-id="6eac3-132">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="6eac3-133">Дополнительные сведения о доступных параметрах см. в статье [Глобализация .NET и ICU](../../../../docs/standard/globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="6eac3-133">For more information about the available switches, see the [.NET globalization and ICU](../../../../docs/standard/globalization-localization/globalization-icu.md) article.</span></span>

#### <a name="category"></a><span data-ttu-id="6eac3-134">Категория</span><span class="sxs-lookup"><span data-stu-id="6eac3-134">Category</span></span>

- <span data-ttu-id="6eac3-135">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="6eac3-135">Core .NET libraries</span></span>
- <span data-ttu-id="6eac3-136">Глобализация</span><span class="sxs-lookup"><span data-stu-id="6eac3-136">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6eac3-137">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="6eac3-137">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="6eac3-138">Почти все типы в пространстве имен <xref:System.Globalization?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6eac3-138">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>
- <span data-ttu-id="6eac3-139"><xref:System.Array.Sort%2A?displayProperty=fullName> (при сортировке массива строк)</span><span class="sxs-lookup"><span data-stu-id="6eac3-139"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting an array of strings)</span></span>
- <span data-ttu-id="6eac3-140"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (если элементы списка являются строками)</span><span class="sxs-lookup"><span data-stu-id="6eac3-140"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="6eac3-141"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (если ключи являются строками)</span><span class="sxs-lookup"><span data-stu-id="6eac3-141"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="6eac3-142"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (если ключи являются строками)</span><span class="sxs-lookup"><span data-stu-id="6eac3-142"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="6eac3-143"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (если набор содержит строки)</span><span class="sxs-lookup"><span data-stu-id="6eac3-143"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

-->
