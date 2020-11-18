---
title: Разработка абстрактных классов
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 6903e10c8695376d8ac5961461796c5413307f90
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821649"
---
# <a name="abstract-class-design"></a><span data-ttu-id="40dec-102">Разработка абстрактных классов</span><span class="sxs-lookup"><span data-stu-id="40dec-102">Abstract Class Design</span></span>

<span data-ttu-id="40dec-103">❌ НЕ определяйте открытые или защищенные внутренние конструкторы в абстрактных типах.</span><span class="sxs-lookup"><span data-stu-id="40dec-103">❌ DO NOT define public or protected internal constructors in abstract types.</span></span>

 <span data-ttu-id="40dec-104">Конструкторы должны быть открытыми только в том случае, если пользователям необходимо создавать экземпляры типа.</span><span class="sxs-lookup"><span data-stu-id="40dec-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="40dec-105">Поскольку нельзя создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неверно спроектирован и ошибочно ведет себя для пользователей.</span><span class="sxs-lookup"><span data-stu-id="40dec-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>

 <span data-ttu-id="40dec-106">✔️ определить защищенный или внутренний конструктор в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="40dec-106">✔️ DO define a protected or an internal constructor in abstract classes.</span></span>

 <span data-ttu-id="40dec-107">Защищенный конструктор является более распространенным и просто позволяет базовому классу выполнять собственную инициализацию при создании подтипов.</span><span class="sxs-lookup"><span data-stu-id="40dec-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>

 <span data-ttu-id="40dec-108">Внутренний конструктор можно использовать для ограничения конкретных реализаций абстрактного класса сборкой, определяющей класс.</span><span class="sxs-lookup"><span data-stu-id="40dec-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>

 <span data-ttu-id="40dec-109">✔️ предоставить по крайней мере один конкретный тип, наследующий от каждого передаваемого абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="40dec-109">✔️ DO provide at least one concrete type that inherits from each abstract class that you ship.</span></span>

 <span data-ttu-id="40dec-110">Это помогает проверить структуру абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="40dec-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="40dec-111">Например,  <xref:System.IO.FileStream?displayProperty=nameWithType> является реализацией <xref:System.IO.Stream?displayProperty=nameWithType> абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="40dec-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>

 <span data-ttu-id="40dec-112">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="40dec-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="40dec-113">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="40dec-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="40dec-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="40dec-114">See also</span></span>

- [<span data-ttu-id="40dec-115">Рекомендации по проектированию типов</span><span class="sxs-lookup"><span data-stu-id="40dec-115">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="40dec-116">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="40dec-116">Framework Design Guidelines</span></span>](index.md)
