---
title: Ожидается инициализатор
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 13fa8917f228661fc44f5e0920d91c596e250c38
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402841"
---
# <a name="initializer-expected"></a><span data-ttu-id="86de3-102">Ожидается инициализатор</span><span class="sxs-lookup"><span data-stu-id="86de3-102">Initializer expected</span></span>
<span data-ttu-id="86de3-103">Предпринята попытка объявить экземпляр класса с помощью инициализатора объекта, в котором список инициализации пуст, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="86de3-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="86de3-104">В списке инициализаторов должно быть инициализировано по крайней мере одно поле или свойство, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="86de3-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="86de3-105">**Идентификатор ошибки:** BC30996</span><span class="sxs-lookup"><span data-stu-id="86de3-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86de3-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="86de3-106">To correct this error</span></span>  
  
1. <span data-ttu-id="86de3-107">Инициализируйте по крайней мере одно поле или свойство в инициализаторе или не используйте инициализатор объекта.</span><span class="sxs-lookup"><span data-stu-id="86de3-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86de3-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="86de3-108">See also</span></span>

- [<span data-ttu-id="86de3-109">Инициализаторы объектов: именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="86de3-109">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="86de3-110">Практическое руководство. Объявление объекта с помощью инициализатора объектов</span><span class="sxs-lookup"><span data-stu-id="86de3-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
