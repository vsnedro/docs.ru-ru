---
title: Отладка деревьев выражений в Visual Studio (C#)
description: Изучите свойство DebugView в Visual Studio. Узнайте, как использовать это свойство для анализа структуры и содержимого деревьев выражений.
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 5dcf56f96ecdbfdc3f4cb171fdb30b96456b59c9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91154136"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="1dbe1-104">Отладка деревьев выражений в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="1dbe1-104">Debugging Expression Trees in Visual Studio (C#)</span></span>

<span data-ttu-id="1dbe1-105">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="1dbe1-105">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="1dbe1-106">Чтобы получить краткий обзор структуры дерева выражения, вы можете использовать свойство `DebugView`, которое представляет деревья выражений, [используя специальный синтаксис](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="1dbe1-106">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="1dbe1-107">(Обратите внимание, что `DebugView` доступен только в режиме отладки.)</span><span class="sxs-lookup"><span data-stu-id="1dbe1-107">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Снимок экрана: DebugView дерева выражений в отладчике VS](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

<span data-ttu-id="1dbe1-109">Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="1dbe1-109">Since `DebugView` is a string, you can use the [built-in Text Visualizer](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Снимок экрана: визуализатор текста, примененный к результатам DebugView](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

<span data-ttu-id="1dbe1-111">Или вы можете установить и использовать [пользовательский визуализатор](/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, например:</span><span class="sxs-lookup"><span data-stu-id="1dbe1-111">Alternatively, you can install and use [a custom visualizer](/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="1dbe1-112">[Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) отображают дерево выражения в виде кода C# с темой и различными вариантами отрисовки:</span><span class="sxs-lookup"><span data-stu-id="1dbe1-112">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as themeable C# code, with various rendering options:</span></span>

  ![Снимок экрана: визуализатор доступных для чтения выражений](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="1dbe1-114">[Визуализатор дерева выражения](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([лицензия MIT](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) — древовидное представление дерева выражения и его узлов:</span><span class="sxs-lookup"><span data-stu-id="1dbe1-114">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT license](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) provides a tree view of the expression tree and its individual nodes:</span></span>

  ![Снимок экрана: визуализатор дерева выражений](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="1dbe1-116">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="1dbe1-116">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="1dbe1-117">Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="1dbe1-117">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  

    <span data-ttu-id="1dbe1-118">Отображается список доступных визуализаторов:</span><span class="sxs-lookup"><span data-stu-id="1dbe1-118">A list of available visualizers is displayed.:</span></span>

    ![Снимок экрана: открытие визуализаторов из Visual Studio](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. <span data-ttu-id="1dbe1-120">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="1dbe1-120">Click the visualizer you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dbe1-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1dbe1-121">See also</span></span>

- [<span data-ttu-id="1dbe1-122">Деревья выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="1dbe1-122">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="1dbe1-123">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1dbe1-123">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="1dbe1-124">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="1dbe1-124">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="1dbe1-125">Синтаксис `DebugView`</span><span class="sxs-lookup"><span data-stu-id="1dbe1-125">`DebugView` syntax</span></span>](debugview-syntax.md)
