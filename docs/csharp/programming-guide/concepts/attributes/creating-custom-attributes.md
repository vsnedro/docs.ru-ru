---
title: Создание настраиваемых атрибутов (C#)
description: Узнайте, как создавать настраиваемые атрибуты в C#, определяя класс атрибута, производный от класса Attribute.
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: 6946b707134b2bdbc245b8786f144517a5870440
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202609"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="8805f-103">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="8805f-103">Creating Custom Attributes (C#)</span></span>

<span data-ttu-id="8805f-104">Собственные настраиваемые атрибуты можно создать, определив класс атрибута, то есть класс, прямо или косвенно наследующий от <xref:System.Attribute>, который упрощает задание определений атрибутов в метаданных.</span><span class="sxs-lookup"><span data-stu-id="8805f-104">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="8805f-105">Предположим, что требуется пометить тип тегом с именем программиста, который его разработал.</span><span class="sxs-lookup"><span data-stu-id="8805f-105">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="8805f-106">Вы можете определить класс настраиваемых атрибутов `Author`:</span><span class="sxs-lookup"><span data-stu-id="8805f-106">You might define a custom `Author` attribute class:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class AuthorAttribute : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public AuthorAttribute(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 <span data-ttu-id="8805f-107">Имя класса `AuthorAttribute` является именем атрибута, `Author` плюс суффикс `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="8805f-107">The class name `AuthorAttribute` is the attribute's name, `Author`, plus the `Attribute` suffix.</span></span> <span data-ttu-id="8805f-108">Он является производным от `System.Attribute`, поэтому это класс настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="8805f-108">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="8805f-109">Параметры конструктора являются позиционными параметрами настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="8805f-109">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="8805f-110">В этом примере `name` является позиционным параметром.</span><span class="sxs-lookup"><span data-stu-id="8805f-110">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="8805f-111">Все открытые поля или свойства, доступные для чтения и записи, являются именованными параметрами.</span><span class="sxs-lookup"><span data-stu-id="8805f-111">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="8805f-112">В этом случае `version` — единственный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="8805f-112">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="8805f-113">Обратите внимание на использование атрибута `AttributeUsage`, делающего атрибут `Author` допустимым только для класса и объявлений `struct`.</span><span class="sxs-lookup"><span data-stu-id="8805f-113">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="8805f-114">Этот атрибут можно использовать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8805f-114">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="8805f-115">`AttributeUsage` имеет именованный параметр, `AllowMultiple`, с помощью которого можно задавать для настраиваемого атрибута однократное или многократное использование.</span><span class="sxs-lookup"><span data-stu-id="8805f-115">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="8805f-116">В следующем примере кода создается многократно используемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="8805f-116">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class AuthorAttribute : System.Attribute  
```  
  
 <span data-ttu-id="8805f-117">В следующем примере кода несколько атрибутов одного типа применяются к классу.</span><span class="sxs-lookup"><span data-stu-id="8805f-117">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8805f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8805f-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="8805f-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8805f-119">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="8805f-120">Написание настраиваемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="8805f-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="8805f-121">Отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="8805f-121">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="8805f-122">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="8805f-122">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="8805f-123">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="8805f-123">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="8805f-124">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="8805f-124">AttributeUsage (C#)</span></span>](../../../language-reference/attributes/general.md)
