---
title: 'Невозможно завершить операцию: конечный каталог находится внутри исходного'
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 46ec7ae452d4f8259d0f8ca3a896d1b29151ed61
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376746"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="e9f0c-102">Невозможно завершить операцию: конечный каталог находится внутри исходного</span><span class="sxs-lookup"><span data-stu-id="e9f0c-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="e9f0c-103">Циклическая операция не удалась.</span><span class="sxs-lookup"><span data-stu-id="e9f0c-103">A cyclic operation has failed.</span></span> <span data-ttu-id="e9f0c-104">Циклические операции являются бесконечными циклами и поэтому не могут завершиться.</span><span class="sxs-lookup"><span data-stu-id="e9f0c-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="e9f0c-105">Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.</span><span class="sxs-lookup"><span data-stu-id="e9f0c-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9f0c-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e9f0c-106">To correct this error</span></span>  
  
- <span data-ttu-id="e9f0c-107">При наследовании убедитесь в отсутствии циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="e9f0c-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f0c-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e9f0c-108">See also</span></span>

- [<span data-ttu-id="e9f0c-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="e9f0c-109">Error Types</span></span>](../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="e9f0c-110">Использование точек останова в отладчике Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e9f0c-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
