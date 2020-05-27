---
title: -langversion (параметры компилятора C#)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 408b2fb1f19f872db675321601ebc1b0c921044b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802958"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="db9b0-102">-langversion (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="db9b0-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="db9b0-103">Инструктирует компилятор принимать только синтаксис, включенный в заданную спецификацию языка C#.</span><span class="sxs-lookup"><span data-stu-id="db9b0-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="db9b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db9b0-104">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="db9b0-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="db9b0-105">Arguments</span></span>

`option`

<span data-ttu-id="db9b0-106">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="db9b0-106">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="db9b0-107">Версия языка по умолчанию зависит от целевой платформы приложения, а также от установленной версии пакета SDK или Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="db9b0-107">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="db9b0-108">Эти правила определяются в статье о [настройке версии языка](../configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="db9b0-108">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="db9b0-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="db9b0-109">Remarks</span></span>

<span data-ttu-id="db9b0-110">Параметр компилятора **-langversion** не влияет на метаданные, на которые ссылается ваше приложение C#.</span><span class="sxs-lookup"><span data-stu-id="db9b0-110">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="db9b0-111">Так как каждая версия компилятора C# содержит расширения для спецификации языка, параметр **-langversion** не позволяет получить функциональные возможности, аналогичные более ранней версии компилятора.</span><span class="sxs-lookup"><span data-stu-id="db9b0-111">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="db9b0-112">Кроме того, в отличие от обновлений версии C#, которые обычно совпадают с основными выпусками платформы .NET Framework, новые функции и возможности синтаксиса могут быть не привязаны к конкретной версии этой платформы.</span><span class="sxs-lookup"><span data-stu-id="db9b0-112">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="db9b0-113">Для работы с новыми версиями требуется обновление компилятора, которое также выпускается с новой редакцией C#. Тем не менее для каждой функции определен собственный набор минимальных требований к API .NET или общеязыковой среде выполнения, в результате чего их можно выполнять на более ранних версиях платформы, добавив необходимые пакеты NuGet или другие библиотеки.</span><span class="sxs-lookup"><span data-stu-id="db9b0-113">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="db9b0-114">Независимо от того, какой параметр **-langversion** вы задали, используйте для создания файлов с расширением .exe или .dll. текущую версию общеязыковой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="db9b0-114">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="db9b0-115">Единственным исключением являются дружественные сборки и [-moduleassemblyname (параметр компилятора C#)](./moduleassemblyname-compiler-option.md), которые работают при установке параметра **-langversion:ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="db9b0-115">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="db9b0-116">Другие способы указания версии языка C# см. в статье [Выбор версии языка C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="db9b0-116">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="db9b0-117">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="db9b0-117">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="db9b0-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="db9b0-118">C# language specification</span></span>

| <span data-ttu-id="db9b0-119">Version</span><span class="sxs-lookup"><span data-stu-id="db9b0-119">Version</span></span>          | <span data-ttu-id="db9b0-120">Ссылка</span><span class="sxs-lookup"><span data-stu-id="db9b0-120">Link</span></span>                       | <span data-ttu-id="db9b0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="db9b0-121">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="db9b0-122">C# 7.0 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="db9b0-122">C# 7.0 and later</span></span> |                            | <span data-ttu-id="db9b0-123">В настоящее время недоступно.</span><span class="sxs-lookup"><span data-stu-id="db9b0-123">Not currently available</span></span>                                                 |
| <span data-ttu-id="db9b0-124">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-124">C# 6.0</span></span>           | <span data-ttu-id="db9b0-125">[Ссылка][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="db9b0-125">[Link][csharp-6]</span></span>           | <span data-ttu-id="db9b0-126">Спецификация языка C# версии 6 (неофициальный проект): .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="db9b0-126">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="db9b0-127">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-127">C# 5.0</span></span>           | <span data-ttu-id="db9b0-128">[Загрузить PDF-файл][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="db9b0-128">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="db9b0-129">Стандарт ECMA-334, 5-й выпуск</span><span class="sxs-lookup"><span data-stu-id="db9b0-129">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="db9b0-130">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-130">C# 3.0</span></span>           | <span data-ttu-id="db9b0-131">[Загрузить DOC-файл][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="db9b0-131">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="db9b0-132">Спецификация языка C#, версия 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="db9b0-132">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="db9b0-133">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-133">C# 2.0</span></span>           | <span data-ttu-id="db9b0-134">[Загрузить PDF-файл][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="db9b0-134">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="db9b0-135">Стандарт ECMA-334, 4-й выпуск</span><span class="sxs-lookup"><span data-stu-id="db9b0-135">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="db9b0-136">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="db9b0-136">C# 1.2</span></span>           | <span data-ttu-id="db9b0-137">[Загрузить DOC-файл][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="db9b0-137">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="db9b0-138">Спецификация языка C#, версия 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="db9b0-138">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="db9b0-139">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-139">C# 1.0</span></span>           | <span data-ttu-id="db9b0-140">[Загрузить DOC-файл][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="db9b0-140">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="db9b0-141">Спецификация языка C#, версия 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="db9b0-141">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="db9b0-142">Минимальная версия пакета SDK, необходимая для поддержки всех возможностей языка</span><span class="sxs-lookup"><span data-stu-id="db9b0-142">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="db9b0-143">В следующей таблице перечислены минимальные версии пакета SDK с компилятором C#, поддерживающим соответствующую версию языка:</span><span class="sxs-lookup"><span data-stu-id="db9b0-143">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="db9b0-144">Версия C#</span><span class="sxs-lookup"><span data-stu-id="db9b0-144">C# version</span></span> | <span data-ttu-id="db9b0-145">Минимальная версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="db9b0-145">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="db9b0-146">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-146">C# 8.0</span></span>     | <span data-ttu-id="db9b0-147">Microsoft Visual Studio/Build Tools 2019, версия 16.3 или пакет SDK .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-147">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="db9b0-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="db9b0-148">C# 7.3</span></span>     | <span data-ttu-id="db9b0-149">Microsoft Visual Studio/Build Tools 2017, версия 15.7</span><span class="sxs-lookup"><span data-stu-id="db9b0-149">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="db9b0-150">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="db9b0-150">C# 7.2</span></span>     | <span data-ttu-id="db9b0-151">Microsoft Visual Studio/Build Tools 2017, версия 15.5</span><span class="sxs-lookup"><span data-stu-id="db9b0-151">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="db9b0-152">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="db9b0-152">C# 7.1</span></span>     | <span data-ttu-id="db9b0-153">Microsoft Visual Studio/Build Tools 2017, версия 15.3</span><span class="sxs-lookup"><span data-stu-id="db9b0-153">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="db9b0-154">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-154">C# 7.0</span></span>     | <span data-ttu-id="db9b0-155">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="db9b0-155">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="db9b0-156">C# 6</span><span class="sxs-lookup"><span data-stu-id="db9b0-156">C# 6</span></span>       | <span data-ttu-id="db9b0-157">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="db9b0-157">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="db9b0-158">C# 5</span><span class="sxs-lookup"><span data-stu-id="db9b0-158">C# 5</span></span>       | <span data-ttu-id="db9b0-159">Microsoft Visual Studio/Build Tools 2012 или встроенный компилятор .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="db9b0-159">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="db9b0-160">C# 4</span><span class="sxs-lookup"><span data-stu-id="db9b0-160">C# 4</span></span>       | <span data-ttu-id="db9b0-161">Microsoft Visual Studio/Build Tools 2010 или встроенный компилятор .NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-161">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="db9b0-162">C# 3</span><span class="sxs-lookup"><span data-stu-id="db9b0-162">C# 3</span></span>       | <span data-ttu-id="db9b0-163">Microsoft Visual Studio/Build Tools 2008 или встроенный компилятор .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="db9b0-163">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="db9b0-164">C# 2</span><span class="sxs-lookup"><span data-stu-id="db9b0-164">C# 2</span></span>       | <span data-ttu-id="db9b0-165">Microsoft Visual Studio/Build Tools 2005 или встроенный компилятор .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-165">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="db9b0-166">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="db9b0-166">C# 1.0/1.2</span></span> | <span data-ttu-id="db9b0-167">Microsoft Visual Studio/Build Tools .NET 2002 или встроенный компилятор .NET Framework 1.0</span><span class="sxs-lookup"><span data-stu-id="db9b0-167">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="db9b0-168">См. также</span><span class="sxs-lookup"><span data-stu-id="db9b0-168">See also</span></span>

- [<span data-ttu-id="db9b0-169">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="db9b0-169">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="db9b0-170">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="db9b0-170">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
