---
title: Ожидается Optional
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: e212939cf814a9ac632571b2203f2f256dea61ae
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873597"
---
# <a name="optional-expected"></a><span data-ttu-id="fc1ac-102">Ожидается Optional</span><span class="sxs-lookup"><span data-stu-id="fc1ac-102">'Optional' expected</span></span>

<span data-ttu-id="fc1ac-103">За дополнительным аргументом в объявлении процедуры следует обязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="fc1ac-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="fc1ac-104">Каждый аргумент, следующий за необязательным аргументом, также должен быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="fc1ac-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="fc1ac-105">**Идентификатор ошибки:** BC30202</span><span class="sxs-lookup"><span data-stu-id="fc1ac-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fc1ac-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fc1ac-106">To correct this error</span></span>  
  
1. <span data-ttu-id="fc1ac-107">Если аргумент должен быть обязательным, переместите его перед первым необязательным аргументом в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="fc1ac-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="fc1ac-108">Если аргумент должен быть необязательным, используйте `Optional` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="fc1ac-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1ac-109">См. также</span><span class="sxs-lookup"><span data-stu-id="fc1ac-109">See also</span></span>

- [<span data-ttu-id="fc1ac-110">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="fc1ac-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
