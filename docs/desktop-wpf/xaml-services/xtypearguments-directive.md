---
title: Директива x:TypeArguments
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 430ab65af52282ccb1d429cd2523efe213f13609
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543555"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="37ecb-102">Директива x:TypeArguments</span><span class="sxs-lookup"><span data-stu-id="37ecb-102">x:TypeArguments Directive</span></span>

<span data-ttu-id="37ecb-103">Передает ограничивающие аргументы типа универсального класса в конструктор универсального типа.</span><span class="sxs-lookup"><span data-stu-id="37ecb-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="37ecb-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="37ecb-104">XAML Attribute Usage</span></span>

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="37ecb-105">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="37ecb-105">XAML Values</span></span>

|||
|-|-|
|`object`|<span data-ttu-id="37ecb-106">Объявление объектного элемента типа XAML, который поддерживается универсальным типом CLR.</span><span class="sxs-lookup"><span data-stu-id="37ecb-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="37ecb-107">Если `object` ссылается на тип XAML, который не относится к пространству имен XAML по умолчанию, `object` требуется префикс, указывающий пространство имен XAML, где `object` существует.</span><span class="sxs-lookup"><span data-stu-id="37ecb-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|
|`typeString`|<span data-ttu-id="37ecb-108">Строка, объявляющая одно или несколько имен типов XAML в виде строк, которые предоставляют аргументы типа для универсального типа CLR.</span><span class="sxs-lookup"><span data-stu-id="37ecb-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="37ecb-109">Дополнительные сведения о синтаксисе см. в разделе Примечания.</span><span class="sxs-lookup"><span data-stu-id="37ecb-109">See Remarks for additional syntax notes.</span></span>|

## <a name="remarks"></a><span data-ttu-id="37ecb-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="37ecb-110">Remarks</span></span>

<span data-ttu-id="37ecb-111">В большинстве случаев типы XAML, используемые в качестве информационного элемента в `typeString` строке, являются префиксами.</span><span class="sxs-lookup"><span data-stu-id="37ecb-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="37ecb-112">Типичные типы универсальных ограничений CLR (например, <xref:System.Int32> и <xref:System.String> ) поступают из библиотек базовых классов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="37ecb-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="37ecb-113">Эти библиотеки не сопоставляются с типичными пространствами имен XAML по умолчанию для конкретной платформы, поэтому для использования XAML требуется сопоставление префикса.</span><span class="sxs-lookup"><span data-stu-id="37ecb-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>

<span data-ttu-id="37ecb-114">Можно указать несколько имен типов XAML, используя разделитель-запятую.</span><span class="sxs-lookup"><span data-stu-id="37ecb-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>

<span data-ttu-id="37ecb-115">Если универсальные ограничения сами по себе используют универсальные типы, аргументы типа вложенного ограничения могут содержаться в круглых скобках ().</span><span class="sxs-lookup"><span data-stu-id="37ecb-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>

