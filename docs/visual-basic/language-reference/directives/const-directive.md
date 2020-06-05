---
title: '#Директива Const'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 91152771a4ef5ec74a7408511ccc2afe28dd442e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415470"
---
# <a name="const-directive"></a><span data-ttu-id="3b767-102">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="3b767-102">#Const Directive</span></span>

<span data-ttu-id="3b767-103">Определяет константы условной компилятора для Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3b767-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b767-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b767-104">Syntax</span></span>  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3b767-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="3b767-105">Parts</span></span>  

 `constname`  
 <span data-ttu-id="3b767-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3b767-106">Required.</span></span> <span data-ttu-id="3b767-107">Имя определяемой константы.</span><span class="sxs-lookup"><span data-stu-id="3b767-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="3b767-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3b767-108">Required.</span></span> <span data-ttu-id="3b767-109">Literal, другая условная константа компилятора или любое сочетание, включающее любые или все арифметические или логические операторы, кроме `Is` .</span><span class="sxs-lookup"><span data-stu-id="3b767-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b767-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3b767-110">Remarks</span></span>  

 <span data-ttu-id="3b767-111">Константы условной компиляции всегда являются частными для файла, в котором они отображаются.</span><span class="sxs-lookup"><span data-stu-id="3b767-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="3b767-112">Нельзя создавать открытые константы компилятора с помощью `#Const` директивы. их можно создавать только в пользовательском интерфейсе или с помощью `/define` параметра компилятора.</span><span class="sxs-lookup"><span data-stu-id="3b767-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="3b767-113">В можно использовать только константы условной компиляции и литералы `expression` .</span><span class="sxs-lookup"><span data-stu-id="3b767-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="3b767-114">Использование стандартной константы, определенной с помощью, `Const` приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="3b767-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="3b767-115">И наоборот, константы, определенные с помощью `#Const` ключевого слова, можно использовать только для условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="3b767-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="3b767-116">Константы также могут быть неопределенными, в этом случае они имеют значение `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="3b767-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b767-117">Пример</span><span class="sxs-lookup"><span data-stu-id="3b767-117">Example</span></span>  

 <span data-ttu-id="3b767-118">В этом примере используется директива `#Const`.</span><span class="sxs-lookup"><span data-stu-id="3b767-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3b767-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3b767-119">See also</span></span>

- [<span data-ttu-id="3b767-120">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b767-120">-define (Visual Basic)</span></span>](../../reference/command-line-compiler/define.md)
- [<span data-ttu-id="3b767-121">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="3b767-121">#If...Then...#Else Directives</span></span>](if-then-else-directives.md)
- [<span data-ttu-id="3b767-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="3b767-122">Const Statement</span></span>](../statements/const-statement.md)
- [<span data-ttu-id="3b767-123">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="3b767-123">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="3b767-124">Оператор If…Then…Else</span><span class="sxs-lookup"><span data-stu-id="3b767-124">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
