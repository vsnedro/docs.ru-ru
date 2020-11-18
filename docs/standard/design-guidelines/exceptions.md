---
title: Правила разработки исключений
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
ms.openlocfilehash: 776e559bb1629245c275cb4463531a8dd4b230ae
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821155"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="e0a25-102">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="e0a25-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="e0a25-103">Обработка исключений имеет много преимуществ по сравнению с отчетами об ошибках, основанными на возврате значений.</span><span class="sxs-lookup"><span data-stu-id="e0a25-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="e0a25-104">Хорошая структура платформы помогает разработчику приложений реализовать преимущества исключений.</span><span class="sxs-lookup"><span data-stu-id="e0a25-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="e0a25-105">В этом разделе обсуждаются преимущества исключений и приводятся рекомендации по их эффективному использованию.</span><span class="sxs-lookup"><span data-stu-id="e0a25-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0a25-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e0a25-106">In This Section</span></span>  
 [<span data-ttu-id="e0a25-107">Вызов исключения</span><span class="sxs-lookup"><span data-stu-id="e0a25-107">Exception Throwing</span></span>](exception-throwing.md)  
 [<span data-ttu-id="e0a25-108">Использование исключений стандартных типов</span><span class="sxs-lookup"><span data-stu-id="e0a25-108">Using Standard Exception Types</span></span>](using-standard-exception-types.md)  
 [<span data-ttu-id="e0a25-109">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="e0a25-109">Exceptions and Performance</span></span>](exceptions-and-performance.md)  
 <span data-ttu-id="e0a25-110">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e0a25-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e0a25-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e0a25-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a25-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e0a25-112">See also</span></span>

- [<span data-ttu-id="e0a25-113">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="e0a25-113">Framework Design Guidelines</span></span>](index.md)
