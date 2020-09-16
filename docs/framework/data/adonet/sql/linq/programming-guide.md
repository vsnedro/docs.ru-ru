---
title: Руководство по программированию
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 0746d14d7be0b67bc9966ae0c5a4af0a3226c1e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546566"
---
# <a name="programming-guide"></a><span data-ttu-id="d97be-102">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="d97be-102">Programming Guide</span></span>
<span data-ttu-id="d97be-103">В этом разделе содержатся сведения о создании и использовании объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d97be-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="d97be-104">При использовании Visual Studio можно также использовать реляционный конструктор объектов для выполнения многих из этих задач.</span><span class="sxs-lookup"><span data-stu-id="d97be-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="d97be-105">Можно также выполнить поиск по Документация Майкрософт для конкретных проблем, и вы можете принять участие в [форуме LINQ](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), где вы сможете обсуждать более сложные темы подробно с экспертами.</span><span class="sxs-lookup"><span data-stu-id="d97be-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="d97be-106">Наконец, [LINQ to SQL: запрос на языке .NET для реляционных данных](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) , содержащий технические сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] технологии, завершен с помощью Visual Basic и примеров кода C#.</span><span class="sxs-lookup"><span data-stu-id="d97be-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d97be-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d97be-107">In This Section</span></span>  
 [<span data-ttu-id="d97be-108">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="d97be-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="d97be-109">Описывается создание объектной модели.</span><span class="sxs-lookup"><span data-stu-id="d97be-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="d97be-110">Установка связи с базой данных</span><span class="sxs-lookup"><span data-stu-id="d97be-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="d97be-111">Описывается использование объекта <xref:System.Data.Linq.DataContext> в качестве канала передачи в базу данных.</span><span class="sxs-lookup"><span data-stu-id="d97be-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="d97be-112">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="d97be-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="d97be-113">Описывается, как выполнять запросы в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], с демонстрацией целого ряда примеров.</span><span class="sxs-lookup"><span data-stu-id="d97be-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="d97be-114">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="d97be-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="d97be-115">Описывается, как изменять данные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d97be-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="d97be-116">Поддержка отладки</span><span class="sxs-lookup"><span data-stu-id="d97be-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="d97be-117">Описывается поддержка, доступная для отладки проектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d97be-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="d97be-118">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="d97be-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="d97be-119">Включает дополнительные вопросы для более опытных пользователей, такие как разрешение конфликтов параллелизма, создание новых баз данных и многое другое.</span><span class="sxs-lookup"><span data-stu-id="d97be-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d97be-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d97be-120">Related Sections</span></span>  
 [<span data-ttu-id="d97be-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d97be-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="d97be-122">Ссылки на разделы, в которых объясняется технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и демонстрируются ее возможности.</span><span class="sxs-lookup"><span data-stu-id="d97be-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="d97be-123">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="d97be-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="d97be-124">Ссылки на разделы, в которых демонстрируется использование хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="d97be-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="d97be-125">Введение в LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="d97be-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="d97be-126">Содержит ресурсы, помогающие начать изучение LINQ to SQL с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="d97be-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="d97be-127">Знакомство с LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d97be-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="d97be-128">Содержит ресурсы, помогающие начать изучение LINQ to SQL с помощью Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d97be-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
