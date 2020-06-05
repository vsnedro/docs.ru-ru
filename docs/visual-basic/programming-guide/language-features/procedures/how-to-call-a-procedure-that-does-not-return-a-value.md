---
title: Практическое руководство. Вызов процедуры, которая не возвращает значение
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 514d6e576b9b782387840ae04dcefa00de876aa9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388742"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="32ab3-102">Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32ab3-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="32ab3-103">`Sub`Процедура не возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="32ab3-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="32ab3-104">Он вызывается явным образом с помощью изолированного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="32ab3-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="32ab3-105">Его нельзя вызвать, просто используя его имя в выражении.</span><span class="sxs-lookup"><span data-stu-id="32ab3-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="32ab3-106">Вызов процедуры подпрограммы</span><span class="sxs-lookup"><span data-stu-id="32ab3-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="32ab3-107">Укажите имя `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="32ab3-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="32ab3-108">Чтобы заключить список аргументов, выполните имя процедуры с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="32ab3-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="32ab3-109">Если аргументы отсутствуют, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="32ab3-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="32ab3-110">Однако использование круглых скобок упрощает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="32ab3-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="32ab3-111">Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="32ab3-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="32ab3-112">Убедитесь, что аргументы указываются в том же порядке, в котором `Sub` процедура определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="32ab3-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="32ab3-113">В следующем примере вызывается <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> функция Visual Basic для активации окна приложения.</span><span class="sxs-lookup"><span data-stu-id="32ab3-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="32ab3-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>принимает заголовок окна в качестве единственного аргумента.</span><span class="sxs-lookup"><span data-stu-id="32ab3-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="32ab3-115">Он не возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="32ab3-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="32ab3-116">Если процесс «Блокнот» не выполняется, в примере создается исключение <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="32ab3-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="32ab3-117">`Shell`Процедура предполагает, что приложения находятся в указанных путях.</span><span class="sxs-lookup"><span data-stu-id="32ab3-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="32ab3-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="32ab3-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="32ab3-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="32ab3-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="32ab3-120">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="32ab3-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="32ab3-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="32ab3-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="32ab3-122">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="32ab3-122">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="32ab3-123">Практическое руководство. Создание процедуры</span><span class="sxs-lookup"><span data-stu-id="32ab3-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="32ab3-124">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="32ab3-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="32ab3-125">Практическое руководство. Вызов обработчика событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32ab3-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
