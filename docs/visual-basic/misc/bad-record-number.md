---
title: Неверный номер записи
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 8cbffc7714211fb10bedc3a73729eac59d98f0bb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086989"
---
# <a name="bad-record-number"></a><span data-ttu-id="18457-102">Неверный номер записи</span><span class="sxs-lookup"><span data-stu-id="18457-102">Bad record number</span></span>

<span data-ttu-id="18457-103">Номер записи в операторе `a FileGet`, `FilePut`, `FileGetObject`или `FilePutObject` меньше или равен нулю.</span><span class="sxs-lookup"><span data-stu-id="18457-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="18457-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="18457-104">To correct this error</span></span>  
  
1. <span data-ttu-id="18457-105">Проверьте вычисления, используемые при формировании номера записи.</span><span class="sxs-lookup"><span data-stu-id="18457-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="18457-106">Проверьте правильность написания переменных, содержащих номер записи или используемых при вычислении номеров записей.</span><span class="sxs-lookup"><span data-stu-id="18457-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="18457-107">Неправильно написанное имя переменной неявно объявляется и приравнивается к нулю, если вы не использовали `Option Explicit On` в модуле.</span><span class="sxs-lookup"><span data-stu-id="18457-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18457-108">См. также</span><span class="sxs-lookup"><span data-stu-id="18457-108">See also</span></span>

- [<span data-ttu-id="18457-109">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="18457-109">Option Explicit Statement</span></span>](../language-reference/statements/option-explicit-statement.md)