<span data-ttu-id="37ecb-116">Обратите внимание, что это определение `x:TypeArguments` характерно для служб XAML .NET и использует резервное копирование среды CLR.</span><span class="sxs-lookup"><span data-stu-id="37ecb-116">Note that this definition of `x:TypeArguments` is specific to .NET XAML Services and using CLR backing.</span></span> <span data-ttu-id="37ecb-117">Определение уровня языка можно найти в [ \[ \] разделе 5.3.11 в MS-XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="37ecb-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="usage-examples"></a><span data-ttu-id="37ecb-118">Примеры использования</span><span class="sxs-lookup"><span data-stu-id="37ecb-118">Usage Examples</span></span>

<span data-ttu-id="37ecb-119">В этих примерах предполагается, что объявляются следующие определения пространства имен XAML:</span><span class="sxs-lookup"><span data-stu-id="37ecb-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a><span data-ttu-id="37ecb-120">Числ\<String></span><span class="sxs-lookup"><span data-stu-id="37ecb-120">List\<String></span></span>

<span data-ttu-id="37ecb-121">`<scg:List x:TypeArguments="sys:String" ...>` создает новый объект <xref:System.Collections.Generic.List%601> с <xref:System.String> аргументом типа.</span><span class="sxs-lookup"><span data-stu-id="37ecb-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>

### <a name="dictionarystringstring"></a><span data-ttu-id="37ecb-122">Dictionary\<String,String></span><span class="sxs-lookup"><span data-stu-id="37ecb-122">Dictionary\<String,String></span></span>

<span data-ttu-id="37ecb-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` создает новый экземпляр <xref:System.Collections.Generic.Dictionary%602> с двумя <xref:System.String> аргументами типа.</span><span class="sxs-lookup"><span data-stu-id="37ecb-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>

### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="37ecb-124">Очередь<KeyValuePair\<String,String>></span><span class="sxs-lookup"><span data-stu-id="37ecb-124">Queue<KeyValuePair\<String,String>></span></span>

<span data-ttu-id="37ecb-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` создает новый объект <xref:System.Collections.Generic.Queue%601> , имеющий ограничение <xref:System.Collections.Generic.KeyValuePair%602> с аргументами типа внутреннего ограничения <xref:System.String> и <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="37ecb-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="37ecb-126">Общие сведения об использовании XAML в XAML 2006 и WPF</span><span class="sxs-lookup"><span data-stu-id="37ecb-126">XAML 2006 and WPF Generic XAML Usages</span></span>

<span data-ttu-id="37ecb-127">Для использования XAML 2006 и XAML, используемого для приложений WPF, в целом существуют следующие ограничения на `x:TypeArguments` Использование универсального типа из XAML.</span><span class="sxs-lookup"><span data-stu-id="37ecb-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>

- <span data-ttu-id="37ecb-128">Только корневой элемент файла XAML может поддерживать универсальное использование XAML, которое ссылается на универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="37ecb-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>

- <span data-ttu-id="37ecb-129">Корневой элемент должен сопоставляться с универсальным типом по крайней мере с одним аргументом типа.</span><span class="sxs-lookup"><span data-stu-id="37ecb-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="37ecb-130">Например, <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="37ecb-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="37ecb-131">Страничные функции являются основным сценарием для поддержки общего использования XAML в WPF.</span><span class="sxs-lookup"><span data-stu-id="37ecb-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>

- <span data-ttu-id="37ecb-132">Элемент объекта XAML корневого элемента для универсального класса должен также объявлять разделяемый класс с помощью `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="37ecb-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="37ecb-133">Это справедливо даже при определении действия построения WPF.</span><span class="sxs-lookup"><span data-stu-id="37ecb-133">This is true even if defining a WPF build action.</span></span>

- <span data-ttu-id="37ecb-134">`x:TypeArguments` невозможно сослаться на вложенные универсальные ограничения.</span><span class="sxs-lookup"><span data-stu-id="37ecb-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="37ecb-135">XAML 2009 или XAML 2006 без зависимостей WPF 3,0 или WPF 3,5</span><span class="sxs-lookup"><span data-stu-id="37ecb-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>

<span data-ttu-id="37ecb-136">В службах .NET XAML для XAML 2006 или XAML 2009 ограничения, связанные с WPF, для универсального использования XAML нестрогие.</span><span class="sxs-lookup"><span data-stu-id="37ecb-136">In .NET XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="37ecb-137">Можно создать экземпляр универсального элемента объекта в любой позиции в разметке XAML, которую может поддерживать система резервных типов и модель объектов.</span><span class="sxs-lookup"><span data-stu-id="37ecb-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>

<span data-ttu-id="37ecb-138">При использовании XAML 2009 вместо сопоставления базовых типов CLR для получения типов XAML для общих языковых примитивов можно использовать [встроенные типы для общих примитивов языка XAML](types-for-primitives.md) в качестве информационных элементов в `typeString` .</span><span class="sxs-lookup"><span data-stu-id="37ecb-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](types-for-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="37ecb-139">Например, можно объявить следующее (сопоставление префиксов не показано, но x является пространством имен XAML языка XAML для XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="37ecb-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

<span data-ttu-id="37ecb-140">В WPF и при нацеливании на .NET Framework 4 или .NET Core 3,0 (или более поздней версии) можно использовать функции XAML 2009 вместе с, `x:TypeArguments` но только для свободного XAML (XAML, не скомпилированный разметкой).</span><span class="sxs-lookup"><span data-stu-id="37ecb-140">In WPF and when targeting .NET Framework 4 or .NET Core 3.0 (or later), you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="37ecb-141">Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="37ecb-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="37ecb-142">Если необходимо скомпилировать XAML в разметку, необходимо использовать ограничения, указанные в разделе [об использовании xaml 2006 и WPF Generic XAML](#xaml-2006-and-wpf-generic-xaml-usages) .</span><span class="sxs-lookup"><span data-stu-id="37ecb-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the [XAML 2006 and WPF Generic XAML Usages](#xaml-2006-and-wpf-generic-xaml-usages) section.</span></span> <span data-ttu-id="37ecb-143">BAML поддерживается только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="37ecb-143">BAML is only supported in .NET Framework.</span></span>

## <a name="see-also"></a><span data-ttu-id="37ecb-144">См. также</span><span class="sxs-lookup"><span data-stu-id="37ecb-144">See also</span></span>

- [<span data-ttu-id="37ecb-145">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="37ecb-145">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="37ecb-146">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="37ecb-146">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="37ecb-147">Встроенные типы для общих примитивов языка XAML</span><span class="sxs-lookup"><span data-stu-id="37ecb-147">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
- [<span data-ttu-id="37ecb-148">Универсальные шаблоны в XAML</span><span class="sxs-lookup"><span data-stu-id="37ecb-148">Generics in XAML</span></span>](generics.md)
