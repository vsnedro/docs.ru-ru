---
title: Обычные шаблоны разработки
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
ms.openlocfilehash: 9b9525a7597f7df6c9a554b51160a99f0e06232c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290971"
---
# <a name="common-design-patterns"></a><span data-ttu-id="d8c6b-102">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="d8c6b-102">Common Design Patterns</span></span>
<span data-ttu-id="d8c6b-103">Существует множество книг по шаблонам программного обеспечения, языкам шаблонов и антишаблонам, направленным на очень обширную тему шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d8c6b-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="d8c6b-104">Поэтому в этой главе приводятся рекомендации и обсуждение, связанное с очень ограниченным набором шаблонов, которые часто используются в проектировании API-интерфейсов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8c6b-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8c6b-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d8c6b-105">In This Section</span></span>  
 [<span data-ttu-id="d8c6b-106">Свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="d8c6b-106">Dependency Properties</span></span>](dependency-properties.md)  
 [<span data-ttu-id="d8c6b-107">Шаблон ликвидации</span><span class="sxs-lookup"><span data-stu-id="d8c6b-107">Dispose Pattern</span></span>](../garbage-collection/implementing-dispose.md)  
 <span data-ttu-id="d8c6b-108">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="d8c6b-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d8c6b-109">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d8c6b-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c6b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d8c6b-110">See also</span></span>

- [<span data-ttu-id="d8c6b-111">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="d8c6b-111">Framework Design Guidelines</span></span>](index.md)
