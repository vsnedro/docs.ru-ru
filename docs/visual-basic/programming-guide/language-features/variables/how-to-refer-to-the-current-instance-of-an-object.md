---
title: Практическое руководство. Ссылка на текущий экземпляр объекта
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 43bfd54592fb1d26cbf7f268b7e098e01e3745d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410429"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="1d232-102">Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d232-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="1d232-103">*Текущим экземпляром* объекта является экземпляр, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="1d232-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="1d232-104">Используйте `Me` ключевое слово для ссылки на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1d232-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="1d232-105">Ссылка на текущий экземпляр</span><span class="sxs-lookup"><span data-stu-id="1d232-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="1d232-106">Используйте `Me` ключевое слово, в котором обычно используется имя объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="1d232-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="1d232-107">Несмотря `Me` на то, что ведет себя как объектная переменная, вы не можете объявить ее или присвоить ей что-либо.</span><span class="sxs-lookup"><span data-stu-id="1d232-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="1d232-108">`Me`всегда ссылается на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1d232-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d232-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1d232-109">See also</span></span>

- [<span data-ttu-id="1d232-110">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="1d232-110">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="1d232-111">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="1d232-111">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="1d232-112">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="1d232-112">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
