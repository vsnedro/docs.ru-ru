---
title: Переменная <variablename> скрывает содержащуюся в блоке переменную
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 408acaafd5e266266b5191313611b94b72a5c270
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161352"
---
# <a name="bc30616-variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="d03e3-102">BC30616: переменная " \<variablename> " скрывает переменную во внешнем блоке</span><span class="sxs-lookup"><span data-stu-id="d03e3-102">BC30616: Variable '\<variablename>' hides a variable in an enclosing block</span></span>

<span data-ttu-id="d03e3-103">Переменная, заключенная в блок, имеет то же имя, что и другая локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="d03e3-103">A variable enclosed in a block has the same name as another local variable.</span></span>

 <span data-ttu-id="d03e3-104">**Идентификатор ошибки:** BC30616</span><span class="sxs-lookup"><span data-stu-id="d03e3-104">**Error ID:** BC30616</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d03e3-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d03e3-105">To correct this error</span></span>

- <span data-ttu-id="d03e3-106">Переименуйте переменную во вложенном блоке так, чтобы она не совпадала с другими локальными переменными.</span><span class="sxs-lookup"><span data-stu-id="d03e3-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="d03e3-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="d03e3-107">For example:</span></span>

    ```vb
    Dim a, b, x As Integer
    If a = b Then
       Dim y As Integer = 20 ' Uniquely named block variable.
    End If
    ```

- <span data-ttu-id="d03e3-108">Распространенной причиной этой ошибки является использование `Catch e As Exception` внутри обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="d03e3-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="d03e3-109">Если это так, назовите `Catch` переменную блока, `ex` а не `e` .</span><span class="sxs-lookup"><span data-stu-id="d03e3-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>

- <span data-ttu-id="d03e3-110">Другой распространенный источник этой ошибки — попытка доступа к локальной переменной, объявленной в `Try` блоке, в отдельном `Catch` блоке.</span><span class="sxs-lookup"><span data-stu-id="d03e3-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="d03e3-111">Чтобы исправить это, объявите переменную вне `Try...Catch...Finally` структуры.</span><span class="sxs-lookup"><span data-stu-id="d03e3-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="d03e3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d03e3-112">See also</span></span>

- [<span data-ttu-id="d03e3-113">Оператор Try…Catch…Finally</span><span class="sxs-lookup"><span data-stu-id="d03e3-113">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="d03e3-114">Объявление переменной</span><span class="sxs-lookup"><span data-stu-id="d03e3-114">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
