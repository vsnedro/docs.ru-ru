---
title: SQL Server Compact и LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 7963db9e05eca7a7a148228c6d2fbca0221ca870
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155683"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="4bfaf-102">SQL Server Compact и LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4bfaf-102">SQL Server Compact and LINQ to SQL</span></span>

<span data-ttu-id="4bfaf-103">SQL Server Compact — это база данных по умолчанию, устанавливаемая вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="4bfaf-104">Дополнительные сведения см. [в разделе использование SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="4bfaf-104">For more information, see [Using SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="4bfaf-105">В этом разделе описываются основные различия в использовании, конфигурации, наборах функций и области [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддержки.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="4bfaf-106">Характеристики SQL Server Compact относительно LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4bfaf-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  

 <span data-ttu-id="4bfaf-107">По умолчанию SQL Server Compact устанавливается для всех выпусков Visual Studio и, следовательно, доступен на компьютере разработчика для использования с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bfaf-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="4bfaf-108">Но развертывание приложения, которое использует SQL Server Compact и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отличается от этого для SQL Server приложения.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="4bfaf-109">SQL Server Compact не является частью платформы .NET Framework. Этот компонент должен быть упакован в состав приложения или загружен отдельно с веб-сайта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="4bfaf-110">Обратите внимание на следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="4bfaf-111">SQL Server Compact упаковывается в виде DLL-файла, который может использоваться непосредственно в файлах базы данных (расширение SDF).</span><span class="sxs-lookup"><span data-stu-id="4bfaf-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="4bfaf-112">SQL Server Compact выполняется в тех же процессах, что и клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="4bfaf-113">Таким образом, эффективность взаимодействия с SQL Server Compact может быть значительно выше, чем связь с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="4bfaf-114">С другой стороны, для SQL Server Compact не требуется взаимодействие управляемого и неуправляемого кода с сопутствующими расходами.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="4bfaf-115">Размер DLL-библиотеки SQL Server Compact невелик.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="4bfaf-116">Данная функция сокращает общий размер приложения.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="4bfaf-117">Среда выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и средство командной строки SQLMetal поддерживают SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="4bfaf-118">Реляционный конструктор объектов не поддерживает SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-118">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="4bfaf-119">Набор возможностей</span><span class="sxs-lookup"><span data-stu-id="4bfaf-119">Feature Set</span></span>  

 <span data-ttu-id="4bfaf-120">Набор функций SQL Server Compact намного проще, чем набор функций SQL Server следующими способами, которые могут повлиять на [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] приложения:</span><span class="sxs-lookup"><span data-stu-id="4bfaf-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="4bfaf-121">SQL Server Compact не поддерживает хранимые процедуры или представления.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="4bfaf-122">SQL Server Compact поддерживает только подмножество типов данных и функций SQL.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="4bfaf-123">SQL Server Compact поддерживает только подмножество конструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="4bfaf-124">SQL Server Compact предоставляет только минимальный оптимизатор.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="4bfaf-125">Существует возможность истечения времени ожидания некоторых запросов.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="4bfaf-126">SQL Server Compact не поддерживает частичное доверие.</span><span class="sxs-lookup"><span data-stu-id="4bfaf-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfaf-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4bfaf-127">See also</span></span>

- [<span data-ttu-id="4bfaf-128">Ссылки</span><span class="sxs-lookup"><span data-stu-id="4bfaf-128">Reference</span></span>](reference.md)
