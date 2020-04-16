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
# <a name="xmlspace-handling-in-xaml"></a>Обработка xml:space в языке XAML

Атрибут `xml:space` — это XML-определенный атрибут, который декларирует значительное поведение обработки белого пространства в элементе объекта. Это поведение актуально для всего содержимого (внутреннего `xml:space` текста), содержащегося в элементе, где декларируется, а также для областей для элементов ребенка.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object xml:space="preserve" />
```

 \- или -

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>Примечания

Определение атрибута `xml:space` в XAML, включая два возможных `xml:space` значения, вытекает из такого определения как "специальный атрибут" спецификаций W3C для XML.

Значение атрибута `xml:space` по умолчанию является `"default"`буквальным значением. Для значения, `"default"`или `xml:space` если это не указано на всех, поведение значительного белого пространства разбора по умолчанию обработки, как это определено в теме [Белого пространства обработки в XAML](white-space-processing.md).

Чтобы сохранить белое пространство в `xml:space="preserve"` содержимом элемента объекта, укажите на этом элементе объекта.

При большинстве интерпретаций эффекты `xml:space` атрибута и значение атрибута относятся к элементам-ребезам.

Для полного обсуждения обработки белого пространства в XAML [см.](white-space-processing.md)

## <a name="see-also"></a>См. также

- [Обработка пробелов в XAML](white-space-processing.md)
- [Обзор XAML (WPF)](../fundamentals/xaml.md)
