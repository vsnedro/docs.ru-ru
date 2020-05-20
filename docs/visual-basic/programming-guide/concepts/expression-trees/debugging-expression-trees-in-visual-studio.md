---
title: Отладка деревьев выражений в Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 287f3096a1af8b9fa42d252c5240d7caefa6bac8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616906"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="52829-102">Отладка деревьев выражений в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52829-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="52829-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="52829-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="52829-104">Чтобы получить краткий обзор структуры дерева выражения, вы можете использовать свойство `DebugView`, которое представляет деревья выражений, [используя специальный синтаксис](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="52829-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="52829-105">(Обратите внимание, что `DebugView` доступен только в режиме отладки.)</span><span class="sxs-lookup"><span data-stu-id="52829-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Снимок экрана DebugView дерева выражения.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

<span data-ttu-id="52829-107">Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="52829-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Снимок экрана: визуализатор текста, примененный к результатам DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

<span data-ttu-id="52829-109">Или вы можете установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, например:</span><span class="sxs-lookup"><span data-stu-id="52829-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="52829-110">[Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) отображают дерево выражения в виде кода C# с темой и различными вариантами отрисовки:</span><span class="sxs-lookup"><span data-stu-id="52829-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as themeable C# code, with various rendering options:</span></span>

  ![Снимок экрана: визуализатор доступных для чтения выражений](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="52829-112">[Визуализатор дерева выражений](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([Лицензия MIT](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) предоставляет древовидное представление дерева выражения и его отдельных узлов. и могут визуализировать дерево выражения с помощью синтаксиса Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="52829-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT license](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) provides a tree view of the expression tree and its individual nodes; and can render the expression tree using Visual Basic syntax:</span></span>

  ![Снимок экрана: визуализатор дерева выражений](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="52829-114">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="52829-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="52829-115">Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="52829-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
    <span data-ttu-id="52829-116">Отображается список доступных визуализаторов:</span><span class="sxs-lookup"><span data-stu-id="52829-116">A list of available visualizers is displayed.:</span></span>

    ![Снимок экрана пользователя, открывающего визуализаторы из Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. <span data-ttu-id="52829-118">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="52829-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="52829-119">См. также</span><span class="sxs-lookup"><span data-stu-id="52829-119">See also</span></span>

- <span data-ttu-id="52829-120">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="52829-120">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
- [<span data-ttu-id="52829-121">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52829-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="52829-122">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="52829-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="52829-123">Синтаксис `DebugView`</span><span class="sxs-lookup"><span data-stu-id="52829-123">`DebugView` syntax</span></span>](debugview-syntax.md)
