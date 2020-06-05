---
title: Оператор TypeOf
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 0cce36073b53442bce63f966f3bd94bd5d70d2a8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406331"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="e5341-102">Оператор TypeOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5341-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="e5341-103">Проверяет, совместим ли тип среды выполнения результата выражения с указанным типом.</span><span class="sxs-lookup"><span data-stu-id="e5341-103">Checks whether the runtime type of an expression's result is type-compatible with the specified type.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e5341-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5341-104">Syntax</span></span>  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="e5341-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="e5341-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e5341-106">Возвращено.</span><span class="sxs-lookup"><span data-stu-id="e5341-106">Returned.</span></span> <span data-ttu-id="e5341-107">Значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="e5341-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="e5341-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e5341-108">Required.</span></span> <span data-ttu-id="e5341-109">Любое выражение, результатом которого является тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="e5341-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="e5341-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e5341-110">Required.</span></span> <span data-ttu-id="e5341-111">Любое имя типа данных.</span><span class="sxs-lookup"><span data-stu-id="e5341-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5341-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e5341-112">Remarks</span></span>  
 <span data-ttu-id="e5341-113">Оператор `TypeOf` определяет, совместим ли тип времени выполнения `objectexpression` с `typename`.</span><span class="sxs-lookup"><span data-stu-id="e5341-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="e5341-114">Совместимость зависит от категории типа `typename`.</span><span class="sxs-lookup"><span data-stu-id="e5341-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="e5341-115">В следующей таблице показано, как определяется совместимость.</span><span class="sxs-lookup"><span data-stu-id="e5341-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="e5341-116">Категория типа `typename`</span><span class="sxs-lookup"><span data-stu-id="e5341-116">Type category of `typename`</span></span>|<span data-ttu-id="e5341-117">Критерий совместимости</span><span class="sxs-lookup"><span data-stu-id="e5341-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="e5341-118">Класс</span><span class="sxs-lookup"><span data-stu-id="e5341-118">Class</span></span>|<span data-ttu-id="e5341-119">`objectexpression` типа `typename` или наследует от `typename`</span><span class="sxs-lookup"><span data-stu-id="e5341-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="e5341-120">structure</span><span class="sxs-lookup"><span data-stu-id="e5341-120">Structure</span></span>|<span data-ttu-id="e5341-121">`objectexpression` типа `typename`</span><span class="sxs-lookup"><span data-stu-id="e5341-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="e5341-122">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="e5341-122">Interface</span></span>|<span data-ttu-id="e5341-123">`objectexpression` реализует `typename` или наследует от класса, реализующего `typename`</span><span class="sxs-lookup"><span data-stu-id="e5341-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="e5341-124">Если тип времени выполнения `objectexpression` удовлетворяет критерию совместимости, `result` является `True`.</span><span class="sxs-lookup"><span data-stu-id="e5341-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="e5341-125">В противном случае `result` является `False`.</span><span class="sxs-lookup"><span data-stu-id="e5341-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="e5341-126">Если `objectexpression` имеет значение null, то `TypeOf`...`Is` возвращает `False`, а ...`IsNot` возвращает `True`.</span><span class="sxs-lookup"><span data-stu-id="e5341-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="e5341-127">`TypeOf` всегда используется с ключевым словом `Is` для создания выражения `TypeOf`...`Is` или с ключевым словом `IsNot` для создания выражения `TypeOf`...`IsNot`.</span><span class="sxs-lookup"><span data-stu-id="e5341-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5341-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e5341-128">Example</span></span>  
 <span data-ttu-id="e5341-129">В следующем примере выражение `TypeOf`...`Is` используется для проверки на совместимость типов двух переменных ссылок на объекты с различными типами данных.</span><span class="sxs-lookup"><span data-stu-id="e5341-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="e5341-130">Переменная `refInteger` имеет тип времени выполнения `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e5341-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="e5341-131">Она совместима с `Integer`, но не с `Double`.</span><span class="sxs-lookup"><span data-stu-id="e5341-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="e5341-132">Переменная `refForm` имеет тип времени выполнения <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="e5341-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="e5341-133">Она совместима с <xref:System.Windows.Forms.Form>, так как это ее тип, с <xref:System.Windows.Forms.Control>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.Windows.Forms.Control>, и с <xref:System.ComponentModel.IComponent>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.ComponentModel.Component>, который реализует <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="e5341-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="e5341-134">Однако `refForm` несовместима с <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="e5341-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5341-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e5341-135">See also</span></span>

- [<span data-ttu-id="e5341-136">Оператор is</span><span class="sxs-lookup"><span data-stu-id="e5341-136">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="e5341-137">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="e5341-137">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="e5341-138">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5341-138">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="e5341-139">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5341-139">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="e5341-140">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="e5341-140">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="e5341-141">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="e5341-141">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
