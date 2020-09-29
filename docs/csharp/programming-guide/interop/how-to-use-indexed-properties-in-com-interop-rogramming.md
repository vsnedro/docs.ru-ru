---
title: Руководство по программированию на C#. Использование индексированных свойств в программировании COM-взаимодействия
description: Сведения о том, как индексированные свойства оптимизируют использование свойств COM с параметрами при программировании на C#.
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 5f239a0772f734391bd68ef6618ea8ece8e8c9cd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178493"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="fb229-103">Руководство по программированию на C#. Использование индексированных свойств в программировании COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fb229-103">How to use indexed properties in COM interop programming (C# Programming Guide)</span></span>

<span data-ttu-id="fb229-104">*Индексированные свойства* делают использование свойств COM с параметрами при программировании на C# более удобным.</span><span class="sxs-lookup"><span data-stu-id="fb229-104">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="fb229-105">Индексированные свойства используются совместно с другими компонентами, представленными в Visual C#, например [именованными и необязательными аргументами](../classes-and-structs/named-and-optional-arguments.md), новым типом ([dynamic](../../language-reference/builtin-types/reference-types.md)) и [внедренными сведениями о типах](../../../standard/assembly/embed-types-visual-studio.md) для расширения возможностей программирования для Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="fb229-105">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="fb229-106">В более ранних версиях C# методы доступны как свойства только при условии, что у метода `get` нет параметров, а у метода `set` есть только один параметр значения.</span><span class="sxs-lookup"><span data-stu-id="fb229-106">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="fb229-107">Однако не все свойства COM удовлетворяют этим ограничениям.</span><span class="sxs-lookup"><span data-stu-id="fb229-107">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="fb229-108">Например, свойство <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> Excel имеет метод доступа `get`, которому требуется параметр для имени диапазона.</span><span class="sxs-lookup"><span data-stu-id="fb229-108">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="fb229-109">Раньше из-за отсутствия возможности прямого обращения к свойству `Range` приходилось использовать вместо этого метод `get_Range`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fb229-109">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="fb229-110">Индексированные свойства позволяют вместо этого использовать следующий код:</span><span class="sxs-lookup"><span data-stu-id="fb229-110">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="fb229-111">В предыдущем примере также используются [необязательные аргументы](../classes-and-structs/named-and-optional-arguments.md), которые позволяют опустить `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="fb229-111">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="fb229-112">Аналогичным образом, чтобы задать значение свойства `Value` объекта <xref:Microsoft.Office.Interop.Excel.Range> в C# 3.0 и более ранних версиях, требуются два аргумента.</span><span class="sxs-lookup"><span data-stu-id="fb229-112">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="fb229-113">Один предоставляет аргумент для необязательного параметра, указывающего тип значения диапазона.</span><span class="sxs-lookup"><span data-stu-id="fb229-113">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="fb229-114">Другой предоставляет значение для свойства `Value`.</span><span class="sxs-lookup"><span data-stu-id="fb229-114">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="fb229-115">Эти методы показаны в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="fb229-115">The following examples illustrate these techniques.</span></span> <span data-ttu-id="fb229-116">В примерах ячейке A1 задается значение `Name`.</span><span class="sxs-lookup"><span data-stu-id="fb229-116">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="fb229-117">Индексированные свойства позволяют вместо этого использовать следующий код.</span><span class="sxs-lookup"><span data-stu-id="fb229-117">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="fb229-118">Разработчики не могут создавать собственные индексированные свойства.</span><span class="sxs-lookup"><span data-stu-id="fb229-118">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="fb229-119">Эта возможность поддерживает только использование имеющихся индексированных свойств.</span><span class="sxs-lookup"><span data-stu-id="fb229-119">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb229-120">Пример</span><span class="sxs-lookup"><span data-stu-id="fb229-120">Example</span></span>  

 <span data-ttu-id="fb229-121">Ниже приведен полный пример кода.</span><span class="sxs-lookup"><span data-stu-id="fb229-121">The following code shows a complete example.</span></span> <span data-ttu-id="fb229-122">См. сведения о создании проекта, обращающегося к Office API, в руководстве по [получению доступа к объектам взаимодействия Office с помощью функций C#](./how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="fb229-122">For more information about how to set up a project that accesses the Office API, see [How to access Office interop objects by using C# features](./how-to-access-office-onterop-objects.md).</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="fb229-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fb229-123">See also</span></span>

- [<span data-ttu-id="fb229-124">Именованные и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="fb229-124">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="fb229-125">dynamic</span><span class="sxs-lookup"><span data-stu-id="fb229-125">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="fb229-126">Использование типа dynamic</span><span class="sxs-lookup"><span data-stu-id="fb229-126">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="fb229-127">Использование именованных и необязательных аргументов в программировании приложений Office</span><span class="sxs-lookup"><span data-stu-id="fb229-127">How to use named and optional arguments in Office programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="fb229-128">Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка C#</span><span class="sxs-lookup"><span data-stu-id="fb229-128">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="fb229-129">Пошаговое руководство: Программирование для Office</span><span class="sxs-lookup"><span data-stu-id="fb229-129">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
