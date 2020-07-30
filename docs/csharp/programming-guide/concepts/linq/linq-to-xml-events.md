---
title: События LINQ to XML (C#)
description: Добавьте события LINQ to XML в C# для экземпляра XObject. Обработчик событий получает события при изменении дерева XML для этого XObject.
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 576b0a5d0472bddd66e01d3bef8f3affa1c9458b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165415"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="21e19-104">События LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="21e19-104">LINQ to XML Events (C#)</span></span>
<span data-ttu-id="21e19-105">События [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют получать уведомления, когда изменяется дерево XML.</span><span class="sxs-lookup"><span data-stu-id="21e19-105">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="21e19-106">Можно добавить события в экземпляр любого объекта <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="21e19-106">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="21e19-107">Обработчик события будет получать уведомления об изменениях объекта <xref:System.Xml.Linq.XObject> и всех его потомков.</span><span class="sxs-lookup"><span data-stu-id="21e19-107">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="21e19-108">Например, можно добавить обработчик события в корень дерева и обрабатывать все изменения дерева в этом обработчике события.</span><span class="sxs-lookup"><span data-stu-id="21e19-108">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="21e19-109">Примеры таких событий [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] см. в разделах <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="21e19-109">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="21e19-110">Типы и события</span><span class="sxs-lookup"><span data-stu-id="21e19-110">Types and Events</span></span>  
 <span data-ttu-id="21e19-111">Используйте следующие типы при работе с событиями.</span><span class="sxs-lookup"><span data-stu-id="21e19-111">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="21e19-112">Тип</span><span class="sxs-lookup"><span data-stu-id="21e19-112">Type</span></span>|<span data-ttu-id="21e19-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="21e19-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="21e19-114">Задает тип события, когда событие вызывается объектом <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="21e19-114">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="21e19-115">Предоставляет данные для событий <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="21e19-115">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="21e19-116">При изменении дерева XML возникают следующие события.</span><span class="sxs-lookup"><span data-stu-id="21e19-116">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="21e19-117">Событие</span><span class="sxs-lookup"><span data-stu-id="21e19-117">Event</span></span>|<span data-ttu-id="21e19-118">Описание</span><span class="sxs-lookup"><span data-stu-id="21e19-118">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="21e19-119">Возникает непосредственно перед тем, как объект <xref:System.Xml.Linq.XObject> или какой-либо его потомок изменяется.</span><span class="sxs-lookup"><span data-stu-id="21e19-119">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="21e19-120">Возникает, когда изменился объект <xref:System.Xml.Linq.XObject> или один из его потомков.</span><span class="sxs-lookup"><span data-stu-id="21e19-120">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="21e19-121">Пример</span><span class="sxs-lookup"><span data-stu-id="21e19-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="21e19-122">Описание</span><span class="sxs-lookup"><span data-stu-id="21e19-122">Description</span></span>  
 <span data-ttu-id="21e19-123">События полезны, когда нужно поддержать какие-либо статистические данные в дереве XML.</span><span class="sxs-lookup"><span data-stu-id="21e19-123">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="21e19-124">Например, нужно рассчитать сумму элементов строки.</span><span class="sxs-lookup"><span data-stu-id="21e19-124">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="21e19-125">Следующий пример использует события для подсчета суммы всех дочерних элементов сложного элемента `Items`.</span><span class="sxs-lookup"><span data-stu-id="21e19-125">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="21e19-126">Код</span><span class="sxs-lookup"><span data-stu-id="21e19-126">Code</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="21e19-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="21e19-127">Comments</span></span>  
 <span data-ttu-id="21e19-128">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="21e19-128">This code produces the following output:</span></span>  
  
```output  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  