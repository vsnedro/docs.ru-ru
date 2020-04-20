---
title: Создание настраиваемых атрибутов (C#)
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: ec959723c339a13a40fd62388421ceacb736dfca
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389561"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="05613-102">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="05613-102">Creating Custom Attributes (C#)</span></span>
<span data-ttu-id="05613-103">Собственные настраиваемые атрибуты можно создать, определив класс атрибута, то есть класс, прямо или косвенно наследующий от <xref:System.Attribute>, который упрощает задание определений атрибутов в метаданных.</span><span class="sxs-lookup"><span data-stu-id="05613-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="05613-104">Предположим, что требуется пометить тип тегом с именем программиста, который его разработал.</span><span class="sxs-lookup"><span data-stu-id="05613-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="05613-105">Вы можете определить класс настраиваемых атрибутов `Author`:</span><span class="sxs-lookup"><span data-stu-id="05613-105">You might define a custom `Author` attribute class:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class Author : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 <span data-ttu-id="05613-106">Имя класса — это имя атрибута, `Author`.</span><span class="sxs-lookup"><span data-stu-id="05613-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="05613-107">Он является производным от `System.Attribute`, поэтому это класс настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="05613-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="05613-108">Параметры конструктора являются позиционными параметрами настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="05613-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="05613-109">В этом примере `name` является позиционным параметром.</span><span class="sxs-lookup"><span data-stu-id="05613-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="05613-110">Все открытые поля или свойства, доступные для чтения и записи, являются именованными параметрами.</span><span class="sxs-lookup"><span data-stu-id="05613-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="05613-111">В этом случае `version` — единственный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="05613-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="05613-112">Обратите внимание на использование атрибута `AttributeUsage`, делающего атрибут `Author` допустимым только для класса и объявлений `struct`.</span><span class="sxs-lookup"><span data-stu-id="05613-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="05613-113">Этот атрибут можно использовать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="05613-113">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="05613-114">`AttributeUsage` имеет именованный параметр, `AllowMultiple`, с помощью которого можно задавать для настраиваемого атрибута однократное или многократное использование.</span><span class="sxs-lookup"><span data-stu-id="05613-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="05613-115">В следующем примере кода создается многократно используемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="05613-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 <span data-ttu-id="05613-116">В следующем примере кода несколько атрибутов одного типа применяются к классу.</span><span class="sxs-lookup"><span data-stu-id="05613-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="05613-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="05613-117">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="05613-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="05613-118">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="05613-119">Написание настраиваемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="05613-119">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="05613-120">Отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="05613-120">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="05613-121">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="05613-121">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="05613-122">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="05613-122">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="05613-123">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="05613-123">AttributeUsage (C#)</span></span>](../../../language-reference/attributes/general.md)
