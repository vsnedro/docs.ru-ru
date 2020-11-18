---
title: Разработка статичных классов
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: efa5ca6e7b5e7b7d03cbe1d55471a388f3faab37
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828664"
---
# <a name="static-class-design"></a><span data-ttu-id="c8b02-102">Разработка статичных классов</span><span class="sxs-lookup"><span data-stu-id="c8b02-102">Static Class Design</span></span>
<span data-ttu-id="c8b02-103">Статический класс определяется как класс, который содержит только статические члены (конечно же, помимо членов экземпляров, наследуемых от <xref:System.Object?displayProperty=nameWithType> и, возможно, закрытого конструктора).</span><span class="sxs-lookup"><span data-stu-id="c8b02-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="c8b02-104">Некоторые языки предоставляют встроенную поддержку статических классов.</span><span class="sxs-lookup"><span data-stu-id="c8b02-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="c8b02-105">В C# 2,0 и более поздних версиях, когда класс объявлен как статический, он является запечатанным, абстрактным, а члены экземпляров не могут быть переопределены или объявлены.</span><span class="sxs-lookup"><span data-stu-id="c8b02-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>

 <span data-ttu-id="c8b02-106">Статические классы являются компромиссом между чисто объектно-ориентированной архитектурой и простотой.</span><span class="sxs-lookup"><span data-stu-id="c8b02-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="c8b02-107">Они обычно используются для предоставления сочетаний клавиш для других операций (например <xref:System.IO.File?displayProperty=nameWithType> ,), владельцев методов расширения или функциональных возможностей, для которых полная объектно-ориентированная оболочка не гарантируется (например, <xref:System.Environment?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="c8b02-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="c8b02-108">✔️ использовать статические классы с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="c8b02-108">✔️ DO use static classes sparingly.</span></span>

 <span data-ttu-id="c8b02-109">Статические классы должны использоваться только в качестве вспомогательных классов для объектно-ориентированного ядра платформы.</span><span class="sxs-lookup"><span data-stu-id="c8b02-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>

 <span data-ttu-id="c8b02-110">❌ НЕ следует рассматривать статические классы как различные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="c8b02-110">❌ DO NOT treat static classes as a miscellaneous bucket.</span></span>

 <span data-ttu-id="c8b02-111">❌ НЕ объявляйте и не переопределяйте члены экземпляров в статических классах.</span><span class="sxs-lookup"><span data-stu-id="c8b02-111">❌ DO NOT declare or override instance members in static classes.</span></span>

 <span data-ttu-id="c8b02-112">✔️ объявить статические классы как запечатанные, абстрактные и добавьте конструктор закрытого экземпляра, если ваш язык программирования не имеет встроенной поддержки статических классов.</span><span class="sxs-lookup"><span data-stu-id="c8b02-112">✔️ DO declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>

 <span data-ttu-id="c8b02-113">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="c8b02-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="c8b02-114">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c8b02-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="c8b02-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c8b02-115">See also</span></span>

- [<span data-ttu-id="c8b02-116">Рекомендации по проектированию типов</span><span class="sxs-lookup"><span data-stu-id="c8b02-116">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="c8b02-117">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="c8b02-117">Framework Design Guidelines</span></span>](index.md)
