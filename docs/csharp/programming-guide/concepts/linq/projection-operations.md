---
title: Операции проекции (C#)
description: Узнайте об операциях проецирования. Эти операции позволяют преобразовать объект в новую форму, которая часто состоит только из свойств, которые будут использоваться позже.
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: 6128b1bb2e7ba3dbb1b428d475acc307ba931013
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186007"
---
# <a name="projection-operations-c"></a><span data-ttu-id="0c9d9-104">Операции проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="0c9d9-104">Projection Operations (C#)</span></span>

<span data-ttu-id="0c9d9-105">Проекцией называют операцию преобразования объекта в новую форму, которая часто состоит только из тех его свойств, которые будут использоваться впоследствии.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-105">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="0c9d9-106">С помощью проекции можно создать новый тип, построенный из каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-106">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="0c9d9-107">Вы можете проецировать свойство и выполнять над ним математические функции.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-107">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="0c9d9-108">Также можно проецировать исходный объект, не изменяя его.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-108">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="0c9d9-109">Методы стандартных операторов запросов, которые выполняют проецирование, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-109">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c9d9-110">Методы</span><span class="sxs-lookup"><span data-stu-id="0c9d9-110">Methods</span></span>  
  
|<span data-ttu-id="0c9d9-111">Имя метода</span><span class="sxs-lookup"><span data-stu-id="0c9d9-111">Method Name</span></span>|<span data-ttu-id="0c9d9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0c9d9-112">Description</span></span>|<span data-ttu-id="0c9d9-113">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="0c9d9-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="0c9d9-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0c9d9-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="0c9d9-115">Выбрать</span><span class="sxs-lookup"><span data-stu-id="0c9d9-115">Select</span></span>|<span data-ttu-id="0c9d9-116">Проецирует значения, основанные на функции преобразования.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-116">Projects values that are based on a transform function.</span></span>|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0c9d9-117">SelectMany</span><span class="sxs-lookup"><span data-stu-id="0c9d9-117">SelectMany</span></span>|<span data-ttu-id="0c9d9-118">Проецирует последовательности значений, основанных на функции преобразования, а затем выравнивает их в одну последовательность.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-118">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="0c9d9-119">Использование нескольких предложений `from`</span><span class="sxs-lookup"><span data-stu-id="0c9d9-119">Use multiple `from` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="0c9d9-120">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="0c9d9-120">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="0c9d9-121">Выбрать</span><span class="sxs-lookup"><span data-stu-id="0c9d9-121">Select</span></span>  

 <span data-ttu-id="0c9d9-122">В приведенном ниже примере предложение `select` используется для проецирования первой буквы из каждой строки в списке строк.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-122">The following example uses the `select` clause to project the first letter from each string in a list of strings.</span></span>  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a><span data-ttu-id="0c9d9-123">SelectMany</span><span class="sxs-lookup"><span data-stu-id="0c9d9-123">SelectMany</span></span>  

 <span data-ttu-id="0c9d9-124">В приведенном ниже примере несколько предложений `from` используются для проецирования каждого слова из каждой строки в списке строк.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-124">The following example uses multiple `from` clauses  to project each word from each string in a list of strings.</span></span>  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="0c9d9-125">Select или SelectMany</span><span class="sxs-lookup"><span data-stu-id="0c9d9-125">Select versus SelectMany</span></span>  

 <span data-ttu-id="0c9d9-126">Задача обоих методов `Select()` и `SelectMany()` заключается в создании результирующего значения (или значений) из исходных значений.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-126">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="0c9d9-127">`Select()` создает один результат для каждого исходного значения.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-127">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="0c9d9-128">Таким образом, общий результат является коллекцией, имеющей то же количество элементов, что и исходная коллекция.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-128">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="0c9d9-129">`SelectMany()`, напротив, создает общий результат, содержащий соединенные подколлекции из каждого исходного значения.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-129">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="0c9d9-130">Функция преобразования, которая передается в качестве аргумента методу `SelectMany()`, должна возвращать перечисляемую последовательность значений для каждого исходного значения.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-130">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="0c9d9-131">Эти перечисляемые последовательности затем объединяются `SelectMany()` для создания одной большой последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-131">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="0c9d9-132">На двух рисунках, приведенных ниже, показаны принципиальные различия между работой этих двух методов.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-132">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="0c9d9-133">В обоих случаях предполагается, что функция выбора (преобразования) выбирает массив цветов из каждого исходного значения.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-133">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="0c9d9-134">На этом рисунке представлено, как `Select()` возвращает коллекцию, которая имеет то же количество элементов, что и исходная коллекция.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-134">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 ![График, отображающий действие Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)  
  
 <span data-ttu-id="0c9d9-136">На этом рисунке показано, как `SelectMany()` объединяет промежуточные последовательности массивов в один конечный результат, содержащий все значения из промежуточных массивов.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-136">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 ![График, отображающий действие SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )  
  
### <a name="code-example"></a><span data-ttu-id="0c9d9-138">Пример кода</span><span class="sxs-lookup"><span data-stu-id="0c9d9-138">Code Example</span></span>  

 <span data-ttu-id="0c9d9-139">В приведенном ниже примере сравнивается действие `Select()` и `SelectMany()`.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-139">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="0c9d9-140">Код создает "букет" из цветов путем получения первых двух элементов из каждого списка названий цветов в исходной коллекции.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-140">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="0c9d9-141">В этом примере отдельное значение, используемое функцией преобразования <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>, представляет собой коллекцию значений.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-141">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="0c9d9-142">Этот требует дополнительного цикла `foreach` для перечисления каждой строки в каждой подпоследовательности.</span><span class="sxs-lookup"><span data-stu-id="0c9d9-142">This requires the extra `foreach` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c9d9-143">См. также</span><span class="sxs-lookup"><span data-stu-id="0c9d9-143">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="0c9d9-144">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="0c9d9-144">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="0c9d9-145">предложение select</span><span class="sxs-lookup"><span data-stu-id="0c9d9-145">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
- [<span data-ttu-id="0c9d9-146">Заполнение коллекций объектов из нескольких источников (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0c9d9-146">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
- [<span data-ttu-id="0c9d9-147">Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0c9d9-147">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
