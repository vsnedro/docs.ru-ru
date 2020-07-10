---
title: Практическое руководство. Печать формы Windows Forms
description: Узнайте, как программно распечатать копию текущей формы Windows с помощью метода Копифромскрин.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: b59ea4b5347903b36a166c4f8ac0d8d7db18635e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174696"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="73391-103">Практическое руководство. Печать формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73391-103">How to: Print a Windows Form</span></span>
<span data-ttu-id="73391-104">Как часть процесса разработки, обычно требуется распечатать копию формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="73391-104">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="73391-105">В следующем примере кода показано, как напечатать копию текущей формы с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="73391-105">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73391-106">Пример</span><span class="sxs-lookup"><span data-stu-id="73391-106">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="73391-107">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="73391-107">Robust Programming</span></span>  
 <span data-ttu-id="73391-108">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="73391-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="73391-109">У вас нет разрешения на доступ к принтеру.</span><span class="sxs-lookup"><span data-stu-id="73391-109">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="73391-110">Принтер не установлен.</span><span class="sxs-lookup"><span data-stu-id="73391-110">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="73391-111">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="73391-111">.NET Framework Security</span></span>  
 <span data-ttu-id="73391-112">Чтобы запустить этот пример кода, необходимо иметь разрешение на доступ к принтеру, который используется на компьютере.</span><span class="sxs-lookup"><span data-stu-id="73391-112">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73391-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="73391-113">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="73391-114">Практическое руководство. Отрисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="73391-114">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="73391-115">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73391-115">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
