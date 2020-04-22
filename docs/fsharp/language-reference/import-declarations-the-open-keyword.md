---
title: Объявления импорта. Ключевое слово open
description: Узнайте о декларациях импорта f и о том, как они указывают модуль или пространство имен, на элементы которых можно ссылаться без использования полностью квалифицированного имени.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021529"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="00a71-103">Объявления импорта: ключевое слово `open`</span><span class="sxs-lookup"><span data-stu-id="00a71-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="00a71-104">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="00a71-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="00a71-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="00a71-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="00a71-106">*В декларации импорта* указывается модуль или пространство имен, на элементы которого можно ссылаться без использования полностью квалифицированного имени.</span><span class="sxs-lookup"><span data-stu-id="00a71-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="00a71-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00a71-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="00a71-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="00a71-108">Remarks</span></span>

<span data-ttu-id="00a71-109">Ссылки на код с помощью полностью квалифицированного пространства имен или модульного пути каждый раз могут создавать код, который трудно писать, читать и поддерживать.</span><span class="sxs-lookup"><span data-stu-id="00a71-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="00a71-110">Вместо этого можно `open` использовать ключевое слово для часто используемых модулей и именных пространств, чтобы при упоминании члена этого модуля или пространства имен можно было использовать короткую форму имени вместо полностью квалифицированного имени.</span><span class="sxs-lookup"><span data-stu-id="00a71-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="00a71-111">Это ключевое слово `using` похоже на ключевое `using namespace` слово в C, `Imports` в Visual C и в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="00a71-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="00a71-112">Модуль или при условии, что пространство имен должно быть в том же проекте или в справочном проекте или сборке.</span><span class="sxs-lookup"><span data-stu-id="00a71-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="00a71-113">Если это не так, вы можете добавить ссылку на проект или использовать `-reference` опцию `-r`командной строки (или ее аббревиативу).</span><span class="sxs-lookup"><span data-stu-id="00a71-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="00a71-114">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="00a71-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="00a71-115">В декларации об импорте имена доступны в коде, который следует за декларацией, вплоть до конца оговоренного пространства имен, модуля или файла.</span><span class="sxs-lookup"><span data-stu-id="00a71-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="00a71-116">При использовании нескольких импортных деклараций они должны отображаться на отдельных строках.</span><span class="sxs-lookup"><span data-stu-id="00a71-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="00a71-117">Следующий код показывает использование `open` ключевого слова для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="00a71-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="00a71-118">Компилятор F's не испускает ошибку или предупреждение, когда возникают двусмысленности, когда одно и то же имя происходит в более чем одном открытом модуле или пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="00a71-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="00a71-119">При возникновении двусмысленности, F-удается отдавать предпочтение недавно открытому модулю или пространству имен.</span><span class="sxs-lookup"><span data-stu-id="00a71-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="00a71-120">Например, в следующем `empty` коде, `Seq.empty` `empty` означает, даже `List` если `Seq` находится в обоих и модулей.</span><span class="sxs-lookup"><span data-stu-id="00a71-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="00a71-121">Поэтому будьте осторожны при открытии модулей или именных пространств, таких как `List` или `Seq` содержащих членов с одинаковыми именами; вместо этого рассмотрите возможность использования квалифицированных имен.</span><span class="sxs-lookup"><span data-stu-id="00a71-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="00a71-122">Следует избегать любой ситуации, в которой код зависит от порядка импортных деклараций.</span><span class="sxs-lookup"><span data-stu-id="00a71-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="00a71-123">Области имен, открытые по умолчанию</span><span class="sxs-lookup"><span data-stu-id="00a71-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="00a71-124">Некоторые области имен настолько часто используются в коде F,s, что они открываются неявно без явной декларации импорта.</span><span class="sxs-lookup"><span data-stu-id="00a71-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="00a71-125">В следующей таблице показаны пространства имен, открытые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00a71-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="00a71-126">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="00a71-126">Namespace</span></span>|<span data-ttu-id="00a71-127">Описание</span><span class="sxs-lookup"><span data-stu-id="00a71-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="00a71-128">Содержит базовые определения типа F-типа для `int` `float`встроенных типов, таких как и .</span><span class="sxs-lookup"><span data-stu-id="00a71-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="00a71-129">Содержит основные арифметические `+` `*`операции, такие как и .</span><span class="sxs-lookup"><span data-stu-id="00a71-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="00a71-130">Содержит неизменяемые `List` `Array`классы коллекции, такие как и .</span><span class="sxs-lookup"><span data-stu-id="00a71-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="00a71-131">Содержит типы для контрольных конструкций, такие как ленивая оценка и асинхронные рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="00a71-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="00a71-132">Содержит функции для отформатированных io-х, таких как `printf` функция.</span><span class="sxs-lookup"><span data-stu-id="00a71-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="00a71-133">AutoOpen Атрибут</span><span class="sxs-lookup"><span data-stu-id="00a71-133">AutoOpen Attribute</span></span>

<span data-ttu-id="00a71-134">При этом `AutoOpen` атрибут можно применить к сборке, если вы хотите автоматически открыть пространство имен или модуль при упоминании сборки.</span><span class="sxs-lookup"><span data-stu-id="00a71-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="00a71-135">Вы также можете `AutoOpen` применить атрибут к модулю, чтобы автоматически открыть этот модуль при открытии родительского модуля или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="00a71-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="00a71-136">Для получения дополнительной информации [см.](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)</span><span class="sxs-lookup"><span data-stu-id="00a71-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="00a71-137">Атрибут requireQualifiedAccess</span><span class="sxs-lookup"><span data-stu-id="00a71-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="00a71-138">Некоторые модули, записи или `RequireQualifiedAccess` типы соединения могут указывать атрибут.</span><span class="sxs-lookup"><span data-stu-id="00a71-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="00a71-139">При упоминании элементов этих модулей, записей или союзов необходимо использовать квалифицированное имя независимо от того, включаете ли вы объявление об импорте.</span><span class="sxs-lookup"><span data-stu-id="00a71-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="00a71-140">При стратегическом использовании этого атрибута в типах, определяющих часто используемые имена, можно избежать коллизий имен и тем самым сделать код более устойчивым к изменениям в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="00a71-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="00a71-141">Для получения дополнительной [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)информации см.</span><span class="sxs-lookup"><span data-stu-id="00a71-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="00a71-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="00a71-142">See also</span></span>

- [<span data-ttu-id="00a71-143">Ссылка на язык F</span><span class="sxs-lookup"><span data-stu-id="00a71-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="00a71-144">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="00a71-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="00a71-145">Модули</span><span class="sxs-lookup"><span data-stu-id="00a71-145">Modules</span></span>](modules.md)
