---
title: Ковариация и контравариантность (C#)
description: Сведения о ковариации и контравариантности, а также о том, как они влияют на совместимость назначений. Пример кода демонстрирует различия между ними.
ms.date: 07/20/2015
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
ms.openlocfilehash: d0309ec1bb3161412433e1b44e8e35410911b38d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176335"
---
# <a name="covariance-and-contravariance-c"></a><span data-ttu-id="0d5e8-104">Ковариация и контравариантность (C#)</span><span class="sxs-lookup"><span data-stu-id="0d5e8-104">Covariance and Contravariance (C#)</span></span>

<span data-ttu-id="0d5e8-105">В C# ковариация и контрвариантность позволяют использовать неявное преобразование ссылок для типов массивов и делегатов, а также для аргументов универсального типа.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-105">In C#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="0d5e8-106">Ковариация сохраняет совместимость присваивания, а при контрвариантности присваивание начинает работать противоположным образом.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-106">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="0d5e8-107">Следующий код показывает разницу между совместимостью присваивания, ковариацией и контрвариантностью.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-107">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
```csharp  
// Assignment compatibility.
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.
object obj = str;  
  
// Covariance.
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument
// is assigned to an object instantiated with a less derived type argument.
// Assignment compatibility is preserved.
IEnumerable<object> objects = strings;  
  
// Contravariance.
// Assume that the following method is in the class:
// static void SetObject(object o) { }
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument
// is assigned to an object instantiated with a more derived type argument.
// Assignment compatibility is reversed.
Action<string> actString = actObject;  
```  
  
 <span data-ttu-id="0d5e8-108">Ковариация для массивов позволяет неявно преобразовать массив более производного типа в массив менее производного типа.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-108">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="0d5e8-109">Но эта операция не является типобезопасной, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-109">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 <span data-ttu-id="0d5e8-110">Поддержка ковариации и контрвариантности для групп методов позволяет сопоставить сигнатуры методов с типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-110">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="0d5e8-111">За счет этого вы можете назначать делегатам не только методы с совпадающими сигнатурами, но и методы, которые возвращают более производные типы (ковариация) или принимают параметры с менее производными типами (контрвариантность), чем задает тип делегата.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-111">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="0d5e8-112">Дополнительные сведения см. в разделах [Вариативность в делегатах (C#)](./variance-in-delegates.md) и [Использование вариативности в делегатах (C#)](./using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="0d5e8-112">For more information, see [Variance in Delegates (C#)](./variance-in-delegates.md) and [Using Variance in Delegates (C#)](./using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="0d5e8-113">В следующем примере кода демонстрируется поддержка ковариации и контрвариантности для групп методов.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-113">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 <span data-ttu-id="0d5e8-114">В .NET Framework 4 и более поздних версиях язык C# поддерживает ковариацию и контрвариантность для универсальных интерфейсов и делегатов, а также позволяет выполнять неявное преобразование параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-114">In .NET Framework 4 and later versions, C# supports covariance and contravariance in generic interfaces and delegates and allows for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="0d5e8-115">Дополнительные сведения см. в разделах [Вариативность в универсальных интерфейсах (C#)](./variance-in-generic-interfaces.md) и [Вариативность в делегатах (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="0d5e8-115">For more information, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md) and [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="0d5e8-116">В следующем примере кода показано неявное преобразование ссылок для универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-116">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="0d5e8-117">Универсальный интерфейс или делегат называется *вариантным*, если его универсальные параметры объявлены ковариантными или контрвариантными.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-117">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="0d5e8-118">C# позволяет вам создавать собственные вариантные интерфейсы и делегаты.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-118">C# enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="0d5e8-119">Дополнительные сведения см. в разделах [Создание вариантных универсальных интерфейсов (C#)](./creating-variant-generic-interfaces.md) и [Вариативность в делегатах (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="0d5e8-119">For more information, see [Creating Variant Generic Interfaces (C#)](./creating-variant-generic-interfaces.md) and [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="0d5e8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0d5e8-120">Related Topics</span></span>  
  
|<span data-ttu-id="0d5e8-121">Заголовок</span><span class="sxs-lookup"><span data-stu-id="0d5e8-121">Title</span></span>|<span data-ttu-id="0d5e8-122">Описание</span><span class="sxs-lookup"><span data-stu-id="0d5e8-122">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0d5e8-123">Вариативность в универсальных интерфейсах (C#)</span><span class="sxs-lookup"><span data-stu-id="0d5e8-123">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)|<span data-ttu-id="0d5e8-124">В этом разделе описываются ковариантность и контрвариантность в универсальных интерфейсах, а также представлен список вариативных универсальных интерфейсов в .NET.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-124">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in .NET.</span></span>|  
|[<span data-ttu-id="0d5e8-125">Создание вариантных универсальных интерфейсов (C#)</span><span class="sxs-lookup"><span data-stu-id="0d5e8-125">Creating Variant Generic Interfaces (C#)</span></span>](./creating-variant-generic-interfaces.md)|<span data-ttu-id="0d5e8-126">Узнайте, как создавать ваши собственные вариантные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-126">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="0d5e8-127">Использование вариативности в интерфейсах для универсальных коллекций (C#)</span><span class="sxs-lookup"><span data-stu-id="0d5e8-127">Using Variance in Interfaces for Generic Collections (C#)</span></span>](./using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="0d5e8-128">Узнайте, как использовать поддержку ковариации и контрвариантности в интерфейсах <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IComparable%601> для многократного использования кода.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-128">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="0d5e8-129">Вариативность в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="0d5e8-129">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)|<span data-ttu-id="0d5e8-130">В этом разделе описываются ковариантность и контрвариантность в универсальных и неуниверсальных делегатах, а также представлен список вариантных универсальных делегатов в .NET.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-130">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in .NET.</span></span>|  
|[<span data-ttu-id="0d5e8-131">Использование вариативности в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="0d5e8-131">Using Variance in Delegates (C#)</span></span>](./using-variance-in-delegates.md)|<span data-ttu-id="0d5e8-132">Узнайте, как использовать поддержку ковариации и контрвариантности в неуниверсальных делегатах для сопоставления сигнатур методов с типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-132">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|[<span data-ttu-id="0d5e8-133">Использование вариативности в универсальных методах-делегатах Func и Action (C#)</span><span class="sxs-lookup"><span data-stu-id="0d5e8-133">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="0d5e8-134">Узнайте, как использовать поддержку ковариации и контрвариантности в делегатах `Func` и `Action` для многократного использования кода.</span><span class="sxs-lookup"><span data-stu-id="0d5e8-134">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|
