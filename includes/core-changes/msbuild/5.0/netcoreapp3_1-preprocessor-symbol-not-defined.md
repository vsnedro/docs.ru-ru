---
ms.openlocfilehash: de35df21d1887bc95a3106edba312c53daad8b68
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654746"
---
### <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a><span data-ttu-id="9f709-101">Символ препроцессора NETCOREAPP3_1 не определен при нацеливании на .NET 5</span><span class="sxs-lookup"><span data-stu-id="9f709-101">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>

<span data-ttu-id="9f709-102">В .NET 5.0 RC2 и более поздних версиях в проектах больше не определяются символы препроцессора для более ранних версий. Определяются символы препроцессора только для целевой версии.</span><span class="sxs-lookup"><span data-stu-id="9f709-102">In .NET 5.0 RC2 and later versions, projects no longer define preprocessor symbols for earlier versions, but only for the version that they target.</span></span> <span data-ttu-id="9f709-103">Это то же самое поведение, что и в .NET Core 1.0–3.1.</span><span class="sxs-lookup"><span data-stu-id="9f709-103">This is the same behavior as .NET Core 1.0 - 3.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9f709-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="9f709-104">Version introduced</span></span>

<span data-ttu-id="9f709-105">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="9f709-105">5.0 RC2</span></span>

#### <a name="change-description"></a><span data-ttu-id="9f709-106">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="9f709-106">Change description</span></span>

<span data-ttu-id="9f709-107">В версиях .NET 5.0 с предварительной версии 7 до RC1 в проектах, предназначенных для `net5.0`, определяются символы препроцессора `NETCOREAPP3_1` и `NET5_0`.</span><span class="sxs-lookup"><span data-stu-id="9f709-107">In .NET 5.0 preview 7 through RC1, projects that target `net5.0` define both `NETCOREAPP3_1` and `NET5_0` preprocessor symbols.</span></span> <span data-ttu-id="9f709-108">Цель этого изменения поведения заключается в том, чтобы начиная с .NET 5.0 символы условной компиляции [были накопительными](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span><span class="sxs-lookup"><span data-stu-id="9f709-108">The intent behind this behavior change was that starting with .NET 5.0, conditional compilation [symbols would be cumulative](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span></span>

<span data-ttu-id="9f709-109">В .NET 5.0 RC2 и более поздних версиях в проектах определяются только символы для моникеров целевой платформы (TFM), для которой она предназначена, а не для предыдущих версий.</span><span class="sxs-lookup"><span data-stu-id="9f709-109">In .NET 5.0 RC2 and later, projects only define symbols for the target framework monikers (TFM) that it targets and not for any earlier versions.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9f709-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="9f709-110">Reason for change</span></span>

<span data-ttu-id="9f709-111">Изменение из предварительной версии 7 было отменено из-за отзывов пользователей.</span><span class="sxs-lookup"><span data-stu-id="9f709-111">The change from preview 7 was reverted due to customer feedback.</span></span> <span data-ttu-id="9f709-112">Определение символов для более ранних версий удивило и запутало пользователей, и некоторые предположили, что это ошибка в компиляторе C#.</span><span class="sxs-lookup"><span data-stu-id="9f709-112">Defining symbols for earlier versions surprised and confused customers, and some assumed it was a bug in the C# compiler.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9f709-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="9f709-113">Recommended action</span></span>

<span data-ttu-id="9f709-114">Убедитесь, что в логике `#if` не предполагается определение `NETCOREAPP3_1`, если проект предназначен для `net5.0` или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9f709-114">Make sure that your `#if` logic doesn't assume that `NETCOREAPP3_1` is defined when the project targets `net5.0` or higher.</span></span> <span data-ttu-id="9f709-115">Вместо этого сделайте так, чтобы `NETCOREAPP3_1` определялся только в том случае, если проект явно предназначен для `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="9f709-115">Instead, assume that `NETCOREAPP3_1` is only defined when the project explicitly targets `netcoreapp3.1`.</span></span>

<span data-ttu-id="9f709-116">Например, если проект предназначен для нескольких платформ (.NET Core 2.1 и .NET Core 3.1) и вы вызываете API, которые появились в .NET Core 3.1, то логика `#if` должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9f709-116">For example, if your project multitargets for .NET Core 2.1 and .NET Core 3.1 and you call APIs that were introduced in .NET Core 3.1, your `#if` logic should look as follows:</span></span>

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

#### <a name="category"></a><span data-ttu-id="9f709-117">Категория</span><span class="sxs-lookup"><span data-stu-id="9f709-117">Category</span></span>

<span data-ttu-id="9f709-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="9f709-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9f709-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="9f709-119">Affected APIs</span></span>

<span data-ttu-id="9f709-120">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9f709-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
