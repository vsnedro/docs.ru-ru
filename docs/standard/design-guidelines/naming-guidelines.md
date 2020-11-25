---
title: Правила именования
description: В этом обзоре прочитайте о соглашениях об именовании, используемых при разработке платформ. Перейдите к статьям, описывающим регистр букв, общее именование и другие рекомендации.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
ms.openlocfilehash: de68eeb287b13bc9f55230243f23cd03508f2561
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706428"
---
# <a name="naming-guidelines"></a><span data-ttu-id="3c7a1-104">Правила именования</span><span class="sxs-lookup"><span data-stu-id="3c7a1-104">Naming Guidelines</span></span>

<span data-ttu-id="3c7a1-105">В соответствии с единообразным набором соглашений об именовании в разработке платформы может быть основная составляющая удобства использования платформы.</span><span class="sxs-lookup"><span data-stu-id="3c7a1-105">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="3c7a1-106">Он позволяет использовать платформу многими разработчиками в широко разделенных проектах.</span><span class="sxs-lookup"><span data-stu-id="3c7a1-106">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="3c7a1-107">Помимо согласованности форм, имена элементов платформы должны быть легко понятны и должны передавать функцию каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="3c7a1-107">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="3c7a1-108">Цель этой главы — предоставить единообразный набор соглашений об именовании, которые приводят к непосредственным именам для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="3c7a1-108">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="3c7a1-109">Хотя применение этих соглашений об именовании в качестве общего руководства по разработке кода приведет к более согласованному именованию в коде, необходимо только применить их к интерфейсам API, которые являются общедоступными (открытые или защищенные типы и члены, а также явно реализованные интерфейсы).</span><span class="sxs-lookup"><span data-stu-id="3c7a1-109">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c7a1-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="3c7a1-110">In This Section</span></span>  

 [<span data-ttu-id="3c7a1-111">Соглашения о капитализации</span><span class="sxs-lookup"><span data-stu-id="3c7a1-111">Capitalization Conventions</span></span>](capitalization-conventions.md)  
 [<span data-ttu-id="3c7a1-112">Общие соглашения об именовании</span><span class="sxs-lookup"><span data-stu-id="3c7a1-112">General Naming Conventions</span></span>](general-naming-conventions.md)  
 [<span data-ttu-id="3c7a1-113">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="3c7a1-113">Names of Assemblies and DLLs</span></span>](names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="3c7a1-114">Имена пространств имен</span><span class="sxs-lookup"><span data-stu-id="3c7a1-114">Names of Namespaces</span></span>](names-of-namespaces.md)  
 [<span data-ttu-id="3c7a1-115">Имена классов, структур и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="3c7a1-115">Names of Classes, Structs, and Interfaces</span></span>](names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="3c7a1-116">Имена членов типа</span><span class="sxs-lookup"><span data-stu-id="3c7a1-116">Names of Type Members</span></span>](names-of-type-members.md)  
 [<span data-ttu-id="3c7a1-117">Параметры именования</span><span class="sxs-lookup"><span data-stu-id="3c7a1-117">Naming Parameters</span></span>](naming-parameters.md)  
 [<span data-ttu-id="3c7a1-118">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="3c7a1-118">Naming Resources</span></span>](naming-resources.md)  
 <span data-ttu-id="3c7a1-119">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="3c7a1-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3c7a1-120">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="3c7a1-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7a1-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3c7a1-121">See also</span></span>

- [<span data-ttu-id="3c7a1-122">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="3c7a1-122">Framework Design Guidelines</span></span>](index.md)
