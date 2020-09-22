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
# <a name="data-transformations-with-linq-c"></a>Преобразования данных с помощью LINQ (C#)
LINQ используется не только для получения данных. Это эффективный инструмент для их преобразования. С помощью запросов LINQ можно использовать исходную последовательность в качестве входных данных и изменять ее разными способами для создания новой выходной последовательности. Можно изменить саму последовательность, не изменяя элементы, с помощью сортировки и группировки. Но самой интересной функцией запросов LINQ можно назвать возможность создания новых типов. Это выполняется в предложении [select](../../../language-reference/keywords/select-clause.md). Например, можно выполнить следующие задачи.  
  
- Объединение нескольких входных последовательностей в одну выходную последовательность, имеющую новый тип.  
  
- Создание выходных последовательностей, элементы которых состоят из одного или нескольких свойств каждого элемента в исходной последовательности.  
  
- Создание выходных последовательностей, элементы которых состоят из результатов операций, выполняемых с источником данных.  
  
- Создание выходных последовательностей в другом формате. Например, можно преобразовать данные из строк SQL или текстовых файлов в XML.  
  
 Это лишь несколько примеров. Очевидно, что эти преобразования могут сочетаться различными способами в одном запросе. Более того, выходную последовательность одного запроса можно использовать как входную последовательность для нового запроса.  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a>Объединение нескольких входных последовательностей в одну выходную  
 Запрос LINQ можно использовать для создания выходной последовательности, содержащей элементы из нескольких входных последовательностей. Следующий пример демонстрирует объединение двух структур данных в памяти, однако те же принципы могут применяться для объединения данных из источников XML, SQL или DataSet. Рассмотрим следующие два типа классов:  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 В следующем примере показан запрос:  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 Дополнительные сведения см. в разделе [Предложение join](../../../language-reference/keywords/join-clause.md) и [Предложение select](../../../language-reference/keywords/select-clause.md).  
  
## <a name="selecting-a-subset-of-each-source-element"></a>Выбор подмножества каждого исходного элемента  
 Существует два основных способа выбора подмножества каждого элемента в исходной последовательности:  
  
1. Выбор только одного члена исходного элемента с помощью операции dot. В следующем примере предполагается, что объект `Customer` содержит несколько открытых свойств, включая строку с именем `City`. При выполнении этот запрос создаст выходную последовательность строк.  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. Для создания элементов, содержащих более одного свойства исходного элемента, можно использовать инициализатор объектов с именованным объектом или анонимным типом. В следующем примере показано использование анонимного типа для инкапсуляции двух свойств из каждого элемента `Customer`:  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Дополнительные сведения см. в разделе [Инициализаторы объектов и коллекций](../../classes-and-structs/object-and-collection-initializers.md) и [Анонимные типы](../../classes-and-structs/anonymous-types.md).  
  
## <a name="transforming-in-memory-objects-into-xml"></a>Преобразование объектов в памяти в XML  
 Запросы LINQ позволяют легко преобразовывать данные между структурами данных в памяти, базами данных SQL, наборами данных ADO.NET и XML-потоками или документами. В следующем примере объекты в структуре данных в памяти преобразуются в XML-элементы.  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 Этот код создает следующий выходные данные XML:  
  
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
  
 Дополнительные сведения см. в разделе [Создание деревьев XML C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).  
  
## <a name="performing-operations-on-source-elements"></a>Выполнение операций с исходными элементами  
 Выходная последовательность не может содержать любые элементы или свойства элементов из исходной последовательности. Результатом может быть последовательность значений, вычисляемых с использованием исходных элементов в качестве входных аргументов.

 Следующий запрос принимает последовательность чисел, представляющих радиусы окружностей, вычисляет площадь каждой окружности и возвращает выходную последовательность, содержащую строки, отформатированные с учетом вычисленной площади.

 Каждая строка для выходной последовательности будет отформатирована с помощью [интерполяции строк](../../../language-reference/tokens/interpolated.md). Перед открывающей кавычкой в интерполированной строке будет находиться `$`, а операции будут выполняться внутри фигурных скобок, помещенных в интерполированную строку. После выполнения операций результаты будут объединены.
  
> [!NOTE]
> Вызов методов в выражениях запросов не поддерживается, если запрос будет преобразован в некоторую другую область. Например, невозможно вызвать обычный метод C# в [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], так как в SQL Server для него отсутствует контекст. Тем не менее можно сопоставить хранимые процедуры методов и вызвать их. Дополнительные сведения см. в разделе [Хранимые процедуры](../../../../framework/data/adonet/sql/linq/stored-procedures.md).  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a>См. также

- [LINQ (C#)](./index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)
- [LINQ to XML (C#)](../../../../standard/linq/linq-xml-overview.md)
- [Выражения запросов LINQ](../../../linq/index.md)
- [предложение select](../../../language-reference/keywords/select-clause.md)
