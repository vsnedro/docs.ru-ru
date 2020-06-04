---
title: Ожидается Optional
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 411e3248409ab0184666f4efefb4ec4becf7cab1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409352"
---
# <a name="optional-expected"></a><span data-ttu-id="2cbf0-102">Ожидается Optional</span><span class="sxs-lookup"><span data-stu-id="2cbf0-102">'Optional' expected</span></span>
<span data-ttu-id="2cbf0-103">За дополнительным аргументом в объявлении процедуры следует обязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="2cbf0-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="2cbf0-104">Каждый аргумент, следующий за необязательным аргументом, также должен быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="2cbf0-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="2cbf0-105">**Идентификатор ошибки:** BC30202</span><span class="sxs-lookup"><span data-stu-id="2cbf0-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2cbf0-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2cbf0-106">To correct this error</span></span>  
  
1. <span data-ttu-id="2cbf0-107">Если аргумент должен быть обязательным, переместите его перед первым необязательным аргументом в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="2cbf0-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="2cbf0-108">Если аргумент должен быть необязательным, используйте `Optional` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="2cbf0-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbf0-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2cbf0-109">See also</span></span>

- [<span data-ttu-id="2cbf0-110">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="2cbf0-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
