---
title: Директива x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432836"
---
# <a name="xarguments-directive"></a><span data-ttu-id="87174-102">Директива x:Arguments</span><span class="sxs-lookup"><span data-stu-id="87174-102">x:Arguments Directive</span></span>

<span data-ttu-id="87174-103">Пакеты аргументов в области построения для непараметрического объявления элемента объекта конструкции в XAML или для объявления объекта фабричного метода.</span><span class="sxs-lookup"><span data-stu-id="87174-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="87174-104">Использование элементов XAML (безпаратиров конструктор)</span><span class="sxs-lookup"><span data-stu-id="87174-104">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="87174-105">Использование элементов XAML (заводский метод)</span><span class="sxs-lookup"><span data-stu-id="87174-105">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="87174-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="87174-106">XAML Values</span></span>

|||
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="87174-107">Один или несколько элементов объекта, которые определяют аргументы, которые должны быть переданы резервному непараметрике конструктора или заводскому методу.</span><span class="sxs-lookup"><span data-stu-id="87174-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="87174-108">Типичное использование заключается в использовании текста инициализации в элементах объекта для указания фактических значений аргумента.</span><span class="sxs-lookup"><span data-stu-id="87174-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="87174-109">Смотрите раздел Примеры.</span><span class="sxs-lookup"><span data-stu-id="87174-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="87174-110">Порядок элементов значителен.</span><span class="sxs-lookup"><span data-stu-id="87174-110">The order of the elements is significant.</span></span> <span data-ttu-id="87174-111">Типы XAML в порядке должны соответствовать типам и порядку ввода перегрузки конструктора резервного или заводского метода.</span><span class="sxs-lookup"><span data-stu-id="87174-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="87174-112">Название заводского метода, который `x:Arguments` должен обрабатывать любые аргументы.</span><span class="sxs-lookup"><span data-stu-id="87174-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="87174-113">Зависимости</span><span class="sxs-lookup"><span data-stu-id="87174-113">Dependencies</span></span>

<span data-ttu-id="87174-114">`x:FactoryMethod`может изменять область `x:Arguments` и поведение, если применяется.</span><span class="sxs-lookup"><span data-stu-id="87174-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="87174-115">Если `x:FactoryMethod` нет, `x:Arguments` применяется к альтернативным (не по умолчанию) подписям конструкторов поддержки.</span><span class="sxs-lookup"><span data-stu-id="87174-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="87174-116">Если `x:FactoryMethod` указано, `x:Arguments` применяется к перегрузке названного метода.</span><span class="sxs-lookup"><span data-stu-id="87174-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="87174-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="87174-117">Remarks</span></span>

<span data-ttu-id="87174-118">XAML 2006 может поддерживать инициализацию без дефолта через текст инициализации.</span><span class="sxs-lookup"><span data-stu-id="87174-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="87174-119">Однако практическое применение метода инициализации текстового строительства ограничено.</span><span class="sxs-lookup"><span data-stu-id="87174-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="87174-120">Текст инициализации рассматривается как единая текстовая строка; Таким образом, он только добавляет возможность для одного параметрики, если конвертер типа не определен для поведения конструкции, который может разбирать пользовательские элементы информации и пользовательские делимитемые из строки.</span><span class="sxs-lookup"><span data-stu-id="87174-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="87174-121">Кроме того, строка текста для логики объектов потенциально является нативным преобразователем типа по умолчанию для обработки примитивов, кроме истинной строки.</span><span class="sxs-lookup"><span data-stu-id="87174-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="87174-122">Использование `x:Arguments` XAML не является использованием элемента свойства в типичном смысле, поскольку разметка директивы не ссылается на тип элемента, содержащего объект.</span><span class="sxs-lookup"><span data-stu-id="87174-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="87174-123">Это больше похоже на другие `x:Code` директивы, такие как, когда элемент обозначает диапазон, в котором разметка должна быть истолкована как иная, чем по умолчанию для содержимого ребенка.</span><span class="sxs-lookup"><span data-stu-id="87174-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="87174-124">В этом случае тип XAML каждого элемента объекта передает информацию о типах аргументов, которая используется parsers `x:Arguments` XAML для определения того, какой конкретный метод завода-конструктора пытается ссылаться на использование.</span><span class="sxs-lookup"><span data-stu-id="87174-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="87174-125">`x:Arguments`для построенного элемента объекта должен предшествовать любым другим элементам свойств, содержимому, внутреннему тексту или строкам инициализации элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="87174-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="87174-126">Элементы объекта `x:Arguments` внутри могут включать атрибуты и строки инициализации, как это разрешено типом XAML и его резервным конструктором или заводским методом.</span><span class="sxs-lookup"><span data-stu-id="87174-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="87174-127">Для объекта или аргументов можно указать пользовательские типы XAML или XAML, которые в противном случае находятся за пределами пространства имен XAML по умолчанию, ссылаясь на установленные отображения приставки.</span><span class="sxs-lookup"><span data-stu-id="87174-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="87174-128">Процессоры XAML используют следующие рекомендации для определения `x:Arguments` того, как аргументы, указанные в проекте, должны использоваться для построения объекта.</span><span class="sxs-lookup"><span data-stu-id="87174-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="87174-129">Если `x:FactoryMethod` указано, информация сравнивается с `x:FactoryMethod` указанной `x:FactoryMethod` (обратите внимание, что значение является именем метода, и названный метод может иметь перегрузки.</span><span class="sxs-lookup"><span data-stu-id="87174-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="87174-130">Если `x:FactoryMethod` не указано, информация сравнивается с набором всех общедоступных перегрузок объекта.</span><span class="sxs-lookup"><span data-stu-id="87174-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="87174-131">Затем логика обработки XAML сравнивает количество параметров и выбирает перегрузку с соответствующей арти.</span><span class="sxs-lookup"><span data-stu-id="87174-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="87174-132">Если совпадений несколько, процессор XAML должен сравнить типы параметров на основе типов XAML предоставленных элементов объекта.</span><span class="sxs-lookup"><span data-stu-id="87174-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="87174-133">Если совпадений несколько, поведение процессора XAML не определено.</span><span class="sxs-lookup"><span data-stu-id="87174-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="87174-134">Если `x:FactoryMethod` указано, но метод не может быть решен, процессор XAML должен выбросить исключение.</span><span class="sxs-lookup"><span data-stu-id="87174-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="87174-135">Использование `<x:Arguments>string</x:Arguments>` атрибута XAML технически возможно.</span><span class="sxs-lookup"><span data-stu-id="87174-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="87174-136">Тем не менее, это не дает никаких возможностей, помимо того, что можно было бы сделать иначе с помощью инициализации текста и преобразователей типа, и использование этого синтаксиса не является проектным намерением функций заводского метода XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="87174-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="87174-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="87174-137">Examples</span></span>

<span data-ttu-id="87174-138">В следующем примере показана непараметрная подпись конструктора, `x:Arguments` а затем использование XAML, которое получает доступ к этой подписи.</span><span class="sxs-lookup"><span data-stu-id="87174-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="87174-139">В следующем примере показана подпись целевого фабричного метода, а затем использование XAML, которое `x:Arguments` получает доступ к этой подписи.</span><span class="sxs-lookup"><span data-stu-id="87174-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="87174-140">См. также</span><span class="sxs-lookup"><span data-stu-id="87174-140">See also</span></span>

- [<span data-ttu-id="87174-141">Определение пользовательских типов для использования со службами XAML .NET</span><span class="sxs-lookup"><span data-stu-id="87174-141">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="87174-142">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="87174-142">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
