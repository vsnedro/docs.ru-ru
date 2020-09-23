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
ms.openlocfilehash: 64d21fe4aaf6fd34bf880373a7ab3067fb67820e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077063"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="9824b-102">Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9824b-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>

<span data-ttu-id="9824b-103">*Текущим экземпляром* объекта является экземпляр, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="9824b-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="9824b-104">Используйте `Me` ключевое слово для ссылки на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="9824b-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="9824b-105">Ссылка на текущий экземпляр</span><span class="sxs-lookup"><span data-stu-id="9824b-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="9824b-106">Используйте `Me` ключевое слово, в котором обычно используется имя объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="9824b-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="9824b-107">Несмотря `Me` на то, что ведет себя как объектная переменная, вы не можете объявить ее или присвоить ей что-либо.</span><span class="sxs-lookup"><span data-stu-id="9824b-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="9824b-108">`Me` всегда ссылается на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="9824b-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9824b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="9824b-109">See also</span></span>

- [<span data-ttu-id="9824b-110">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="9824b-110">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="9824b-111">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="9824b-111">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="9824b-112">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="9824b-112">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
