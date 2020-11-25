---
title: Разработка структур
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: 7bb7e63004df2eb7541ba8d4f1118ea2272db126
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730907"
---
# <a name="struct-design"></a><span data-ttu-id="29df8-102">Разработка структур</span><span class="sxs-lookup"><span data-stu-id="29df8-102">Struct Design</span></span>

<span data-ttu-id="29df8-103">Тип значения общего назначения чаще всего называется структурой, ключевым словом C#.</span><span class="sxs-lookup"><span data-stu-id="29df8-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="29df8-104">В этом разделе приводятся рекомендации по проектированию общих структур.</span><span class="sxs-lookup"><span data-stu-id="29df8-104">This section provides guidelines for general struct design.</span></span>

 <span data-ttu-id="29df8-105">❌ НЕ предоставляющих конструктор без параметров для структуры.</span><span class="sxs-lookup"><span data-stu-id="29df8-105">❌ DO NOT provide a parameterless constructor for a struct.</span></span>

 <span data-ttu-id="29df8-106">После этого правила можно создавать массивы структур без необходимости запуска конструктора для каждого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="29df8-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="29df8-107">Обратите внимание, что C# не допускает, чтобы структуры имели конструкторы без параметров.</span><span class="sxs-lookup"><span data-stu-id="29df8-107">Notice that C# does not allow structs to have parameterless constructors.</span></span>

 <span data-ttu-id="29df8-108">❌ НЕ определяйте изменяемые типы значений.</span><span class="sxs-lookup"><span data-stu-id="29df8-108">❌ DO NOT define mutable value types.</span></span>

 <span data-ttu-id="29df8-109">У изменяемых типов значений есть несколько проблем.</span><span class="sxs-lookup"><span data-stu-id="29df8-109">Mutable value types have several problems.</span></span> <span data-ttu-id="29df8-110">Например, когда метод считывания свойства возвращает тип значения, вызывающий объект получает копию.</span><span class="sxs-lookup"><span data-stu-id="29df8-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="29df8-111">Поскольку копия создается неявным образом, разработчики могут не знать, что они изменяют копию, а не исходное значение.</span><span class="sxs-lookup"><span data-stu-id="29df8-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="29df8-112">Кроме того, некоторые языки (динамические языки, в частности) имеют проблемы с использованием изменяемых типов значений, так как даже локальные переменные при разыменовании приводят к созданию копии.</span><span class="sxs-lookup"><span data-stu-id="29df8-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>

 <span data-ttu-id="29df8-113">✔️ обеспечить допустимость состояния, в котором все данные экземпляра имеют нулевое значение, false или null (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="29df8-113">✔️ DO ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>

 <span data-ttu-id="29df8-114">Это предотвращает случайное создание недопустимых экземпляров при создании массива структур.</span><span class="sxs-lookup"><span data-stu-id="29df8-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>

 <span data-ttu-id="29df8-115">✔️ реализовать <xref:System.IEquatable%601> типы значений.</span><span class="sxs-lookup"><span data-stu-id="29df8-115">✔️ DO implement <xref:System.IEquatable%601> on value types.</span></span>

 <span data-ttu-id="29df8-116"><xref:System.Object.Equals%2A?displayProperty=nameWithType>Метод для типов значений вызывает упаковку и ее реализацию по умолчанию не очень эффективна, так как использует отражение.</span><span class="sxs-lookup"><span data-stu-id="29df8-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="29df8-117"><xref:System.IEquatable%601.Equals%2A> может иметь гораздо более высокую производительность и может быть реализовано таким образом, что он не будет вызывать упаковку.</span><span class="sxs-lookup"><span data-stu-id="29df8-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>

 <span data-ttu-id="29df8-118">❌ НЕ расширяйте явно <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="29df8-118">❌ DO NOT explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="29df8-119">На самом деле, большинство языков препятствуют этому.</span><span class="sxs-lookup"><span data-stu-id="29df8-119">In fact, most languages prevent this.</span></span>

 <span data-ttu-id="29df8-120">Как правило, структуры могут быть очень полезными, но их следует использовать только для небольших, однострочных неизменяемых значений, которые не будут часто выдаваться в штучной упаковке.</span><span class="sxs-lookup"><span data-stu-id="29df8-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>

 <span data-ttu-id="29df8-121">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="29df8-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="29df8-122">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="29df8-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="29df8-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="29df8-123">See also</span></span>

- [<span data-ttu-id="29df8-124">Рекомендации по проектированию типов</span><span class="sxs-lookup"><span data-stu-id="29df8-124">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="29df8-125">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="29df8-125">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="29df8-126">Выбор между классом и структурой</span><span class="sxs-lookup"><span data-stu-id="29df8-126">Choosing Between Class and Struct</span></span>](choosing-between-class-and-struct.md)
