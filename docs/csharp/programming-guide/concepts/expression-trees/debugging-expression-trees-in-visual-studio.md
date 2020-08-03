---
title: Отладка деревьев выражений в Visual Studio (C#)
description: Изучите свойство DebugView в Visual Studio. Узнайте, как использовать это свойство для анализа структуры и содержимого деревьев выражений.
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 5d62a5e6fa5ce537a1ea8b316e7322eb976200c0
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105649"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="07e2a-104">Отладка деревьев выражений в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="07e2a-104">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="07e2a-105">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="07e2a-105">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="07e2a-106">Чтобы получить краткий обзор структуры дерева выражения, вы можете использовать свойство `DebugView`, которое представляет деревья выражений, [используя специальный синтаксис](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="07e2a-106">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="07e2a-107">(Обратите внимание, что `DebugView` доступен только в режиме отладки.)</span><span class="sxs-lookup"><span data-stu-id="07e2a-107">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Снимок экрана: DebugView дерева выражений в отладчике VS](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

<span data-ttu-id="07e2a-109">Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="07e2a-109">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Снимок экрана: визуализатор текста, примененный к результатам DebugView](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

<span data-ttu-id="07e2a-111">Или вы можете установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, например:</span><span class="sxs-lookup"><span data-stu-id="07e2a-111">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="07e2a-112">[Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) отображают дерево выражения в виде кода C# с темой и различными вариантами отрисовки:</span><span class="sxs-lookup"><span data-stu-id="07e2a-112">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as themeable C# code, with various rendering options:</span></span>

  ![Снимок экрана: визуализатор доступных для чтения выражений](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="07e2a-114">[Визуализатор дерева выражения](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([лицензия MIT](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) — древовидное представление дерева выражения и его узлов:</span><span class="sxs-lookup"><span data-stu-id="07e2a-114">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT license](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) provides a tree view of the expression tree and its individual nodes:</span></span>

  ![Снимок экрана: визуализатор дерева выражений](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="07e2a-116">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="07e2a-116">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="07e2a-117">Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="07e2a-117">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  

    <span data-ttu-id="07e2a-118">Отображается список доступных визуализаторов:</span><span class="sxs-lookup"><span data-stu-id="07e2a-118">A list of available visualizers is displayed.:</span></span>

    ![Снимок экрана: открытие визуализаторов из Visual Studio](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. <span data-ttu-id="07e2a-120">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="07e2a-120">Click the visualizer you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e2a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="07e2a-121">See also</span></span>

- [<span data-ttu-id="07e2a-122">Деревья выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="07e2a-122">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="07e2a-123">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="07e2a-123">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="07e2a-124">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="07e2a-124">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="07e2a-125">Синтаксис `DebugView`</span><span class="sxs-lookup"><span data-stu-id="07e2a-125">`DebugView` syntax</span></span>](debugview-syntax.md)
