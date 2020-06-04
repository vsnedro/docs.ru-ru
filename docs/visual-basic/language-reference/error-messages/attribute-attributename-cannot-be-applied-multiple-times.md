---
title: Атрибут <attributename> не может применяться многократно
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 14145f165adf5ccd20298a70ca5596488b488b0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409963"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="88903-102">Атрибут \<attributename> не может применяться многократно</span><span class="sxs-lookup"><span data-stu-id="88903-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="88903-103">Атрибут можно применить только один раз.</span><span class="sxs-lookup"><span data-stu-id="88903-103">The attribute can only be applied once.</span></span> <span data-ttu-id="88903-104">`AttributeUsage`Атрибут определяет, можно ли применить атрибут более одного раза.</span><span class="sxs-lookup"><span data-stu-id="88903-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="88903-105">**Идентификатор ошибки:** BC30663</span><span class="sxs-lookup"><span data-stu-id="88903-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88903-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="88903-106">To correct this error</span></span>  
  
1. <span data-ttu-id="88903-107">Убедитесь, что атрибут применяется только один раз.</span><span class="sxs-lookup"><span data-stu-id="88903-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="88903-108">Если вы используете созданные вами настраиваемые атрибуты, попробуйте изменить их `AttributeUsage` атрибут, чтобы разрешить использование нескольких атрибутов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="88903-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88903-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="88903-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="88903-110">Создание настраиваемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="88903-110">Creating Custom Attributes</span></span>](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="88903-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="88903-111">AttributeUsage</span></span>](../../programming-guide/concepts/attributes/attributeusage.md)
