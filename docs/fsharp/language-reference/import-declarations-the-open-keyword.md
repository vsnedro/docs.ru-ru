---
title: Объявления импорта. Ключевое слово open
description: 'Сведения об объявлениях импорта F # и о том, как они указывают модуль или пространство имен, на элементы которых можно ссылаться без использования полного имени.'
ms.date: 04/04/2019
ms.openlocfilehash: 2b88427ca92212fb4a7598447dd1a5e12061093a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855092"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="1eaca-103">Объявления импорта: `open` ключевое слово</span><span class="sxs-lookup"><span data-stu-id="1eaca-103">Import declarations: The `open` keyword</span></span>

<span data-ttu-id="1eaca-104">В *объявлении импорта* указан модуль или пространство имен, элементы которого можно ссылаться без использования полного имени.</span><span class="sxs-lookup"><span data-stu-id="1eaca-104">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="1eaca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1eaca-105">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="1eaca-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="1eaca-106">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="1eaca-107">Справочник по API docs.microsoft.com для F # не завершен.</span><span class="sxs-lookup"><span data-stu-id="1eaca-107">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="1eaca-108">Если вы столкнулись с неработающими ссылками, используйте [документацию по основной библиотеке F #](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="1eaca-108">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

<span data-ttu-id="1eaca-109">Создание ссылки на код с помощью полного пространства имен или пути к модулю каждый раз может создать код, который трудно писать, читать и обслуживать.</span><span class="sxs-lookup"><span data-stu-id="1eaca-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="1eaca-110">Вместо этого можно использовать `open` ключевое слово для часто используемых модулей и пространств имен, чтобы при ссылке на член этого модуля или пространства имен можно было использовать краткую форму имени вместо полного имени.</span><span class="sxs-lookup"><span data-stu-id="1eaca-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="1eaca-111">Это ключевое слово похоже на `using` ключевое слово в C#, `using namespace` в Visual C++ и `Imports` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1eaca-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="1eaca-112">Предоставленный модуль или пространство имен должен находиться в том же проекте или в проекте или сборке, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="1eaca-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="1eaca-113">Если это не так, можно добавить ссылку на проект или использовать `-reference` параметр командной строки (или его сокращение `-r` ).</span><span class="sxs-lookup"><span data-stu-id="1eaca-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="1eaca-114">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="1eaca-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="1eaca-115">Объявление импорта делает имена доступными в коде, который следует за объявлением, вплоть до конца включающего пространства имен, модуля или файла.</span><span class="sxs-lookup"><span data-stu-id="1eaca-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="1eaca-116">При использовании нескольких объявлений импорта они должны отображаться в разных строках.</span><span class="sxs-lookup"><span data-stu-id="1eaca-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="1eaca-117">В следующем коде показано использование `open` ключевого слова для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="1eaca-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="1eaca-118">Компилятор F # не выдает ошибку или предупреждение, если неоднозначность возникает, когда одно и то же имя встречается в нескольких открытых модулях или пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="1eaca-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="1eaca-119">При возникновении неоднозначности F # дает предпочтение более последнему открытому модулю или пространству имен.</span><span class="sxs-lookup"><span data-stu-id="1eaca-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="1eaca-120">Например, в следующем коде `empty` это означает, что, несмотря на то, что находится `Seq.empty` `empty` в `List` обоих `Seq` модулях и.</span><span class="sxs-lookup"><span data-stu-id="1eaca-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="1eaca-121">Поэтому будьте внимательны при открытии модулей или пространств имен, таких как `List` или `Seq` , которые содержат элементы с одинаковыми именами. вместо этого рекомендуется использовать полные имена.</span><span class="sxs-lookup"><span data-stu-id="1eaca-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="1eaca-122">Следует избегать ситуаций, в которых код зависит от порядка объявлений импорта.</span><span class="sxs-lookup"><span data-stu-id="1eaca-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="1eaca-123">Пространства имен, открытые по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1eaca-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="1eaca-124">Некоторые пространства имен часто используются в коде F #, поэтому они открыты неявно без необходимости явного объявления импорта.</span><span class="sxs-lookup"><span data-stu-id="1eaca-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="1eaca-125">В следующей таблице показаны пространства имен, открытые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1eaca-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="1eaca-126">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1eaca-126">Namespace</span></span>|<span data-ttu-id="1eaca-127">Описание</span><span class="sxs-lookup"><span data-stu-id="1eaca-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="1eaca-128">Содержит основные определения типов F # для встроенных типов, таких как `int` и `float` .</span><span class="sxs-lookup"><span data-stu-id="1eaca-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="1eaca-129">Содержит базовые арифметические операции, такие как `+` и `*` .</span><span class="sxs-lookup"><span data-stu-id="1eaca-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="1eaca-130">Содержит неизменяемые классы коллекций, такие как `List` и `Array` .</span><span class="sxs-lookup"><span data-stu-id="1eaca-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="1eaca-131">Содержит типы для конструкций элементов управления, таких как отложенная оценка и асинхронные рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="1eaca-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="1eaca-132">Содержит функции для форматированного ввода-вывода, например `printf` функции.</span><span class="sxs-lookup"><span data-stu-id="1eaca-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="1eaca-133">Атрибут Автооткрытия</span><span class="sxs-lookup"><span data-stu-id="1eaca-133">AutoOpen Attribute</span></span>

<span data-ttu-id="1eaca-134">Атрибут можно применить `AutoOpen` к сборке, если необходимо автоматически открывать пространство имен или модуль при ссылке на сборку.</span><span class="sxs-lookup"><span data-stu-id="1eaca-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="1eaca-135">Можно также применить `AutoOpen` атрибут к модулю для автоматического открытия этого модуля при открытии родительского модуля или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1eaca-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="1eaca-136">Дополнительные сведения см. в разделе [класс Core. AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="1eaca-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="1eaca-137">Атрибут Рекуирекуалифиедакцесс</span><span class="sxs-lookup"><span data-stu-id="1eaca-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="1eaca-138">Некоторые модули, записи или типы объединений могут задавать `RequireQualifiedAccess` атрибут.</span><span class="sxs-lookup"><span data-stu-id="1eaca-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="1eaca-139">При ссылке на элементы этих модулей, записей или объединений необходимо использовать полное имя независимо от того, включено ли объявление импорта.</span><span class="sxs-lookup"><span data-stu-id="1eaca-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="1eaca-140">Если этот атрибут используется стратегически для типов, определяющих часто используемые имена, можно избежать конфликтов имен и, таким образом, сделать код более устойчивым к изменениям в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="1eaca-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="1eaca-141">Дополнительные сведения см. в разделе [класс Core. рекуирекуалифиедакцессаттрибуте](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="1eaca-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="1eaca-142">См. также</span><span class="sxs-lookup"><span data-stu-id="1eaca-142">See also</span></span>

- [<span data-ttu-id="1eaca-143">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="1eaca-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="1eaca-144">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="1eaca-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="1eaca-145">Модули</span><span class="sxs-lookup"><span data-stu-id="1eaca-145">Modules</span></span>](modules.md)
