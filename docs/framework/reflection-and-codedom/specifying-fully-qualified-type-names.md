---
title: Указание полных имен типов
description: Для выполнения операций отражения следует использовать полные имена типов, которые состоят из спецификаций имен сборок, спецификаций пространств имен и имен типов.
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
ms.openlocfilehash: ff33b6abd31a82c6b80aa794564c5c48648cde63
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865233"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="3a1ca-103">Определение полных имен типов</span><span class="sxs-lookup"><span data-stu-id="3a1ca-103">Specifying fully qualified type names</span></span>

<span data-ttu-id="3a1ca-104">Для выполнения различных операций отражения необходимо задавать имена типов.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-104">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="3a1ca-105">Полное имя типа состоит из спецификации имени сборки, спецификации пространства имен и имени типа.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-105">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="3a1ca-106">Спецификации имен типов используются такими методами, как <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> и <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-106">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>

## <a name="grammar-for-type-names"></a><span data-ttu-id="3a1ca-107">Грамматика для имен типов</span><span class="sxs-lookup"><span data-stu-id="3a1ca-107">Grammar for type names</span></span>

 <span data-ttu-id="3a1ca-108">Эта грамматика определяет синтаксис формальных языков.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-108">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="3a1ca-109">Приведенная ниже таблица содержит список лексических правил, описывающих порядок распознавания допустимых входных данных.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-109">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="3a1ca-110">Терминальные слова (элементы, дальнейшее сокращение которых невозможно) отображаются прописными буквами.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-110">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="3a1ca-111">Нетерминальные слова (допускающие сокращение) содержат прописные буквы вместе со строчными или заключены в одинарные кавычки, причем одинарные кавычки (') не являются частью синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-111">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="3a1ca-112">Символ вертикальной черты (&#124;) обозначает правила, у которых есть подправила.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-112">The pipe character (&#124;) denotes rules that have subrules.</span></span>

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a><span data-ttu-id="3a1ca-113">Определение специальных символов</span><span class="sxs-lookup"><span data-stu-id="3a1ca-113">Specifying special characters</span></span>

<span data-ttu-id="3a1ca-114">В имени типа IDENTIFIER — любое допустимое имя, определяемое правилами языка.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-114">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>

<span data-ttu-id="3a1ca-115">Приведенные ниже лексемы при использовании в составе IDENTIFIER отделяются escape-символом в виде обратной косой черты (\\).</span><span class="sxs-lookup"><span data-stu-id="3a1ca-115">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>

|<span data-ttu-id="3a1ca-116">Токен</span><span class="sxs-lookup"><span data-stu-id="3a1ca-116">Token</span></span>|<span data-ttu-id="3a1ca-117">Значение</span><span class="sxs-lookup"><span data-stu-id="3a1ca-117">Meaning</span></span>|
|-----------|-------------|
|<span data-ttu-id="3a1ca-118">\\,</span><span class="sxs-lookup"><span data-stu-id="3a1ca-118">\\,</span></span>|<span data-ttu-id="3a1ca-119">Разделитель сборок.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-119">Assembly separator.</span></span>|
|\\+|<span data-ttu-id="3a1ca-120">Разделитель вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-120">Nested type separator.</span></span>|
|\\&|<span data-ttu-id="3a1ca-121">Ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-121">Reference type.</span></span>|
|\\*|<span data-ttu-id="3a1ca-122">Тип указателя.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-122">Pointer type.</span></span>|
|<span data-ttu-id="3a1ca-123">\\[</span><span class="sxs-lookup"><span data-stu-id="3a1ca-123">\\[</span></span>|<span data-ttu-id="3a1ca-124">Ограничитель размерности массива.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-124">Array dimension delimiter.</span></span>|
|<span data-ttu-id="3a1ca-125">\\]</span><span class="sxs-lookup"><span data-stu-id="3a1ca-125">\\]</span></span>|<span data-ttu-id="3a1ca-126">Ограничитель размерности массива.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-126">Array dimension delimiter.</span></span>|
|<span data-ttu-id="3a1ca-127">\\.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-127">\\.</span></span>|<span data-ttu-id="3a1ca-128">Обратная косая черта ставится перед точкой только в том случае, если точка включена в спецификацию массива.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-128">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="3a1ca-129">Для точек в спецификации NamespaceSpec обратная косая черта не требуется.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-129">Periods in NamespaceSpec do not take the backslash.</span></span>|
|<span data-ttu-id="3a1ca-130">\\\|Обратная косая черта, если она используется в качестве строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-130">\\\|Backslash when needed as a string literal.</span></span>|

<span data-ttu-id="3a1ca-131">Следует заметить, что для всех компонентов спецификации TypeSpec, кроме AssemblyNameSpec, пробелы существенны.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-131">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="3a1ca-132">В AssemblyNameSpec пробелы перед разделителем "," существенны, а пробелы после "," игнорируются.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-132">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>

<span data-ttu-id="3a1ca-133">Классы отражения, такие как <xref:System.Type.FullName%2A?displayProperty=nameWithType>, возвращают искаженное имя, которое можно использовать при вызове метода <xref:System.Type.GetType%2A>, например `MyType.GetType(myType.FullName)`.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-133">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>

<span data-ttu-id="3a1ca-134">Например, полное имя типа может иметь следующий вид: `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-134">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>

<span data-ttu-id="3a1ca-135">Если бы использовалось пространство имен `Ozzy.Out+Back`, перед плюсом должна была бы стоять обратная косая черта.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-135">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="3a1ca-136">В противном случае синтаксический анализатор интерпретировал бы плюс как разделитель вложений.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-136">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="3a1ca-137">Отражение порождает эту строку в следующем виде: `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-137">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>

## <a name="specifying-assembly-names"></a><span data-ttu-id="3a1ca-138">Определение имен сборок</span><span class="sxs-lookup"><span data-stu-id="3a1ca-138">Specifying assembly names</span></span>

<span data-ttu-id="3a1ca-139">Единственным обязательным компонентом спецификации имени сборки является текстовое имя сборки (IDENTIFIER).</span><span class="sxs-lookup"><span data-stu-id="3a1ca-139">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="3a1ca-140">За ним может следовать список разделенных запятыми пар "свойство/значение", как показано в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-140">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="3a1ca-141">Имя IDENTIFIER должно удовлетворять правилам именования файлов.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-141">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="3a1ca-142">Регистр символов в имени IDENTIFIER не учитывается.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-142">The IDENTIFIER is case-insensitive.</span></span>

|<span data-ttu-id="3a1ca-143">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-143">Property name</span></span>|<span data-ttu-id="3a1ca-144">Описание</span><span class="sxs-lookup"><span data-stu-id="3a1ca-144">Description</span></span>|<span data-ttu-id="3a1ca-145">Допустимые значения</span><span class="sxs-lookup"><span data-stu-id="3a1ca-145">Allowable values</span></span>|
|-------------------|-----------------|----------------------|
|<span data-ttu-id="3a1ca-146">**Версия**</span><span class="sxs-lookup"><span data-stu-id="3a1ca-146">**Version**</span></span>|<span data-ttu-id="3a1ca-147">Номер версии сборки</span><span class="sxs-lookup"><span data-stu-id="3a1ca-147">Assembly version number</span></span>|<span data-ttu-id="3a1ca-148">*Major.Minor.Build.Revision*, где *Major*, *Minor*, *Build* и *Revision* являются целочисленными значениями в диапазоне от 0 до 65 535 включительно.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-148">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|
|<span data-ttu-id="3a1ca-149">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="3a1ca-149">**PublicKey**</span></span>|<span data-ttu-id="3a1ca-150">Полный открытый ключ</span><span class="sxs-lookup"><span data-stu-id="3a1ca-150">Full public key</span></span>|<span data-ttu-id="3a1ca-151">Строковое значение полного открытого ключа в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-151">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="3a1ca-152">Чтобы явным образом описать сборку как закрытую, необходимо задать пустую ссылку (**Nothing** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="3a1ca-152">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="3a1ca-153">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="3a1ca-153">**PublicKeyToken**</span></span>|<span data-ttu-id="3a1ca-154">Токен открытого ключа (8-байтовый хэш-код полного открытого ключа)</span><span class="sxs-lookup"><span data-stu-id="3a1ca-154">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="3a1ca-155">Строковое значение токена открытого ключа в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-155">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="3a1ca-156">Чтобы явным образом описать сборку как закрытую, необходимо задать пустую ссылку (**Nothing** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="3a1ca-156">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="3a1ca-157">**Язык и региональные параметры**</span><span class="sxs-lookup"><span data-stu-id="3a1ca-157">**Culture**</span></span>|<span data-ttu-id="3a1ca-158">Язык и региональные параметры сборки</span><span class="sxs-lookup"><span data-stu-id="3a1ca-158">Assembly culture</span></span>|<span data-ttu-id="3a1ca-159">Язык и региональные параметры сборки в формате RFC-1766 или нейтральная среда для сборок, независимых от языков (не сопутствующих).</span><span class="sxs-lookup"><span data-stu-id="3a1ca-159">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|
|<span data-ttu-id="3a1ca-160">**Пользовательский**</span><span class="sxs-lookup"><span data-stu-id="3a1ca-160">**Custom**</span></span>|<span data-ttu-id="3a1ca-161">Пользовательский BLOB-объект.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-161">Custom binary large object (BLOB).</span></span> <span data-ttu-id="3a1ca-162">В настоящее время используется только в сборках, созданных [генератором образов в машинном коде (Ngen)](../tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="3a1ca-162">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="3a1ca-163">Настраиваемая строка, с помощью которой генератор образов в машинном коде уведомляет кэш сборок о том, что устанавливаемая сборка является образом в машинном коде и должна быть установлена в кэш образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-163">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="3a1ca-164">Также называется zap-строкой.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-164">Also called a zap string.</span></span>|

<span data-ttu-id="3a1ca-165">В приведенном ниже примере демонстрируется спецификация **AssemblyName** для сборки с простым именем, а также заданными по умолчанию языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-165">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>

```csharp
com.microsoft.crypto, Culture=""
```

<span data-ttu-id="3a1ca-166">В приведенном ниже примере показана полностью определенная ссылка на сборку со строгим именем, для которой установлены язык и региональные параметры —"en".</span><span class="sxs-lookup"><span data-stu-id="3a1ca-166">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

<span data-ttu-id="3a1ca-167">В каждом из приведенных ниже примеров приводится частично определенное имя **AssemblyName**, которое подходит для сборки как с простым, так и со строгим именем.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-167">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

<span data-ttu-id="3a1ca-168">В каждом из приведенных ниже примеров приводится частично определенное имя **AssemblyName**, которое подходит только для сборки с простым именем.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

<span data-ttu-id="3a1ca-169">В каждом из приведенных ниже примеров приводится частично определенное имя **AssemblyName**, которое подходит только для сборки со строгим именем.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-169">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a><span data-ttu-id="3a1ca-170">Определение универсальных типов</span><span class="sxs-lookup"><span data-stu-id="3a1ca-170">Specifying generic types</span></span>

<span data-ttu-id="3a1ca-171">SimpleTypeSpec\`NUMBER представляет открытый универсальный тип с параметрами универсального типа от 1 до *n*.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-171">SimpleTypeSpec\`NUMBER represents an open generic type with from 1 to *n* generic type parameters.</span></span> <span data-ttu-id="3a1ca-172">Например, чтобы получить ссылку на List\<T> для открытого универсального типа или List\<String> для закрытого универсального типа, используйте ``Type.GetType("System.Collections.Generic.List`1")``. Чтобы получить ссылку на Dictionary\<TKey,TValue> для универсального типа, используйте ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-172">For example, to get reference to the open generic type List\<T> or the closed generic type List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")`` To get a reference to the generic type Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span></span>

## <a name="specifying-pointers"></a><span data-ttu-id="3a1ca-173">Определение указателей</span><span class="sxs-lookup"><span data-stu-id="3a1ca-173">Specifying pointers</span></span>

<span data-ttu-id="3a1ca-174">Спецификация SimpleTypeSpec\* представляет неуправляемый указатель.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-174">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="3a1ca-175">Например, для получения указателя на тип MyType можно использовать вызов метода `Type.GetType("MyType*")`.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-175">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="3a1ca-176">Для получения указателя на указатель на тип MyType используется вызов `Type.GetType("MyType**")`.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-176">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>

## <a name="specifying-references"></a><span data-ttu-id="3a1ca-177">Определение ссылок</span><span class="sxs-lookup"><span data-stu-id="3a1ca-177">Specifying references</span></span>

<span data-ttu-id="3a1ca-178">Спецификация SimpleTypeSpec & представляет управляемый указатель или ссылку.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-178">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="3a1ca-179">Например, для получения ссылки на тип MyType можно использовать вызов `Type.GetType("MyType &")`.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-179">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="3a1ca-180">Обратите внимание, что ссылки, в отличие от указателей, ограничены одним уровнем.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-180">Note that unlike pointers, references are limited to one level.</span></span>

## <a name="specifying-arrays"></a><span data-ttu-id="3a1ca-181">Определение массивов</span><span class="sxs-lookup"><span data-stu-id="3a1ca-181">Specifying arrays</span></span>

<span data-ttu-id="3a1ca-182">В БНФ спецификация ReflectionEmitDimension применяется только в отношении неполных определений типов, полученных с использованием метода <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-182">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3a1ca-183">К неполным определениям типов относятся объекты <xref:System.Reflection.Emit.TypeBuilder>, созданные с помощью метода <xref:System.Reflection.Emit?displayProperty=nameWithType>, но для которых не был выполнен вызов <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-183">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="3a1ca-184">Спецификацию ReflectionDimension можно использовать для получения любого полного определения типа, то есть типа, который уже загружен.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-184">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>

<span data-ttu-id="3a1ca-185">Доступ к массиву при отражении осуществляется путем указания размерности массива:</span><span class="sxs-lookup"><span data-stu-id="3a1ca-185">Arrays are accessed in reflection by specifying the rank of the array:</span></span>

- <span data-ttu-id="3a1ca-186">`Type.GetType("MyArray[]")` — получение одномерного массива с нижней границей 0.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-186">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>

- <span data-ttu-id="3a1ca-187">`Type.GetType("MyArray[*]")` — получение одномерного массива с неизвестной нижней границей.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-187">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>
- <span data-ttu-id="3a1ca-188">`Type.GetType("MyArray[][]")` — получение массива двумерных массивов.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-188">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>

- <span data-ttu-id="3a1ca-189">`Type.GetType("MyArray[*,*]")` и `Type.GetType("MyArray[,]")` — получение прямоугольного двумерного массива с неизвестными нижними границами.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-189">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>

<span data-ttu-id="3a1ca-190">Обратите внимание, что с точки зрения среды выполнения `MyArray[] != MyArray[*]`, но для многомерных массивов эти обозначения эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-190">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="3a1ca-191">Другими словами, выражение `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` дает значение **true**.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-191">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>

<span data-ttu-id="3a1ca-192">Для метода **ModuleBuilder.GetType**`MyArray[0..5]` указывает одномерный массив размером 6 с нижней границей 0.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-192">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="3a1ca-193">`MyArray[4…]` указывает одномерный массив неизвестного размера с нижней границей 4.</span><span class="sxs-lookup"><span data-stu-id="3a1ca-193">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a1ca-194">См. также</span><span class="sxs-lookup"><span data-stu-id="3a1ca-194">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3a1ca-195">Просмотр сведений о типах</span><span class="sxs-lookup"><span data-stu-id="3a1ca-195">Viewing Type Information</span></span>](viewing-type-information.md)
