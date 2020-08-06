---
title: Потоковая передача фрагментов XML с доступом к сведениям заголовка (C#)
description: Сведения о потоковой передаче фрагментов XML с доступом к данным заголовка. Методы потоковой передачи помогают избежать чрезмерного использования памяти.
ms.date: 07/20/2015
ms.assetid: 7f242770-b0c7-418d-894b-643215e1f8aa
ms.openlocfilehash: 8bfded96ea1fa6b096d56ae0736002b9062d58b6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303222"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-c"></a><span data-ttu-id="d32b2-104">Потоковая передача фрагментов XML с доступом к сведениям заголовка (C#)</span><span class="sxs-lookup"><span data-stu-id="d32b2-104">How to stream XML fragments with access to header information (C#)</span></span>
<span data-ttu-id="d32b2-105">Иногда приходится считывать достаточно большие XML-файлы и разрабатывать приложения таким образом, чтобы объем памяти, используемой этим приложением, был прогнозируемым.</span><span class="sxs-lookup"><span data-stu-id="d32b2-105">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="d32b2-106">Если попытаться заполнить XML-дерево большим XML-файлом, используемый объем памяти будет пропорционален размеру файла, то есть излишним.</span><span class="sxs-lookup"><span data-stu-id="d32b2-106">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="d32b2-107">Поэтому следует вместо этого использовать потоки.</span><span class="sxs-lookup"><span data-stu-id="d32b2-107">Therefore, you should use a streaming technique instead.</span></span>  
  
<span data-ttu-id="d32b2-108">Одна из возможностей состоит в том, чтобы разработать приложение с использованием метода <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d32b2-108">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="d32b2-109">При этом для создания запроса к XML-дереву можно использовать LINQ.</span><span class="sxs-lookup"><span data-stu-id="d32b2-109">However, you might want to use LINQ to query the XML tree.</span></span> <span data-ttu-id="d32b2-110">В этом случае можно написать собственный пользовательский метод оси.</span><span class="sxs-lookup"><span data-stu-id="d32b2-110">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="d32b2-111">См. сведения см. в руководстве по [созданию метода оси LINQ to XML (C#)](./how-to-write-a-linq-to-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="d32b2-111">For more information, see [How to write a LINQ to XML axis method (C#)](./how-to-write-a-linq-to-xml-axis-method.md).</span></span>
  
 <span data-ttu-id="d32b2-112">Чтобы написать собственный метод оси, нужно написать небольшой метод, который использует метод <xref:System.Xml.XmlReader> для считывания узлов, до тех пор пока не достигнет одного из интересующих вас узлов.</span><span class="sxs-lookup"><span data-stu-id="d32b2-112">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="d32b2-113">Затем метод вызывает метод <xref:System.Xml.Linq.XNode.ReadFrom%2A>, который читает из объекта <xref:System.Xml.XmlReader> и создает экземпляр фрагмента XML.</span><span class="sxs-lookup"><span data-stu-id="d32b2-113">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="d32b2-114">Затем он выдает фрагмент с помощью ключевого слова `yield return` методу, который выполняет перечисление по пользовательскому методу оси.</span><span class="sxs-lookup"><span data-stu-id="d32b2-114">It then yields each fragment through `yield return` to the method that is enumerating your custom axis method.</span></span> <span data-ttu-id="d32b2-115">После этого можно написать запросы в LINQ на основе пользовательского метода оси.</span><span class="sxs-lookup"><span data-stu-id="d32b2-115">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="d32b2-116">Использование потоков лучше всего уместно в ситуациях, когда требуется обработать исходный документ только один раз, и элементы можно обрабатывать в порядке их следования в документе.</span><span class="sxs-lookup"><span data-stu-id="d32b2-116">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="d32b2-117">Некоторые стандартные операторы запросов, например <xref:System.Linq.Enumerable.OrderBy%2A>, проходят через источник, собирают все данные, сортируют их и выдают первый элемент последовательности.</span><span class="sxs-lookup"><span data-stu-id="d32b2-117">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="d32b2-118">Если вы используете оператор запроса, который материализует источник раньше, чем выбирает первый элемент, занимаемая память увеличится.</span><span class="sxs-lookup"><span data-stu-id="d32b2-118">If you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d32b2-119">Пример</span><span class="sxs-lookup"><span data-stu-id="d32b2-119">Example</span></span>  

<span data-ttu-id="d32b2-120">Иногда проблема становится немного интереснее.</span><span class="sxs-lookup"><span data-stu-id="d32b2-120">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="d32b2-121">В следующем XML-документе потребитель пользовательского метода оси должен знать имя клиента, которому принадлежит каждый элемент.</span><span class="sxs-lookup"><span data-stu-id="d32b2-121">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="d32b2-122">Подход, который используется в данном примере, также отслеживает эти данные о заголовках, сохраняет эти данные о заголовках, а затем строит небольшое XML-дерево, которое содержит и эти данные о заголовках, и сведения, которые вы перечисляете.</span><span class="sxs-lookup"><span data-stu-id="d32b2-122">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="d32b2-123">При использовании этого подхода метод оси позволяет получить это новое небольшое XML-дерево.</span><span class="sxs-lookup"><span data-stu-id="d32b2-123">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="d32b2-124">Тогда запрос имеет доступ к данным о заголовках наряду с вашими сведениями.</span><span class="sxs-lookup"><span data-stu-id="d32b2-124">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="d32b2-125">При данном подходе используется малый объем памяти.</span><span class="sxs-lookup"><span data-stu-id="d32b2-125">This approach has a small memory footprint.</span></span> <span data-ttu-id="d32b2-126">После того как выданы все данные фрагмента XML, ссылки на предыдущий фрагмент не сохраняются, и он становится пригодным для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d32b2-126">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="d32b2-127">Этот метод создает в куче много объектов с небольшим периодом жизни.</span><span class="sxs-lookup"><span data-stu-id="d32b2-127">This technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="d32b2-128">В следующем примере показано, как реализовать и использовать пользовательский метод оси, который осуществляет потоковую передачу XML-фрагментов из файла, указанного в URI.</span><span class="sxs-lookup"><span data-stu-id="d32b2-128">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="d32b2-129">Эта настраиваемая ось создана так, чтобы ожидать документ с элементами `Customer`, `Name` и `Item`, упорядоченными, как в указанном документе `Source.xml`.</span><span class="sxs-lookup"><span data-stu-id="d32b2-129">This custom axis is written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="d32b2-130">Это упрощенная реализация.</span><span class="sxs-lookup"><span data-stu-id="d32b2-130">It is a simplistic implementation.</span></span> <span data-ttu-id="d32b2-131">Будет подготовлена более надежная реализация анализа неверных документов.</span><span class="sxs-lookup"><span data-stu-id="d32b2-131">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null) {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    XElement xmlTree = new XElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        where (int)el.Element("Key") >= 3 && (int)el.Element("Key") <= 7  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    Console.WriteLine(xmlTree);  
}  
```  
  
 <span data-ttu-id="d32b2-132">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="d32b2-132">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
</Root>  
```  
