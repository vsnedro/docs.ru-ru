---
title: Преобразования данных с помощью LINQ (C#)
description: Узнайте, как использовать запросы LINQ в C# для преобразования данных. Можно изменить последовательность путем сортировки и группировки и создать новые типы с помощью предложения SELECT.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: af08938b6b8f169ded2180529c2b4aadebefef55
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558814"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="837c8-104">Преобразования данных с помощью LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="837c8-104">Data Transformations with LINQ (C#)</span></span>
<span data-ttu-id="837c8-105">LINQ используется не только для получения данных.</span><span class="sxs-lookup"><span data-stu-id="837c8-105">Language-Integrated Query (LINQ) is not only about retrieving data.</span></span> <span data-ttu-id="837c8-106">Это эффективный инструмент для их преобразования.</span><span class="sxs-lookup"><span data-stu-id="837c8-106">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="837c8-107">С помощью запросов LINQ можно использовать исходную последовательность в качестве входных данных и изменять ее разными способами для создания новой выходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="837c8-107">By using a LINQ query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="837c8-108">Можно изменить саму последовательность, не изменяя элементы, с помощью сортировки и группировки.</span><span class="sxs-lookup"><span data-stu-id="837c8-108">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="837c8-109">Но самой интересной функцией запросов LINQ можно назвать возможность создания новых типов.</span><span class="sxs-lookup"><span data-stu-id="837c8-109">But perhaps the most powerful feature of LINQ queries is the ability to create new types.</span></span> <span data-ttu-id="837c8-110">Это выполняется в предложении [select](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="837c8-110">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="837c8-111">Например, можно выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="837c8-111">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="837c8-112">Объединение нескольких входных последовательностей в одну выходную последовательность, имеющую новый тип.</span><span class="sxs-lookup"><span data-stu-id="837c8-112">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="837c8-113">Создание выходных последовательностей, элементы которых состоят из одного или нескольких свойств каждого элемента в исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="837c8-113">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="837c8-114">Создание выходных последовательностей, элементы которых состоят из результатов операций, выполняемых с источником данных.</span><span class="sxs-lookup"><span data-stu-id="837c8-114">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="837c8-115">Создание выходных последовательностей в другом формате.</span><span class="sxs-lookup"><span data-stu-id="837c8-115">Create output sequences in a different format.</span></span> <span data-ttu-id="837c8-116">Например, можно преобразовать данные из строк SQL или текстовых файлов в XML.</span><span class="sxs-lookup"><span data-stu-id="837c8-116">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="837c8-117">Это лишь несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="837c8-117">These are just several examples.</span></span> <span data-ttu-id="837c8-118">Очевидно, что эти преобразования могут сочетаться различными способами в одном запросе.</span><span class="sxs-lookup"><span data-stu-id="837c8-118">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="837c8-119">Более того, выходную последовательность одного запроса можно использовать как входную последовательность для нового запроса.</span><span class="sxs-lookup"><span data-stu-id="837c8-119">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="837c8-120">Объединение нескольких входных последовательностей в одну выходную</span><span class="sxs-lookup"><span data-stu-id="837c8-120">Joining Multiple Inputs into One Output Sequence</span></span>  
 <span data-ttu-id="837c8-121">Запрос LINQ можно использовать для создания выходной последовательности, содержащей элементы из нескольких входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="837c8-121">You can use a LINQ query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="837c8-122">Следующий пример демонстрирует объединение двух структур данных в памяти, однако те же принципы могут применяться для объединения данных из источников XML, SQL или DataSet.</span><span class="sxs-lookup"><span data-stu-id="837c8-122">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="837c8-123">Рассмотрим следующие два типа классов:</span><span class="sxs-lookup"><span data-stu-id="837c8-123">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="837c8-124">В следующем примере показан запрос:</span><span class="sxs-lookup"><span data-stu-id="837c8-124">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="837c8-125">Дополнительные сведения см. в разделе [Предложение join](../../../language-reference/keywords/join-clause.md) и [Предложение select](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="837c8-125">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="837c8-126">Выбор подмножества каждого исходного элемента</span><span class="sxs-lookup"><span data-stu-id="837c8-126">Selecting a Subset of each Source Element</span></span>  
 <span data-ttu-id="837c8-127">Существует два основных способа выбора подмножества каждого элемента в исходной последовательности:</span><span class="sxs-lookup"><span data-stu-id="837c8-127">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="837c8-128">Выбор только одного члена исходного элемента с помощью операции dot.</span><span class="sxs-lookup"><span data-stu-id="837c8-128">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="837c8-129">В следующем примере предполагается, что объект `Customer` содержит несколько открытых свойств, включая строку с именем `City`.</span><span class="sxs-lookup"><span data-stu-id="837c8-129">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="837c8-130">При выполнении этот запрос создаст выходную последовательность строк.</span><span class="sxs-lookup"><span data-stu-id="837c8-130">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="837c8-131">Для создания элементов, содержащих более одного свойства исходного элемента, можно использовать инициализатор объектов с именованным объектом или анонимным типом.</span><span class="sxs-lookup"><span data-stu-id="837c8-131">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="837c8-132">В следующем примере показано использование анонимного типа для инкапсуляции двух свойств из каждого элемента `Customer`:</span><span class="sxs-lookup"><span data-stu-id="837c8-132">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="837c8-133">Дополнительные сведения см. в разделе [Инициализаторы объектов и коллекций](../../classes-and-structs/object-and-collection-initializers.md) и [Анонимные типы](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="837c8-133">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="837c8-134">Преобразование объектов в памяти в XML</span><span class="sxs-lookup"><span data-stu-id="837c8-134">Transforming in-Memory Objects into XML</span></span>  
 <span data-ttu-id="837c8-135">Запросы LINQ позволяют легко преобразовывать данные между структурами данных в памяти, базами данных SQL, наборами данных ADO.NET и XML-потоками или документами.</span><span class="sxs-lookup"><span data-stu-id="837c8-135">LINQ queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="837c8-136">В следующем примере объекты в структуре данных в памяти преобразуются в XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="837c8-136">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="837c8-137">Этот код создает следующий выходные данные XML:</span><span class="sxs-lookup"><span data-stu-id="837c8-137">The code produces the following XML output:</span></span>  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 <span data-ttu-id="837c8-138">Дополнительные сведения см. в разделе [Создание деревьев XML C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="837c8-138">For more information, see [Creating XML Trees in C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="837c8-139">Выполнение операций с исходными элементами</span><span class="sxs-lookup"><span data-stu-id="837c8-139">Performing Operations on Source Elements</span></span>  
 <span data-ttu-id="837c8-140">Выходная последовательность не может содержать любые элементы или свойства элементов из исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="837c8-140">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="837c8-141">Результатом может быть последовательность значений, вычисляемых с использованием исходных элементов в качестве входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="837c8-141">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span>

 <span data-ttu-id="837c8-142">Следующий запрос принимает последовательность чисел, представляющих радиусы окружностей, вычисляет площадь каждой окружности и возвращает выходную последовательность, содержащую строки, отформатированные с учетом вычисленной площади.</span><span class="sxs-lookup"><span data-stu-id="837c8-142">The following query will take a sequence of numbers that represent radii of circles, calculate the area for each radius, and return an output sequence containing strings formatted with the calculated area.</span></span>

 <span data-ttu-id="837c8-143">Каждая строка для выходной последовательности будет отформатирована с помощью [интерполяции строк](../../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="837c8-143">Each string for the output sequence will be formatted using [string interpolation](../../../language-reference/tokens/interpolated.md).</span></span> <span data-ttu-id="837c8-144">Перед открывающей кавычкой в интерполированной строке будет находиться `$`, а операции будут выполняться внутри фигурных скобок, помещенных в интерполированную строку.</span><span class="sxs-lookup"><span data-stu-id="837c8-144">An interpolated string will have a `$` in front of the string's opening quotation mark, and operations can be performed within curly braces placed inside the interpolated string.</span></span> <span data-ttu-id="837c8-145">После выполнения операций результаты будут объединены.</span><span class="sxs-lookup"><span data-stu-id="837c8-145">Once those operations are performed, the results will be concatenated.</span></span>
  
> [!NOTE]
> <span data-ttu-id="837c8-146">Вызов методов в выражениях запросов не поддерживается, если запрос будет преобразован в некоторую другую область.</span><span class="sxs-lookup"><span data-stu-id="837c8-146">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="837c8-147">Например, невозможно вызвать обычный метод C# в [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], так как в SQL Server для него отсутствует контекст.</span><span class="sxs-lookup"><span data-stu-id="837c8-147">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="837c8-148">Тем не менее можно сопоставить хранимые процедуры методов и вызвать их.</span><span class="sxs-lookup"><span data-stu-id="837c8-148">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="837c8-149">Дополнительные сведения см. в разделе [Хранимые процедуры](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="837c8-149">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="837c8-150">См. также</span><span class="sxs-lookup"><span data-stu-id="837c8-150">See also</span></span>

- [<span data-ttu-id="837c8-151">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="837c8-151">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="837c8-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="837c8-152">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="837c8-153">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="837c8-153">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="837c8-154">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="837c8-154">LINQ to XML (C#)</span></span>](../../../../standard/linq/linq-xml-overview.md)
- [<span data-ttu-id="837c8-155">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="837c8-155">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="837c8-156">предложение select</span><span class="sxs-lookup"><span data-stu-id="837c8-156">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
