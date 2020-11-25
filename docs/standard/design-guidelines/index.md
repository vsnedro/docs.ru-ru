---
title: Рекомендации по разработке платформы
description: В разделе рекомендации по проектированию платформ для разработки библиотек, расширяющих возможности .NET и взаимодействующих с ними, чтобы обеспечить согласованность и простоту использования API.
titleSuffix: ''
ms.date: 10/22/2008
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 03fa44c1fed219b50cf1a8d22b2c9f79947f4976
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706662"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="d968a-103">Рекомендации по разработке платформы</span><span class="sxs-lookup"><span data-stu-id="d968a-103">Framework Design Guidelines</span></span>

<span data-ttu-id="d968a-104">В этом разделе приводятся рекомендации по проектированию библиотек, которые расширяют и взаимодействуют с .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d968a-104">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="d968a-105">Цель состоит в том, чтобы помочь дизайнерам библиотек обеспечить согласованность и простоту использования API, предоставляя унифицированную модель программирования, которая не зависит от языка программирования, используемого для разработки.</span><span class="sxs-lookup"><span data-stu-id="d968a-105">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="d968a-106">При разработке классов и компонентов, расширяющих .NET Framework, рекомендуется следовать этим рекомендациям по проектированию.</span><span class="sxs-lookup"><span data-stu-id="d968a-106">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="d968a-107">Непоследовательная структура библиотеки негативно влияет на производительность разработки и не дорекомендует внедрения.</span><span class="sxs-lookup"><span data-stu-id="d968a-107">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="d968a-108">Рекомендации организованы в виде простых рекомендаций с префиксами,, `Do` `Consider` `Avoid` и `Do not` .</span><span class="sxs-lookup"><span data-stu-id="d968a-108">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="d968a-109">Эти рекомендации предназначены для того, чтобы помочь дизайнерам библиотек классов понять компромиссы между различными решениями.</span><span class="sxs-lookup"><span data-stu-id="d968a-109">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="d968a-110">Возможны ситуации, когда хорошая структура библиотеки требует соблюдения этих рекомендаций по проектированию.</span><span class="sxs-lookup"><span data-stu-id="d968a-110">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="d968a-111">Такие случаи должны быть редкими, и важно иметь четкие и интересные причины для принятия решения.</span><span class="sxs-lookup"><span data-stu-id="d968a-111">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="d968a-112">Эти рекомендации взяты из *руководства по проектированию для платформы книги: соглашения, идиомы и закономерности для многократно используемых библиотек .NET, 2-го выпуска*, Крзисзтоф Квалина и Михаил Abrams).</span><span class="sxs-lookup"><span data-stu-id="d968a-112">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d968a-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d968a-113">In This Section</span></span>  

 [<span data-ttu-id="d968a-114">Рекомендации по именованию</span><span class="sxs-lookup"><span data-stu-id="d968a-114">Naming Guidelines</span></span>](naming-guidelines.md)  
 <span data-ttu-id="d968a-115">Содержит рекомендации по именованию сборок, пространств имен, типов и членов в библиотеках классов.</span><span class="sxs-lookup"><span data-stu-id="d968a-115">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="d968a-116">Рекомендации по проектированию типов</span><span class="sxs-lookup"><span data-stu-id="d968a-116">Type Design Guidelines</span></span>](type.md)  
 <span data-ttu-id="d968a-117">Содержит рекомендации по использованию статических и абстрактных классов, интерфейсов, перечислений, структур и других типов.</span><span class="sxs-lookup"><span data-stu-id="d968a-117">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="d968a-118">Рекомендации по проектированию членов</span><span class="sxs-lookup"><span data-stu-id="d968a-118">Member Design Guidelines</span></span>](member.md)  
 <span data-ttu-id="d968a-119">Содержит рекомендации по проектированию и использованию свойств, методов, конструкторов, полей, событий, операторов и параметров.</span><span class="sxs-lookup"><span data-stu-id="d968a-119">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="d968a-120">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="d968a-120">Designing for Extensibility</span></span>](designing-for-extensibility.md)  
 <span data-ttu-id="d968a-121">Обсуждаются механизмы расширения, такие как создание подклассов, использование событий, виртуальные члены и обратные вызовы, а также объясняется, как выбрать механизмы, которые наилучшим образом соответствуют требованиям вашей платформы.</span><span class="sxs-lookup"><span data-stu-id="d968a-121">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="d968a-122">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="d968a-122">Design Guidelines for Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="d968a-123">Описывает рекомендации по проектированию, созданию, генерации и перехвату исключений.</span><span class="sxs-lookup"><span data-stu-id="d968a-123">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="d968a-124">Рекомендации по использованию</span><span class="sxs-lookup"><span data-stu-id="d968a-124">Usage Guidelines</span></span>](usage-guidelines.md)  
 <span data-ttu-id="d968a-125">Описывает рекомендации по использованию общих типов, таких как массивы, атрибуты и коллекции, поддержка сериализации и перегрузка операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="d968a-125">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="d968a-126">Общие шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="d968a-126">Common Design Patterns</span></span>](common-design-patterns.md)  
 <span data-ttu-id="d968a-127">Содержит рекомендации по выбору и реализации свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="d968a-127">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="d968a-128">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="d968a-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d968a-129">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d968a-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d968a-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d968a-130">See also</span></span>

- [<span data-ttu-id="d968a-131">Обзор</span><span class="sxs-lookup"><span data-stu-id="d968a-131">Overview</span></span>](../../framework/get-started/overview.md)
- [<span data-ttu-id="d968a-132">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="d968a-132">Development Guide</span></span>](../../framework/development-guide.md)
