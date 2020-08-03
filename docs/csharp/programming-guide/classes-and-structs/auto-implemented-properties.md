---
title: Руководство по программированию на C#. Автоматически реализуемые свойства
description: Для автоматического реализуемого свойства в C# компилятор создает закрытое анонимное резервное поле, доступ к которому осуществляется только через методы доступа get и set свойства.
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: f58f9a23f26bde7e80d834528d94e38af1231e7b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474479"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="b78ab-103">Автоматически реализуемые свойства (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b78ab-103">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="b78ab-104">В C# 3.0 и более поздних версиях автоматически реализуемые свойства делают объявление свойств более лаконичным, когда в методах доступа к свойствам не требуется дополнительная логика.</span><span class="sxs-lookup"><span data-stu-id="b78ab-104">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="b78ab-105">Они также позволяют клиентскому коду создавать объекты.</span><span class="sxs-lookup"><span data-stu-id="b78ab-105">They also enable client code to create objects.</span></span> <span data-ttu-id="b78ab-106">При объявлении свойства, как показано в следующем примере, компилятор создает закрытое анонимное резервное поле, которое может быть доступно только через методы доступа `get` и `set` свойства.</span><span class="sxs-lookup"><span data-stu-id="b78ab-106">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="b78ab-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b78ab-107">Example</span></span>

<span data-ttu-id="b78ab-108">В следующем примере показан простой класс, имеющий несколько автоматически реализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="b78ab-108">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="b78ab-109">В интерфейсах невозможно объявлять автоматически реализуемые свойства.</span><span class="sxs-lookup"><span data-stu-id="b78ab-109">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="b78ab-110">Автоматически реализуемые свойства объявляют резервное поле частного экземпляра, а интерфейсы могут не объявлять поля экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b78ab-110">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="b78ab-111">Объявление свойства в интерфейсе без определения тела приводит к объявлению свойства с методами доступа, которые должны реализовываться каждым типом, реализующим этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b78ab-111">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="b78ab-112">В C# 6 и более поздних версиях можно инициализировать автоматически реализуемые свойства аналогично полям.</span><span class="sxs-lookup"><span data-stu-id="b78ab-112">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

<span data-ttu-id="b78ab-113">Класс, который показан в предыдущем примере, является изменяемым.</span><span class="sxs-lookup"><span data-stu-id="b78ab-113">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="b78ab-114">Клиентский код может изменить значения в объектах после создания.</span><span class="sxs-lookup"><span data-stu-id="b78ab-114">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="b78ab-115">В сложных классах, которые содержат значительные возможности (методы) и данные, часто необходимо иметь открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="b78ab-115">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="b78ab-116">Однако для небольших классов или структур, которые просто инкапсулируют набор значений (данных) и имеют мало функциональных возможностей или совсем их не имеют, вы должны сделать объекты неизменяемыми либо путем объявления метода доступа set как [закрытого](../../language-reference/keywords/private.md) (неизменяемого для потребителей), либо путем объявления только метода доступа get (неизменяемого везде, кроме конструктора).</span><span class="sxs-lookup"><span data-stu-id="b78ab-116">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="b78ab-117">Дополнительные сведения см. в статье [Практическое руководство. Реализация облегченного класса с автоматически реализуемыми свойствами](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b78ab-117">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b78ab-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b78ab-118">See also</span></span>

- [<span data-ttu-id="b78ab-119">Свойства</span><span class="sxs-lookup"><span data-stu-id="b78ab-119">Properties</span></span>](./properties.md)
- [<span data-ttu-id="b78ab-120">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="b78ab-120">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
