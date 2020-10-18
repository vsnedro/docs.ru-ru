---
title: Для необязательных параметров должно быть задано значение по умолчанию
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 3718fe5c42c8af0948f3b5cb0d120c6876c6f98f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162457"
---
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="e1b29-102">BC30812: необязательные параметры должны указывать значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e1b29-102">BC30812: Optional parameters must specify a default value</span></span>

<span data-ttu-id="e1b29-103">Необязательные параметры должны предоставлять значения по умолчанию, которые можно использовать, если вызывающая процедура не предоставляет параметр.</span><span class="sxs-lookup"><span data-stu-id="e1b29-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="e1b29-104">**Идентификатор ошибки:** BC30812</span><span class="sxs-lookup"><span data-stu-id="e1b29-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="e1b29-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e1b29-105">Example</span></span>

<span data-ttu-id="e1b29-106">Следующий пример приводит к возникновению ошибки BC30812:</span><span class="sxs-lookup"><span data-stu-id="e1b29-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="e1b29-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e1b29-107">To correct this error</span></span>

<span data-ttu-id="e1b29-108">Укажите значения по умолчанию для необязательных параметров:</span><span class="sxs-lookup"><span data-stu-id="e1b29-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="e1b29-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e1b29-109">See also</span></span>

- [<span data-ttu-id="e1b29-110">Необязательно</span><span class="sxs-lookup"><span data-stu-id="e1b29-110">Optional</span></span>](../modifiers/optional.md)
