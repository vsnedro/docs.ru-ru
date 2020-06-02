---
title: Правила именования
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
ms.openlocfilehash: 1b137be60f4c8c1c7cf1fa1f807841d4bc209089
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290179"
---
# <a name="naming-guidelines"></a><span data-ttu-id="9c6dc-102">Правила именования</span><span class="sxs-lookup"><span data-stu-id="9c6dc-102">Naming Guidelines</span></span>
<span data-ttu-id="9c6dc-103">В соответствии с единообразным набором соглашений об именовании в разработке платформы может быть основная составляющая удобства использования платформы.</span><span class="sxs-lookup"><span data-stu-id="9c6dc-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="9c6dc-104">Он позволяет использовать платформу многими разработчиками в широко разделенных проектах.</span><span class="sxs-lookup"><span data-stu-id="9c6dc-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="9c6dc-105">Помимо согласованности форм, имена элементов платформы должны быть легко понятны и должны передавать функцию каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="9c6dc-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="9c6dc-106">Цель этой главы — предоставить единообразный набор соглашений об именовании, которые приводят к непосредственным именам для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="9c6dc-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="9c6dc-107">Хотя применение этих соглашений об именовании в качестве общего руководства по разработке кода приведет к более согласованному именованию в коде, необходимо только применить их к интерфейсам API, которые являются общедоступными (открытые или защищенные типы и члены, а также явно реализованные интерфейсы).</span><span class="sxs-lookup"><span data-stu-id="9c6dc-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9c6dc-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9c6dc-108">In This Section</span></span>  
 [<span data-ttu-id="9c6dc-109">Соглашения о капитализации</span><span class="sxs-lookup"><span data-stu-id="9c6dc-109">Capitalization Conventions</span></span>](capitalization-conventions.md)  
 [<span data-ttu-id="9c6dc-110">Общие соглашения об именовании</span><span class="sxs-lookup"><span data-stu-id="9c6dc-110">General Naming Conventions</span></span>](general-naming-conventions.md)  
 [<span data-ttu-id="9c6dc-111">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="9c6dc-111">Names of Assemblies and DLLs</span></span>](names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="9c6dc-112">Имена пространств имен</span><span class="sxs-lookup"><span data-stu-id="9c6dc-112">Names of Namespaces</span></span>](names-of-namespaces.md)  
 [<span data-ttu-id="9c6dc-113">Имена классов, структур и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="9c6dc-113">Names of Classes, Structs, and Interfaces</span></span>](names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="9c6dc-114">Имена членов типа</span><span class="sxs-lookup"><span data-stu-id="9c6dc-114">Names of Type Members</span></span>](names-of-type-members.md)  
 [<span data-ttu-id="9c6dc-115">Параметры именования</span><span class="sxs-lookup"><span data-stu-id="9c6dc-115">Naming Parameters</span></span>](naming-parameters.md)  
 [<span data-ttu-id="9c6dc-116">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="9c6dc-116">Naming Resources</span></span>](naming-resources.md)  
 <span data-ttu-id="9c6dc-117">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="9c6dc-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9c6dc-118">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9c6dc-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c6dc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9c6dc-119">See also</span></span>

- [<span data-ttu-id="9c6dc-120">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="9c6dc-120">Framework Design Guidelines</span></span>](index.md)
