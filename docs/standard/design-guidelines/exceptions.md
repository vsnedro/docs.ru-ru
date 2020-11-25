---
title: Правила разработки исключений
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
ms.openlocfilehash: 28a3e40443c9f1be14243816b347da773705ff02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734739"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="faae4-102">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="faae4-102">Design Guidelines for Exceptions</span></span>

<span data-ttu-id="faae4-103">Обработка исключений имеет много преимуществ по сравнению с отчетами об ошибках, основанными на возврате значений.</span><span class="sxs-lookup"><span data-stu-id="faae4-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="faae4-104">Хорошая структура платформы помогает разработчику приложений реализовать преимущества исключений.</span><span class="sxs-lookup"><span data-stu-id="faae4-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="faae4-105">В этом разделе обсуждаются преимущества исключений и приводятся рекомендации по их эффективному использованию.</span><span class="sxs-lookup"><span data-stu-id="faae4-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="faae4-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="faae4-106">In This Section</span></span>  

 [<span data-ttu-id="faae4-107">Вызов исключения</span><span class="sxs-lookup"><span data-stu-id="faae4-107">Exception Throwing</span></span>](exception-throwing.md)  
 [<span data-ttu-id="faae4-108">Использование исключений стандартных типов</span><span class="sxs-lookup"><span data-stu-id="faae4-108">Using Standard Exception Types</span></span>](using-standard-exception-types.md)  
 [<span data-ttu-id="faae4-109">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="faae4-109">Exceptions and Performance</span></span>](exceptions-and-performance.md)  
 <span data-ttu-id="faae4-110">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="faae4-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="faae4-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="faae4-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faae4-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="faae4-112">See also</span></span>

- [<span data-ttu-id="faae4-113">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="faae4-113">Framework Design Guidelines</span></span>](index.md)
