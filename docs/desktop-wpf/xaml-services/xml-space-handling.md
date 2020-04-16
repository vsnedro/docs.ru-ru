---
title: Обработка xml:space в языке XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432704"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="b2ad4-102">Обработка xml:space в языке XAML</span><span class="sxs-lookup"><span data-stu-id="b2ad4-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="b2ad4-103">Атрибут `xml:space` — это XML-определенный атрибут, который декларирует значительное поведение обработки белого пространства в элементе объекта.</span><span class="sxs-lookup"><span data-stu-id="b2ad4-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="b2ad4-104">Это поведение актуально для всего содержимого (внутреннего `xml:space` текста), содержащегося в элементе, где декларируется, а также для областей для элементов ребенка.</span><span class="sxs-lookup"><span data-stu-id="b2ad4-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="b2ad4-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="b2ad4-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="b2ad4-106">\- или -</span><span class="sxs-lookup"><span data-stu-id="b2ad4-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="b2ad4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2ad4-107">Remarks</span></span>

<span data-ttu-id="b2ad4-108">Определение атрибута `xml:space` в XAML, включая два возможных `xml:space` значения, вытекает из такого определения как "специальный атрибут" спецификаций W3C для XML.</span><span class="sxs-lookup"><span data-stu-id="b2ad4-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="b2ad4-109">Значение атрибута `xml:space` по умолчанию является `"default"`буквальным значением.</span><span class="sxs-lookup"><span data-stu-id="b2ad4-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="b2ad4-110">Для значения, `"default"`или `xml:space` если это не указано на всех, поведение значительного белого пространства разбора по умолчанию обработки, как это определено в теме [Белого пространства обработки в XAML](white-space-processing.md).</span><span class="sxs-lookup"><span data-stu-id="b2ad4-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="b2ad4-111">Чтобы сохранить белое пространство в `xml:space="preserve"` содержимом элемента объекта, укажите на этом элементе объекта.</span><span class="sxs-lookup"><span data-stu-id="b2ad4-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="b2ad4-112">При большинстве интерпретаций эффекты `xml:space` атрибута и значение атрибута относятся к элементам-ребезам.</span><span class="sxs-lookup"><span data-stu-id="b2ad4-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="b2ad4-113">Для полного обсуждения обработки белого пространства в XAML [см.](white-space-processing.md)</span><span class="sxs-lookup"><span data-stu-id="b2ad4-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b2ad4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b2ad4-114">See also</span></span>

- [<span data-ttu-id="b2ad4-115">Обработка пробелов в XAML</span><span class="sxs-lookup"><span data-stu-id="b2ad4-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="b2ad4-116">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="b2ad4-116">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
