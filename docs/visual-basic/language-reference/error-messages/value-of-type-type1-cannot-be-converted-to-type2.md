---
title: Невозможно преобразовать значение типа  в
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8c80429db618e1bcadce1a58a6514d625f0b3cf1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870230"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="7a005-102">Невозможно преобразовать значение типа  в</span><span class="sxs-lookup"><span data-stu-id="7a005-102">Value of type 'type1' cannot be converted to 'type2'</span></span>

<span data-ttu-id="7a005-103">Значение типа "тип1" не может быть преобразовано в "тип2".</span><span class="sxs-lookup"><span data-stu-id="7a005-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="7a005-104">Свойство "value" можно использовать для получения строкового значения первого элемента " \<parentElement> ".</span><span class="sxs-lookup"><span data-stu-id="7a005-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="7a005-105">Предпринята попытка неявного приведения XML-литерала к определенному типу.</span><span class="sxs-lookup"><span data-stu-id="7a005-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="7a005-106">XML-литерал не может быть неявно приведен к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="7a005-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="7a005-107">**Идентификатор ошибки:** BC31194</span><span class="sxs-lookup"><span data-stu-id="7a005-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a005-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7a005-108">To correct this error</span></span>  
  
- <span data-ttu-id="7a005-109">Используйте свойство `Value` XML-литерала для ссылки на его значение как на `String`.</span><span class="sxs-lookup"><span data-stu-id="7a005-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="7a005-110">Используйте функцию `CType` , другую функцию преобразования типа или класс <xref:System.Convert> для приведения значения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="7a005-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a005-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7a005-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="7a005-112">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="7a005-112">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="7a005-113">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="7a005-113">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="7a005-114">XML</span><span class="sxs-lookup"><span data-stu-id="7a005-114">XML</span></span>](../../programming-guide/language-features/xml/index.md)
