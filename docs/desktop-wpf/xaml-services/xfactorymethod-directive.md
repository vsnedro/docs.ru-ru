---
title: Директива x:FactoryMethod
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432788"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="63f41-102">Директива x:FactoryMethod</span><span class="sxs-lookup"><span data-stu-id="63f41-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="63f41-103">Определяет метод, отличный от конструктора, который процессор XAML должен использовать для инициализации объекта после разрешения его типа резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="63f41-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="63f41-104">Использование атрибутов XAML, без x:Аргументы</span><span class="sxs-lookup"><span data-stu-id="63f41-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="63f41-105">Использование атрибутов XAML, x:Аргументы как элемент (ы)</span><span class="sxs-lookup"><span data-stu-id="63f41-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="63f41-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="63f41-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="63f41-107">Название метода строки метода, который процессоры XAML `object`называют для инициализации экземпляра, указанного как.</span><span class="sxs-lookup"><span data-stu-id="63f41-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="63f41-108">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="63f41-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="63f41-109">Один или несколько элементов объекта для объектов, определяющих параметры фабричного метода.</span><span class="sxs-lookup"><span data-stu-id="63f41-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="63f41-110">Порядок значителен; он означает порядок, в котором аргументы должны быть переданы на заводский метод.</span><span class="sxs-lookup"><span data-stu-id="63f41-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63f41-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="63f41-111">Remarks</span></span>  
 <span data-ttu-id="63f41-112">Если `methodname` это метод экземпляра, он не может быть квалифицирован.</span><span class="sxs-lookup"><span data-stu-id="63f41-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="63f41-113">Поддержку используются статические методы в качестве фабричных методов.</span><span class="sxs-lookup"><span data-stu-id="63f41-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="63f41-114">Если `methodname` это статический `methodname` метод, `typeName.methodName` предоставляется `typeName` как комбинация, где называется класс, определяющий метод статической фабрики.</span><span class="sxs-lookup"><span data-stu-id="63f41-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="63f41-115">`typeName`может быть приставка-квалифицированных, если речь идет о типе в отображеном xmlns.</span><span class="sxs-lookup"><span data-stu-id="63f41-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="63f41-116">`typeName`может быть другого `typeof(object)`типа, чем .</span><span class="sxs-lookup"><span data-stu-id="63f41-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="63f41-117">Метод завода должен быть заявленным общедоступным методом типа, который поддерживает соответствующий элемент объекта.</span><span class="sxs-lookup"><span data-stu-id="63f41-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="63f41-118">Метод фабрики должен вернуть экземпляр, присвоенный соответствующему объекту.</span><span class="sxs-lookup"><span data-stu-id="63f41-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="63f41-119">Заводские методы никогда не должны возвращатьнули.</span><span class="sxs-lookup"><span data-stu-id="63f41-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="63f41-120">`x:Arguments`работает по принципу лучшего соответствия для подписи заводских методов.</span><span class="sxs-lookup"><span data-stu-id="63f41-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="63f41-121">Соответствие оценивает количество параметров в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="63f41-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="63f41-122">Если существует более одного возможного совпадения для подсчета параметров, тип параметра затем оценивается и определяется лучший матч.</span><span class="sxs-lookup"><span data-stu-id="63f41-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="63f41-123">Если после этого этапа оценки все еще существует двусмысленность, поведение процессора XAML не определено.</span><span class="sxs-lookup"><span data-stu-id="63f41-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="63f41-124">Использование `x:FactoryMethod` элемента не является использованием элемента свойства в типичном смысле, поскольку разметка директивы не ссылается на тип элемента, содержащего объект.</span><span class="sxs-lookup"><span data-stu-id="63f41-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="63f41-125">Ожидается, что использование элементов встречается реже, чем использование атрибутов.</span><span class="sxs-lookup"><span data-stu-id="63f41-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="63f41-126">`x:Arguments`(или атрибут или использование элемента) `x:FactoryMethod` могут быть использованы вместе с использованием элементов, но это не конкретно показано в разделах использования.</span><span class="sxs-lookup"><span data-stu-id="63f41-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="63f41-127">`x:FactoryMethod`как элемент должен предшествовать любым другим элементам `x:Arguments` свойства, должен предшествовать любому также представленному в качестве элементов, и должен предшествовать любому содержанию/внутреннему тексту/тексту инициализации.</span><span class="sxs-lookup"><span data-stu-id="63f41-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f41-128">См. также</span><span class="sxs-lookup"><span data-stu-id="63f41-128">See also</span></span>

- [<span data-ttu-id="63f41-129">Директива x:Arguments</span><span class="sxs-lookup"><span data-stu-id="63f41-129">x:Arguments Directive</span></span>](xarguments-directive.md)
