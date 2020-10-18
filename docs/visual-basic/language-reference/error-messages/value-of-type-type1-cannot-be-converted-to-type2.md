---
title: Невозможно преобразовать значение типа  в
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 107936aa969690d0cc9fd4a2605cfceea31eeca8
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161417"
---
# <a name="bc31194-value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="83039-102">BC31194: значение типа "тип1" не может быть преобразовано в "тип2"</span><span class="sxs-lookup"><span data-stu-id="83039-102">BC31194: Value of type 'type1' cannot be converted to 'type2'</span></span>

<span data-ttu-id="83039-103">Значение типа "тип1" не может быть преобразовано в "тип2".</span><span class="sxs-lookup"><span data-stu-id="83039-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="83039-104">Свойство "value" можно использовать для получения строкового значения первого элемента " \<parentElement> ".</span><span class="sxs-lookup"><span data-stu-id="83039-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>

 <span data-ttu-id="83039-105">Предпринята попытка неявного приведения XML-литерала к определенному типу.</span><span class="sxs-lookup"><span data-stu-id="83039-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="83039-106">XML-литерал не может быть неявно приведен к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="83039-106">The XML literal cannot be implicitly cast to the specified type.</span></span>

 <span data-ttu-id="83039-107">**Идентификатор ошибки:** BC31194</span><span class="sxs-lookup"><span data-stu-id="83039-107">**Error ID:** BC31194</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="83039-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="83039-108">To correct this error</span></span>

- <span data-ttu-id="83039-109">Используйте свойство `Value` XML-литерала для ссылки на его значение как на `String`.</span><span class="sxs-lookup"><span data-stu-id="83039-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="83039-110">Используйте функцию `CType` , другую функцию преобразования типа или класс <xref:System.Convert> для приведения значения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="83039-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>

## <a name="see-also"></a><span data-ttu-id="83039-111">См. также</span><span class="sxs-lookup"><span data-stu-id="83039-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="83039-112">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="83039-112">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="83039-113">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="83039-113">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="83039-114">XML</span><span class="sxs-lookup"><span data-stu-id="83039-114">XML</span></span>](../../programming-guide/language-features/xml/index.md)
