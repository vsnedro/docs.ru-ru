---
title: Список атрибутов
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: e566239c56efa8ca8e83bff92486fec4c434e92b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874737"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="ce9ec-102">Список атрибутов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce9ec-102">Attribute List (Visual Basic)</span></span>

<span data-ttu-id="ce9ec-103">Задает атрибуты, применяемые к объявленному программному элементу.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="ce9ec-104">Несколько атрибутов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="ce9ec-105">Ниже приведен синтаксис для одного атрибута.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce9ec-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce9ec-106">Syntax</span></span>  
  
```vb  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ce9ec-107">Компоненты</span><span class="sxs-lookup"><span data-stu-id="ce9ec-107">Parts</span></span>  

|||
|---|---|
|`attributemodifier`|<span data-ttu-id="ce9ec-108">Требуется для атрибутов, применяемых в начале исходного файла.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="ce9ec-109">Может быть [сборкой](../modifiers/assembly.md) или [модулем](../modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="ce9ec-109">Can be [Assembly](../modifiers/assembly.md) or [Module](../modifiers/module-keyword.md).</span></span>|
|`attributename`| <span data-ttu-id="ce9ec-110">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-110">Required.</span></span> <span data-ttu-id="ce9ec-111">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-111">Name of the attribute.</span></span>|
|`attributearguments`|<span data-ttu-id="ce9ec-112">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-112">Optional.</span></span> <span data-ttu-id="ce9ec-113">Список позиций аргументов для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="ce9ec-114">Несколько аргументов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-114">Multiple arguments are separated by commas.</span></span>|
|`attributeinitializer`|<span data-ttu-id="ce9ec-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-115">Optional.</span></span> <span data-ttu-id="ce9ec-116">Список инициализаторов переменных или свойств для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="ce9ec-117">Несколько инициализаторов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-117">Multiple initializers are separated by commas.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="ce9ec-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="ce9ec-118">Remarks</span></span>  

 <span data-ttu-id="ce9ec-119">Можно применить один или несколько атрибутов практически к любому элементу программирования (типам, процедурам, свойствам и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ce9ec-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="ce9ec-120">Атрибуты отображаются в метаданных сборки, и они могут помочь добавить заметки в код или указать способ использования определенного программного элемента.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="ce9ec-121">Можно применять атрибуты, определенные Visual Basic и .NET Framework, а также определять собственные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="ce9ec-122">Дополнительные сведения об использовании атрибутов см. в разделе [Общие сведения об атрибутах](../../programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="ce9ec-122">For more information on when to use attributes, see [Attributes overview](../../programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="ce9ec-123">Дополнительные сведения об именах атрибутов см. в разделе [Имена объявленных элементов](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="ce9ec-123">For information on attribute names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ce9ec-124">Правила</span><span class="sxs-lookup"><span data-stu-id="ce9ec-124">Rules</span></span>  
  
- <span data-ttu-id="ce9ec-125">**Размещаем.**</span><span class="sxs-lookup"><span data-stu-id="ce9ec-125">**Placement.**</span></span> <span data-ttu-id="ce9ec-126">К большинству объявленных программных элементов можно применять атрибуты.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="ce9ec-127">Чтобы применить один или несколько атрибутов, поместите *блок атрибутов* в начало объявления элемента.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="ce9ec-128">Каждая запись в списке атрибутов указывает атрибут, который вы хотите применить, и модификатор и аргументы, используемые для этого вызова атрибута.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
- <span data-ttu-id="ce9ec-129">**Угловые скобки.**</span><span class="sxs-lookup"><span data-stu-id="ce9ec-129">**Angle Brackets.**</span></span> <span data-ttu-id="ce9ec-130">При указании списка атрибутов необходимо заключить его в угловые скобки (" `<` " и " `>` ").</span><span class="sxs-lookup"><span data-stu-id="ce9ec-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
- <span data-ttu-id="ce9ec-131">**Часть объявления.**</span><span class="sxs-lookup"><span data-stu-id="ce9ec-131">**Part of the Declaration.**</span></span> <span data-ttu-id="ce9ec-132">Атрибут должен быть частью объявления элемента, а не отдельной инструкции.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="ce9ec-133">`_`Для расширения оператора объявления на несколько строк исходного кода можно использовать последовательность продолжения строки ("").</span><span class="sxs-lookup"><span data-stu-id="ce9ec-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
- <span data-ttu-id="ce9ec-134">**Модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="ce9ec-134">**Modifiers.**</span></span> <span data-ttu-id="ce9ec-135">Модификатор атрибута ( `Assembly` или `Module` ) необходим для каждого атрибута, применяемого к программному элементу в начале исходного файла.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="ce9ec-136">Использование модификаторов атрибутов не допускается для атрибутов, применяемых к элементам, которые не находятся в начале исходного файла.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
- <span data-ttu-id="ce9ec-137">**Даваемых.**</span><span class="sxs-lookup"><span data-stu-id="ce9ec-137">**Arguments.**</span></span> <span data-ttu-id="ce9ec-138">Все позиционированные аргументы для атрибута должны предшествовать любым инициализаторам переменных или свойств.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce9ec-139">Пример</span><span class="sxs-lookup"><span data-stu-id="ce9ec-139">Example</span></span>  

 <span data-ttu-id="ce9ec-140">В следующем примере атрибут применяется <xref:System.Runtime.InteropServices.DllImportAttribute> к скелетному определению `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="ce9ec-141"><xref:System.Runtime.InteropServices.DllImportAttribute> Указывает, что процедура с атрибутом представляет точку входа в неуправляемой библиотеке динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="ce9ec-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="ce9ec-142">Атрибут предоставляет имя библиотеки DLL в качестве аргумента, а другие сведения — как Инициализаторы переменных.</span><span class="sxs-lookup"><span data-stu-id="ce9ec-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce9ec-143">См. также</span><span class="sxs-lookup"><span data-stu-id="ce9ec-143">See also</span></span>

- [<span data-ttu-id="ce9ec-144">Сборка</span><span class="sxs-lookup"><span data-stu-id="ce9ec-144">Assembly</span></span>](../modifiers/assembly.md)
- [<span data-ttu-id="ce9ec-145">Модуль \<keyword></span><span class="sxs-lookup"><span data-stu-id="ce9ec-145">Module \<keyword></span></span>](../modifiers/module-keyword.md)
- [<span data-ttu-id="ce9ec-146">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="ce9ec-146">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="ce9ec-147">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="ce9ec-147">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
