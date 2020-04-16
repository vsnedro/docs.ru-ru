---
title: Директива x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: b5b480016d2183268422dea861510c6a169ac27b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432620"
---
# <a name="xuid-directive"></a>Директива x:Uid

Предоставляет уникальный идентификатор для элементов разметки. Во многих сценариях этот уникальный идентификатор используется процессами и инструментами локализации XAML.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`identifier`|Созданная вручную или аутогенерированная строка, которая должна `x:Uid` быть уникальной в файле, когда она интерпретируется потребителем.|

## <a name="remarks"></a>Примечания

В «MS-XAML» `x:Uid` определяется как директива. Для получения дополнительной информации [ \[см.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))

`x:Uid`дискретна как `x:Name` из-за заявленного сценария локализации XAML, так и так, что идентификаторы, которые используются для локализации, не зависят от последствий `x:Name`модели программирования . Кроме `x:Name` того, регулируется XAML namescope; однако, `x:Uid` не регулируется какой-либо XAML язык определяется понятие уникальности исполнения. Процессоры XAML в широком смысле (процессоры, которые не являются частью процесса локализации) не должны обеспечивать уникальность значений. `x:Uid` Эта ответственность концептуально лежит на создателе ценностей. Ожидание уникальности `x:Uid` ценностей в одном источнике XAML является разумным для потребителей ценностей, таких как специализированные процессы глобализации или инструменты. Типичная модель уникальности заключается в том, что `x:Uid` значения уникальны в xML-кодированном файле, представляющем XAML.

Инструменты, которые обладают значительными знаниями о конкретной схеме XAML, могут применяться `x:Uid` только для истинных локальных строк, а не для всех случаев, когда значение строки текста встречается в разметке.

Рамки могут указывать конкретное свойство в своей `x:Uid` модели объектов <xref:System.Windows.Markup.UidPropertyAttribute> как псевдоним, применяя атрибут к определяющему типу. Если в фреймрете указывается конкретное свойство, то не допустимо указывать как, `x:Uid` так и псевдонимированный член на одном объекте. Если `x:Uid` указаны оба и псевдоним-член, API службx XAML обычно бросает <xref:System.Xaml.XamlDuplicateMemberException> для этого случая.

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

Для получения дополнительной информации `x:Uid` о роли в процессе локализации WPF и в форме BAML XAML см. [Globalization for WPF](../../framework/wpf/advanced/globalization-for-wpf.md)<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>См. также

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Глобализация для WPF](../../framework/wpf/advanced/globalization-for-wpf.md)
