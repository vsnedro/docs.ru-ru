---
title: "Введение в LINQ (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d90ea2503ba94df8ddb750b6f328168ddf22a65a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="introduction-to-linq-c"></a><span data-ttu-id="b79fd-102">Введение в LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="b79fd-102">Introduction to LINQ (C#)</span></span>
<span data-ttu-id="b79fd-103">LINQ (Language-Integrated Query) — это новая возможность, появившаяся в .NET Framework версии 3.5, которая соединяет мир объектов с миром данных.</span><span class="sxs-lookup"><span data-stu-id="b79fd-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="b79fd-104">Традиционно запросы к данным выражаются в виде простых строк без проверки типов при компиляции или поддержки IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b79fd-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="b79fd-105">Кроме того, разработчику приходится изучать различные языки запросов для каждого из типов источников данных: баз данных SQL, XML-документов, различных веб-служб и т. д.</span><span class="sxs-lookup"><span data-stu-id="b79fd-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="b79fd-106">LINQ делает *запросы* очень удобной языковой конструкцией в C#.</span><span class="sxs-lookup"><span data-stu-id="b79fd-106">LINQ makes a *query* a first-class language construct in C#.</span></span> <span data-ttu-id="b79fd-107">Вы создаете запросы к строго типизированным коллекциям объектов с помощью ключевых слов языка и знакомых операторов.</span><span class="sxs-lookup"><span data-stu-id="b79fd-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="b79fd-108">Вы можете писать запросы LINQ в C# для обращения к базам данных SQL Server, XML-документам, наборам данных ADO.NET и любым коллекциям объектов, поддерживающим интерфейс <xref:System.Collections.IEnumerable> или универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b79fd-108">You can write LINQ queries in C# for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="b79fd-109">Кроме того, сторонние разработчики обеспечивают поддержку LINQ для множества веб-служб и других реализаций баз данных.</span><span class="sxs-lookup"><span data-stu-id="b79fd-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="b79fd-110">Запросы LINQ можно использовать в новых проектах или параллельно с запросами, не относящимися к LINQ, в существующих проектах.</span><span class="sxs-lookup"><span data-stu-id="b79fd-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="b79fd-111">Единственное требование: проект должен разрабатываться для платформы .NET Framework версии 3.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="b79fd-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="b79fd-112">На приведенном ниже рисунке показан частично выполненный запрос LINQ к базе данных SQL Server в C# и Visual Basic с полной проверкой типов и поддержкой IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b79fd-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="b79fd-113">![Запрос LINQ с Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="b79fd-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b79fd-114">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="b79fd-114">Next Steps</span></span>  
 <span data-ttu-id="b79fd-115">Чтобы получить дополнительные сведения о LINQ, начните с ознакомления с некоторыми основным понятиями раздела [Приступая к работе с LINQ в C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), а затем прочитайте документацию по интересующей вас технологии LINQ:</span><span class="sxs-lookup"><span data-stu-id="b79fd-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="b79fd-116">Базы данных SQL Server: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="b79fd-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="b79fd-117">Документы XML: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="b79fd-117">XML documents: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="b79fd-118">Наборы данных ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="b79fd-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="b79fd-119">Коллекции, файлы и строки .NET и т. д.: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="b79fd-119">.NET collections, files, strings and so on: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79fd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b79fd-120">See Also</span></span>  
 [<span data-ttu-id="b79fd-121">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="b79fd-121">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
