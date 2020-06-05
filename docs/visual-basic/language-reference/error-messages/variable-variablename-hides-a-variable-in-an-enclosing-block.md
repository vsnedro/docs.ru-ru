---
title: Переменная <variablename> скрывает содержащуюся в блоке переменную
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 474a920c9cfdfba7a8157320d9c88b8677958425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406525"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="96193-102">Переменная \<variablename> скрывает содержащуюся в блоке переменную</span><span class="sxs-lookup"><span data-stu-id="96193-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="96193-103">Переменная, заключенная в блок, имеет то же имя, что и другая локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="96193-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="96193-104">**Идентификатор ошибки:** BC30616</span><span class="sxs-lookup"><span data-stu-id="96193-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96193-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="96193-105">To correct this error</span></span>  
  
- <span data-ttu-id="96193-106">Переименуйте переменную во вложенном блоке так, чтобы она не совпадала с другими локальными переменными.</span><span class="sxs-lookup"><span data-stu-id="96193-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="96193-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="96193-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="96193-108">Распространенной причиной этой ошибки является использование `Catch e As Exception` внутри обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="96193-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="96193-109">Если это так, назовите `Catch` переменную блока, `ex` а не `e` .</span><span class="sxs-lookup"><span data-stu-id="96193-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="96193-110">Другой распространенный источник этой ошибки — попытка доступа к локальной переменной, объявленной в `Try` блоке, в отдельном `Catch` блоке.</span><span class="sxs-lookup"><span data-stu-id="96193-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="96193-111">Чтобы исправить это, объявите переменную вне `Try...Catch...Finally` структуры.</span><span class="sxs-lookup"><span data-stu-id="96193-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96193-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="96193-112">See also</span></span>

- [<span data-ttu-id="96193-113">Оператор Try…Catch…Finally</span><span class="sxs-lookup"><span data-stu-id="96193-113">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="96193-114">Объявление переменной</span><span class="sxs-lookup"><span data-stu-id="96193-114">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
