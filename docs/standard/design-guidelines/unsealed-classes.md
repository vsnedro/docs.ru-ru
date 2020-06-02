---
title: Незапечатанные классы
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 8e332a6382cf644c82d5e26cf5234cea08dcc693
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289555"
---
# <a name="unsealed-classes"></a><span data-ttu-id="f4c74-102">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="f4c74-102">Unsealed Classes</span></span>
<span data-ttu-id="f4c74-103">Запечатанные классы не могут наследоваться от, и они препятствуют расширяемости.</span><span class="sxs-lookup"><span data-stu-id="f4c74-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="f4c74-104">В отличие от этого, классы, которые могут быть унаследованы от, называются незапечатанными классами.</span><span class="sxs-lookup"><span data-stu-id="f4c74-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>

 <span data-ttu-id="f4c74-105">✔️ Рассмотрите возможность использования незапечатанных классов без добавленных виртуальных или защищенных членов в качестве отличного способа предоставления недорогого, но очень удобного расширения для платформы.</span><span class="sxs-lookup"><span data-stu-id="f4c74-105">✔️ CONSIDER using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>

 <span data-ttu-id="f4c74-106">Разработчикам часто требуется наследовать от незапечатанных классов, чтобы добавить удобные члены, такие как пользовательские конструкторы, новые методы или перегрузки методов.</span><span class="sxs-lookup"><span data-stu-id="f4c74-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="f4c74-107">Например, `System.Messaging.MessageQueue` является незапечатанным и, таким образом, позволяет пользователям создавать пользовательские очереди, которые по умолчанию имеют определенный путь к очереди, или добавлять пользовательские методы, которые УПРОЩАЮТ API для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="f4c74-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>

 <span data-ttu-id="f4c74-108">По умолчанию в большинстве языков программирования классы не запечатаны, и это рекомендуемое значение по умолчанию для большинства классов в платформах.</span><span class="sxs-lookup"><span data-stu-id="f4c74-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="f4c74-109">Расширяемость, обеспечиваемая незапечатанными типами, существенно оценена для пользователей платформы и довольно недорога для предоставления из-за сравнительно низких затрат на тестирование, связанных с незапечатанными типами.</span><span class="sxs-lookup"><span data-stu-id="f4c74-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>

 <span data-ttu-id="f4c74-110">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="f4c74-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f4c74-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f4c74-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f4c74-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f4c74-112">See also</span></span>

- [<span data-ttu-id="f4c74-113">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="f4c74-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="f4c74-114">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="f4c74-114">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="f4c74-115">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="f4c74-115">Sealing</span></span>](sealing.md)
