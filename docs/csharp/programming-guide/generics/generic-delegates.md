---
title: Руководство по программированию на C#. Универсальные методы-делегаты
description: Сведения об использовании универсальных методов-делегатов при программировании на C#. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: d99271ca9f12e95743d633caac16aaa4151e9c41
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301909"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="dcb96-104">Универсальные делегаты. (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="dcb96-104">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="dcb96-105">[Делегат](../../language-reference/builtin-types/reference-types.md) может определять собственные параметры типа.</span><span class="sxs-lookup"><span data-stu-id="dcb96-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can define its own type parameters.</span></span> <span data-ttu-id="dcb96-106">В коде, который ссылается на универсальный делегат, можно указать аргумент типа для создания закрытого сконструированного типа. Это будет аналогично созданию экземпляра универсального класса или вызову универсального метода, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="dcb96-106">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="dcb96-107">В C# версии 2.0 представлена новая функция группового преобразования методов, которая применяется как к конкретным, так и к универсальным типам делегатов, и позволяет записать приведенную выше строку с использованием упрощенного синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="dcb96-107">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="dcb96-108">Делегаты, определенные в универсальном классе, могут использовать параметры класса универсального типа таким же образом, как это делают методы класса.</span><span class="sxs-lookup"><span data-stu-id="dcb96-108">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="dcb96-109">В коде, который ссылается на делегат, необходимо указать аргумент типа содержащего класса, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="dcb96-109">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="dcb96-110">Универсальные делегаты особенно полезны при определении событий, основанных на типовых шаблонах разработки, поскольку аргумент отправителя может быть строго типизирован и больше не требует приведения к <xref:System.Object> и из него.</span><span class="sxs-lookup"><span data-stu-id="dcb96-110">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="dcb96-111">См. также</span><span class="sxs-lookup"><span data-stu-id="dcb96-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="dcb96-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dcb96-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="dcb96-113">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="dcb96-113">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="dcb96-114">Универсальные методы</span><span class="sxs-lookup"><span data-stu-id="dcb96-114">Generic Methods</span></span>](./generic-methods.md)
- [<span data-ttu-id="dcb96-115">Универсальные классы</span><span class="sxs-lookup"><span data-stu-id="dcb96-115">Generic Classes</span></span>](./generic-classes.md)
- [<span data-ttu-id="dcb96-116">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="dcb96-116">Generic Interfaces</span></span>](./generic-interfaces.md)
- [<span data-ttu-id="dcb96-117">Делегаты</span><span class="sxs-lookup"><span data-stu-id="dcb96-117">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="dcb96-118">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="dcb96-118">Generics</span></span>](../../../standard/generics/index.md)
