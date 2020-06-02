---
title: Имена классов, структур и интерфейсов
description: Используйте эти рекомендации для именования классов, структур и интерфейсов в рамках рекомендаций по проектированию библиотек, расширяющих и взаимодействующих с библиотеками .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: b9de9329cc8e1bfc47a46523c7119bb3b2c244d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290218"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="66dee-103">Имена классов, структур и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="66dee-103">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="66dee-104">Приведенные ниже рекомендации по именованию применяются к общему именованию типов.</span><span class="sxs-lookup"><span data-stu-id="66dee-104">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="66dee-105">✔️ имена классов и структур с существительными или субстантивные словосочетаниями с помощью Паскалкасинг.</span><span class="sxs-lookup"><span data-stu-id="66dee-105">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="66dee-106">Это отличает имена типов от методов, названных с помощью фраз глагола.</span><span class="sxs-lookup"><span data-stu-id="66dee-106">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="66dee-107">✔️ ИСПОЛЬЗОВАТЬ именованные интерфейсы с фразами прилагательных или иногда с существительными или фразами с существительными.</span><span class="sxs-lookup"><span data-stu-id="66dee-107">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="66dee-108">Существительные и фразы существительное следует использовать редко, и они могут указывать, что тип должен быть абстрактным классом, а не интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="66dee-108">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="66dee-109">❌НЕ присваивайте имена классов префиксом (например, "C").</span><span class="sxs-lookup"><span data-stu-id="66dee-109">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="66dee-110">✔️ Рекомендуется завершать имена производных классов именем базового класса.</span><span class="sxs-lookup"><span data-stu-id="66dee-110">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="66dee-111">Это очень понятное и понятное отношение.</span><span class="sxs-lookup"><span data-stu-id="66dee-111">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="66dee-112">Вот несколько примеров этого кода: `ArgumentOutOfRangeException` , который является разновидностью `Exception` , и `SerializableAttribute` , которая является разновидностью `Attribute` .</span><span class="sxs-lookup"><span data-stu-id="66dee-112">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="66dee-113">Однако важно использовать разумные меры при применении этой рекомендации; Например, `Button` класс является разновидностью `Control` события, хотя `Control` не отображается в его имени.</span><span class="sxs-lookup"><span data-stu-id="66dee-113">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="66dee-114">✔️ префиксы имен интерфейсов с буквой I, чтобы указать, что тип является интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="66dee-114">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="66dee-115">Например, `IComponent` (описательное существительное), `ICustomAttributeProvider` (субстантивные словосочетания) и `IPersistable` (прилагательное) — соответствующие имена интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="66dee-115">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="66dee-116">Как и в случае с другими именами типов, следует избегать сокращений.</span><span class="sxs-lookup"><span data-stu-id="66dee-116">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="66dee-117">✔️ Убедитесь, что имена отличаются только префиксом "I" в имени интерфейса при определении пары "класс — интерфейс", в которой класс является стандартной реализацией интерфейса.</span><span class="sxs-lookup"><span data-stu-id="66dee-117">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="66dee-118">Имена параметров универсального типа</span><span class="sxs-lookup"><span data-stu-id="66dee-118">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="66dee-119">Универсальные шаблоны были добавлены в .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="66dee-119">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="66dee-120">В этой функции появился новый тип идентификатора, называемый *параметром типа*.</span><span class="sxs-lookup"><span data-stu-id="66dee-120">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="66dee-121">✔️ имена параметров универсального типа с описательными именами, если только имя в одном письме не является полностью понятным, а описательное имя не будет добавлять значение.</span><span class="sxs-lookup"><span data-stu-id="66dee-121">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="66dee-122">✔️ РЕКОМЕНДУЕТСЯ использовать `T` в качестве имени параметра типа для типов с одним однобуквенным параметром типа.</span><span class="sxs-lookup"><span data-stu-id="66dee-122">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="66dee-123">✔️ добавлять в префикс имена параметров описательного типа с помощью `T` .</span><span class="sxs-lookup"><span data-stu-id="66dee-123">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="66dee-124">✔️ Рассмотрите возможность указания ограничений, накладываемых на параметр типа в имени параметра.</span><span class="sxs-lookup"><span data-stu-id="66dee-124">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="66dee-125">Например, может быть вызван параметр с ограничением `ISession` `TSession` .</span><span class="sxs-lookup"><span data-stu-id="66dee-125">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="66dee-126">Имена общих типов</span><span class="sxs-lookup"><span data-stu-id="66dee-126">Names of Common Types</span></span>
 <span data-ttu-id="66dee-127">✔️ следовать рекомендациям, описанным в следующей таблице, при именовании типов, производных от или реализующих определенные типы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66dee-127">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="66dee-128">Базовый тип</span><span class="sxs-lookup"><span data-stu-id="66dee-128">Base Type</span></span>|<span data-ttu-id="66dee-129">Руководство по производному или реализующему типу</span><span class="sxs-lookup"><span data-stu-id="66dee-129">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="66dee-130">✔️ Добавить суффикс "Attribute" к именам классов настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="66dee-130">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="66dee-131">✔️ Добавить суффикс EventHandler к именам делегатов, используемых в событиях.</span><span class="sxs-lookup"><span data-stu-id="66dee-131">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="66dee-132">✔️ Добавить суффикс "Callback" к именам делегатов, отличных от используемых в качестве обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="66dee-132">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="66dee-133">❌НЕ добавляйте суффикс "Delegate" в делегат.</span><span class="sxs-lookup"><span data-stu-id="66dee-133">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="66dee-134">✔️ Добавить суффикс EventArgs.</span><span class="sxs-lookup"><span data-stu-id="66dee-134">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="66dee-135">❌НЕ наследовать от этого класса; Вместо этого используйте ключевое слово, поддерживаемое языком. Например, в C# используйте `enum` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="66dee-135">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="66dee-136">❌НЕ добавляйте суффикс "enum" или "Flag".</span><span class="sxs-lookup"><span data-stu-id="66dee-136">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="66dee-137">✔️ Добавить суффикс "Exception".</span><span class="sxs-lookup"><span data-stu-id="66dee-137">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="66dee-138">✔️ Добавить суффикс "Dictionary".</span><span class="sxs-lookup"><span data-stu-id="66dee-138">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="66dee-139">Обратите внимание, что `IDictionary` — это конкретный тип коллекции, но это правило имеет приоритет над более общими коллекциями, приведенными ниже.</span><span class="sxs-lookup"><span data-stu-id="66dee-139">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="66dee-140">✔️ Добавить суффикс "Collection".</span><span class="sxs-lookup"><span data-stu-id="66dee-140">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="66dee-141">✔️ Добавить суффикс "Stream".</span><span class="sxs-lookup"><span data-stu-id="66dee-141">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="66dee-142">✔️ Добавить суффикс "Permission".</span><span class="sxs-lookup"><span data-stu-id="66dee-142">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="66dee-143">Перечисления именования</span><span class="sxs-lookup"><span data-stu-id="66dee-143">Naming Enumerations</span></span>
 <span data-ttu-id="66dee-144">Имена типов перечисления (также называемые перечислениями) в целом должны соответствовать стандартным правилам именования типов (Паскалкасинг и т. д.).</span><span class="sxs-lookup"><span data-stu-id="66dee-144">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="66dee-145">Однако существуют дополнительные рекомендации, которые применяются специально для перечислений.</span><span class="sxs-lookup"><span data-stu-id="66dee-145">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="66dee-146">✔️ использовать единственное имя типа для перечисления, если его значения не являются битовыми полями.</span><span class="sxs-lookup"><span data-stu-id="66dee-146">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="66dee-147">✔️ использовать имя типа во множественном числе для перечисления с битовыми полями в качестве значений, также называемых flags Enum.</span><span class="sxs-lookup"><span data-stu-id="66dee-147">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="66dee-148">❌НЕ используйте суффикс "enum" в именах типов Enum.</span><span class="sxs-lookup"><span data-stu-id="66dee-148">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="66dee-149">❌НЕ используйте суффикс "Flag" или "Flags" в именах типов Enum.</span><span class="sxs-lookup"><span data-stu-id="66dee-149">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="66dee-150">❌НЕ используйте префикс для имен значений перечисления (например, "ad" для перечислений ADO, "RTF" для перечислений форматированного текста и т. д.).</span><span class="sxs-lookup"><span data-stu-id="66dee-150">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="66dee-151">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="66dee-151">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="66dee-152">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="66dee-152">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="66dee-153">См. также</span><span class="sxs-lookup"><span data-stu-id="66dee-153">See also</span></span>

- [<span data-ttu-id="66dee-154">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="66dee-154">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="66dee-155">Рекомендации по именованию</span><span class="sxs-lookup"><span data-stu-id="66dee-155">Naming Guidelines</span></span>](naming-guidelines.md)
