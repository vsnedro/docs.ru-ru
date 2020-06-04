---
title: Создание настраиваемых атрибутов
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 84b400c2fa1b2d4019eec32092f954d680e64978
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400698"
---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="1a5e2-102">Creating Custom Attributes (Visual Basic) (Создание настраиваемых атрибутов (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="1a5e2-102">Creating Custom Attributes (Visual Basic)</span></span>

<span data-ttu-id="1a5e2-103">Собственные настраиваемые атрибуты можно создать, определив класс атрибута, то есть класс, прямо или косвенно наследующий от <xref:System.Attribute>, который упрощает задание определений атрибутов в метаданных.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="1a5e2-104">Предположим, что требуется пометить тип тегом с именем программиста, который его разработал.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="1a5e2-105">Вы можете определить класс настраиваемых атрибутов `Author`:</span><span class="sxs-lookup"><span data-stu-id="1a5e2-105">You might define a custom `Author` attribute class:</span></span>

```vb
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct)>
Public Class Author
    Inherits System.Attribute
    Private name As String
    Public version As Double
    Sub New(ByVal authorName As String)
        name = authorName
        version = 1.0
    End Sub
End Class
```

<span data-ttu-id="1a5e2-106">Имя класса — это имя атрибута, `Author`.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="1a5e2-107">Он является производным от `System.Attribute`, поэтому это класс настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="1a5e2-108">Параметры конструктора являются позиционными параметрами настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="1a5e2-109">В этом примере `name` является позиционным параметром.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="1a5e2-110">Все открытые поля или свойства, доступные для чтения и записи, являются именованными параметрами.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="1a5e2-111">В этом случае `version` — единственный именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="1a5e2-112">Обратите внимание на использование атрибута `AttributeUsage`, делающего атрибут `Author` допустимым только для класса и объявлений `Structure`.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>

<span data-ttu-id="1a5e2-113">Этот атрибут можно использовать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1a5e2-113">You could use this new attribute as follows:</span></span>

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

<span data-ttu-id="1a5e2-114">`AttributeUsage` имеет именованный параметр, `AllowMultiple`, с помощью которого можно задавать для настраиваемого атрибута однократное или многократное использование.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="1a5e2-115">В следующем примере кода создается многократно используемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-115">In the following code example, a multiuse attribute is created.</span></span>

```vb
' multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
```

<span data-ttu-id="1a5e2-116">В следующем примере кода несколько атрибутов одного типа применяются к классу.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>

```vb
<Author("P. Ackerman", Version:=1.1),
Author("R. Koch", Version:=1.2)>
Class SampleClass
    ' P. Ackerman's code goes here...
    ' R. Koch's code goes here...
End Class
```

> [!NOTE]
> <span data-ttu-id="1a5e2-117">Если класс атрибутов содержит свойство, это свойство должно быть доступно для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="1a5e2-117">If your attribute class contains a property, that property must be read-write.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a5e2-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1a5e2-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="1a5e2-119">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a5e2-119">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="1a5e2-120">Написание настраиваемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="1a5e2-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- <span data-ttu-id="1a5e2-121">[Reflection (Visual Basic)](../reflection.md) (Отражение (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="1a5e2-121">[Reflection (Visual Basic)](../reflection.md)</span></span>
- [<span data-ttu-id="1a5e2-122">Атрибуты (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a5e2-122">Attributes (Visual Basic)</span></span>](../../../language-reference/attributes.md)
- <span data-ttu-id="1a5e2-123">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="1a5e2-123">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)</span></span>
- [<span data-ttu-id="1a5e2-124">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a5e2-124">AttributeUsage (Visual Basic)</span></span>](attributeusage.md)
