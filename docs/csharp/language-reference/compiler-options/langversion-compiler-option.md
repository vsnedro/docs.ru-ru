---
description: -langversion (параметры компилятора C#)
title: -langversion (параметры компилятора C#)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: b0e966bcc87303c0a7c2199fbfac743b22481424
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125479"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="39d28-103">-langversion (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="39d28-103">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="39d28-104">Инструктирует компилятор принимать только синтаксис, включенный в заданную спецификацию языка C#.</span><span class="sxs-lookup"><span data-stu-id="39d28-104">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="39d28-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39d28-105">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="39d28-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="39d28-106">Arguments</span></span>

`option`

<span data-ttu-id="39d28-107">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="39d28-107">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="39d28-108">Версия языка по умолчанию зависит от целевой платформы приложения, а также от установленной версии пакета SDK или Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="39d28-108">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="39d28-109">Эти правила определяются в статье о [настройке версии языка](../configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="39d28-109">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="39d28-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="39d28-110">Remarks</span></span>

<span data-ttu-id="39d28-111">Параметр компилятора **-langversion** не влияет на метаданные, на которые ссылается ваше приложение C#.</span><span class="sxs-lookup"><span data-stu-id="39d28-111">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="39d28-112">Так как каждая версия компилятора C# содержит расширения для спецификации языка, параметр **-langversion** не позволяет получить функциональные возможности, аналогичные более ранней версии компилятора.</span><span class="sxs-lookup"><span data-stu-id="39d28-112">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="39d28-113">Кроме того, в отличие от обновлений версии C#, которые обычно совпадают с основными выпусками платформы .NET Framework, новые функции и возможности синтаксиса могут быть не привязаны к конкретной версии этой платформы.</span><span class="sxs-lookup"><span data-stu-id="39d28-113">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="39d28-114">Для работы с новыми версиями требуется обновление компилятора, которое также выпускается с новой редакцией C#. Тем не менее для каждой функции определен собственный набор минимальных требований к API .NET или общеязыковой среде выполнения, в результате чего их можно выполнять на более ранних версиях платформы, добавив необходимые пакеты NuGet или другие библиотеки.</span><span class="sxs-lookup"><span data-stu-id="39d28-114">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="39d28-115">Независимо от того, какой параметр **-langversion** вы задали, используйте для создания файлов с расширением .exe или .dll. текущую версию общеязыковой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="39d28-115">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="39d28-116">Единственным исключением являются дружественные сборки и [-moduleassemblyname (параметр компилятора C#)](./moduleassemblyname-compiler-option.md), которые работают при установке параметра **-langversion:ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="39d28-116">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="39d28-117">Другие способы указания версии языка C# см. в статье [Выбор версии языка C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="39d28-117">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="39d28-118">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="39d28-118">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="39d28-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="39d28-119">C# language specification</span></span>

| <span data-ttu-id="39d28-120">Version</span><span class="sxs-lookup"><span data-stu-id="39d28-120">Version</span></span>          | <span data-ttu-id="39d28-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="39d28-121">Link</span></span>                       | <span data-ttu-id="39d28-122">Описание</span><span class="sxs-lookup"><span data-stu-id="39d28-122">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="39d28-123">C# 7.0 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="39d28-123">C# 7.0 and later</span></span> |                            | <span data-ttu-id="39d28-124">В настоящее время недоступно.</span><span class="sxs-lookup"><span data-stu-id="39d28-124">Not currently available</span></span>                                                 |
| <span data-ttu-id="39d28-125">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="39d28-125">C# 6.0</span></span>           | <span data-ttu-id="39d28-126">[Ссылка][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="39d28-126">[Link][csharp-6]</span></span>           | <span data-ttu-id="39d28-127">Спецификация языка C# версии 6 (неофициальный проект): .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="39d28-127">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="39d28-128">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="39d28-128">C# 5.0</span></span>           | <span data-ttu-id="39d28-129">[Загрузить PDF-файл][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="39d28-129">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="39d28-130">Стандарт ECMA-334, 5-й выпуск</span><span class="sxs-lookup"><span data-stu-id="39d28-130">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="39d28-131">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="39d28-131">C# 3.0</span></span>           | <span data-ttu-id="39d28-132">[Загрузить DOC-файл][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="39d28-132">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="39d28-133">Спецификация языка C#, версия 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="39d28-133">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="39d28-134">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="39d28-134">C# 2.0</span></span>           | <span data-ttu-id="39d28-135">[Загрузить PDF-файл][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="39d28-135">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="39d28-136">Стандарт ECMA-334, 4-й выпуск</span><span class="sxs-lookup"><span data-stu-id="39d28-136">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="39d28-137">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="39d28-137">C# 1.2</span></span>           | <span data-ttu-id="39d28-138">[Загрузить DOC-файл][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="39d28-138">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="39d28-139">Спецификация языка C#, версия 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="39d28-139">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="39d28-140">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="39d28-140">C# 1.0</span></span>           | <span data-ttu-id="39d28-141">[Загрузить DOC-файл][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="39d28-141">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="39d28-142">Спецификация языка C#, версия 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="39d28-142">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="39d28-143">Минимальная версия пакета SDK, необходимая для поддержки всех возможностей языка</span><span class="sxs-lookup"><span data-stu-id="39d28-143">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="39d28-144">В следующей таблице перечислены минимальные версии пакета SDK с компилятором C#, поддерживающим соответствующую версию языка:</span><span class="sxs-lookup"><span data-stu-id="39d28-144">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="39d28-145">Версия C#</span><span class="sxs-lookup"><span data-stu-id="39d28-145">C# version</span></span> | <span data-ttu-id="39d28-146">Минимальная версия пакета SDK</span><span class="sxs-lookup"><span data-stu-id="39d28-146">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="39d28-147">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="39d28-147">C# 8.0</span></span>     | <span data-ttu-id="39d28-148">Microsoft Visual Studio/Build Tools 2019, версия 16.3 или пакет SDK .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="39d28-148">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="39d28-149">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="39d28-149">C# 7.3</span></span>     | <span data-ttu-id="39d28-150">Microsoft Visual Studio/Build Tools 2017, версия 15.7</span><span class="sxs-lookup"><span data-stu-id="39d28-150">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="39d28-151">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="39d28-151">C# 7.2</span></span>     | <span data-ttu-id="39d28-152">Microsoft Visual Studio/Build Tools 2017, версия 15.5</span><span class="sxs-lookup"><span data-stu-id="39d28-152">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="39d28-153">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="39d28-153">C# 7.1</span></span>     | <span data-ttu-id="39d28-154">Microsoft Visual Studio/Build Tools 2017, версия 15.3</span><span class="sxs-lookup"><span data-stu-id="39d28-154">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="39d28-155">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="39d28-155">C# 7.0</span></span>     | <span data-ttu-id="39d28-156">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="39d28-156">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="39d28-157">C# 6</span><span class="sxs-lookup"><span data-stu-id="39d28-157">C# 6</span></span>       | <span data-ttu-id="39d28-158">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="39d28-158">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="39d28-159">C# 5</span><span class="sxs-lookup"><span data-stu-id="39d28-159">C# 5</span></span>       | <span data-ttu-id="39d28-160">Microsoft Visual Studio/Build Tools 2012 или встроенный компилятор .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="39d28-160">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="39d28-161">C# 4</span><span class="sxs-lookup"><span data-stu-id="39d28-161">C# 4</span></span>       | <span data-ttu-id="39d28-162">Microsoft Visual Studio/Build Tools 2010 или встроенный компилятор .NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="39d28-162">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="39d28-163">C# 3</span><span class="sxs-lookup"><span data-stu-id="39d28-163">C# 3</span></span>       | <span data-ttu-id="39d28-164">Microsoft Visual Studio/Build Tools 2008 или встроенный компилятор .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="39d28-164">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="39d28-165">C# 2</span><span class="sxs-lookup"><span data-stu-id="39d28-165">C# 2</span></span>       | <span data-ttu-id="39d28-166">Microsoft Visual Studio/Build Tools 2005 или встроенный компилятор .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="39d28-166">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="39d28-167">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="39d28-167">C# 1.0/1.2</span></span> | <span data-ttu-id="39d28-168">Microsoft Visual Studio/Build Tools .NET 2002 или встроенный компилятор .NET Framework 1.0</span><span class="sxs-lookup"><span data-stu-id="39d28-168">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="39d28-169">См. также</span><span class="sxs-lookup"><span data-stu-id="39d28-169">See also</span></span>

- [<span data-ttu-id="39d28-170">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="39d28-170">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="39d28-171">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="39d28-171">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
