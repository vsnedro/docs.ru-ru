---
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 52e5391fbcf30a4dada4d64a0e810c900ea85806
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409391"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="54303-102">Выведение типа Nullable не поддерживается в данном контексте</span><span class="sxs-lookup"><span data-stu-id="54303-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="54303-103">Типы значений и структуры могут быть объявлены как допускающие значение null.</span><span class="sxs-lookup"><span data-stu-id="54303-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="54303-104">Однако нельзя использовать объявление Nullable в сочетании с выводом типа.</span><span class="sxs-lookup"><span data-stu-id="54303-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="54303-105">Следующие примеры вызывают эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="54303-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="54303-106">**Идентификатор ошибки:** BC36629</span><span class="sxs-lookup"><span data-stu-id="54303-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54303-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="54303-107">To correct this error</span></span>  
  
- <span data-ttu-id="54303-108">Используйте `As` предложение, чтобы объявить переменную как тип значения, допускающего значение null.</span><span class="sxs-lookup"><span data-stu-id="54303-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54303-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="54303-109">See also</span></span>

- [<span data-ttu-id="54303-110">Типы значений, допускающие значение null</span><span class="sxs-lookup"><span data-stu-id="54303-110">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="54303-111">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="54303-111">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
