---
title: Практическое руководство. Как создать модель объектов на языке Visual Basic или C#
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 03525b6f39dcccfb9c68da6bab8b524efa3613ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158413"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="1ff20-102">Как создать объектную модель в Visual Basic или C\#</span><span class="sxs-lookup"><span data-stu-id="1ff20-102">How to: Generate the Object Model in Visual Basic or C\#</span></span>

<span data-ttu-id="1ff20-103">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектная модель используемого языка программирования сопоставляется с реляционной базой данных.</span><span class="sxs-lookup"><span data-stu-id="1ff20-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="1ff20-104">Доступны два средства для автоматического создания Visual Basic или модели C# на основе метаданных существующей базы данных.</span><span class="sxs-lookup"><span data-stu-id="1ff20-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
- <span data-ttu-id="1ff20-105">При использовании Visual Studio можно использовать реляционный конструктор объектов для создания объектной модели.</span><span class="sxs-lookup"><span data-stu-id="1ff20-105">If you are using Visual Studio, you can use the Object Relational Designer to generate an object model.</span></span> <span data-ttu-id="1ff20-106">Реляционный конструктор объектов (R) предоставляет богатый пользовательский интерфейс, помогающий в создании [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектной модели.</span><span class="sxs-lookup"><span data-stu-id="1ff20-106">The O/R Designer provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="1ff20-107">Дополнительные сведения см. [в разделе средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="1ff20-107">For more information see, [Linq to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
- <span data-ttu-id="1ff20-108">Средство командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="1ff20-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="1ff20-109">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="1ff20-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1ff20-110">Если существующие базы данных отсутствуют и необходимо создать базу данных из объектной модели, можно создать объектную модель с помощью редактора кода и метода <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span><span class="sxs-lookup"><span data-stu-id="1ff20-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="1ff20-111">Дополнительные сведения см. [в разделе инструкции. динамическое создание базы данных](how-to-dynamically-create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="1ff20-111">For more information, see [How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="1ff20-112">Документация для реляционного конструктора объектов (R) содержит примеры создания объектной модели Visual Basic или C# с помощью конструктора O/R.</span><span class="sxs-lookup"><span data-stu-id="1ff20-112">Documentation for the O/R Designer provides examples of how to generate a Visual Basic or C# object model by using the O/R Designer.</span></span> <span data-ttu-id="1ff20-113">Ниже приведены примеры использования программы командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="1ff20-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="1ff20-114">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="1ff20-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ff20-115">Пример</span><span class="sxs-lookup"><span data-stu-id="1ff20-115">Example</span></span>  

 <span data-ttu-id="1ff20-116">Командная строка SQLMetal, показанная в следующем примере, создает Visual Basic код в качестве объектной модели на основе атрибутов образца базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="1ff20-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="1ff20-117">Также отображаются хранимые процедуры и функции.</span><span class="sxs-lookup"><span data-stu-id="1ff20-117">Stored procedures and functions are also rendered.</span></span>  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="1ff20-118">Пример</span><span class="sxs-lookup"><span data-stu-id="1ff20-118">Example</span></span>  

 <span data-ttu-id="1ff20-119">С помощью команды программы SQLMetal, представленной в следующем примере, создается код C# для основанной на атрибутах объектной модели базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="1ff20-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="1ff20-120">Также отображаются хранимые процедуры и функции и имена таблиц автоматически преобразуются в имена во множественном числе.</span><span class="sxs-lookup"><span data-stu-id="1ff20-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ff20-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ff20-121">See also</span></span>

- [<span data-ttu-id="1ff20-122">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="1ff20-122">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="1ff20-123">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1ff20-123">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="1ff20-124">Обучение с использованием пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="1ff20-124">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="1ff20-125">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="1ff20-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [<span data-ttu-id="1ff20-126">Сопоставление, основанное на атрибутах</span><span class="sxs-lookup"><span data-stu-id="1ff20-126">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="1ff20-127">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="1ff20-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="1ff20-128">Внешнее сопоставление</span><span class="sxs-lookup"><span data-stu-id="1ff20-128">External Mapping</span></span>](external-mapping.md)
- [<span data-ttu-id="1ff20-129">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="1ff20-129">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="1ff20-130">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="1ff20-130">Creating the Object Model</span></span>](creating-the-object-model.md)
