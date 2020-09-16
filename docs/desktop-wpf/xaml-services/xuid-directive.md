---
title: Директива x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 3de02702e6fd2be63bc2d099dad11f896b281ad1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543502"
---
# <a name="xuid-directive"></a>Директива x:Uid

Предоставляет уникальный идентификатор для элементов разметки. Во многих сценариях этот уникальный идентификатор используется процессами локализации XAML и инструментами.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`identifier`|Созданная вручную или автоматически сформированная строка, которая должна быть уникальной в файле, если она интерпретируется `x:Uid` потребителем.|

## <a name="remarks"></a>Примечания

В [MS-XAML] `x:Uid` определяется как директива. Дополнительные сведения см. в [ \[ \] разделе 5.3.6 в MS-XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

`x:Uid` является дискретным из из- `x:Name` за указанного сценария локализации XAML, поэтому идентификаторы, используемые для локализации, не имеют зависимостей от влияния модели программирования `x:Name` . Кроме того, `x:Name` регулируется областью имен XAML, однако `x:Uid` не регулируется ни одной из концепций, определенных языком XAML. Обработчики XAML в широком смысле (процессоры, которые не являются частью процесса локализации) не должны обеспечивать уникальность `x:Uid` значений. Эта ответственность концептуально полагается на источник значений. Ожидание уникальности `x:Uid` значений в одном источнике XAML целесообразно для потребителей значений, таких как выделенные процессы или средства глобализации. Типичная модель уникальности состоит в том, что `x:Uid` значения уникальны в XML-файле, который представляет XAML.

Средства, имеющие существенные знания о конкретной схеме XAML, могут применять `x:Uid` только к истинным локализуемого строкам, а не ко всем случаям, когда в разметке встречается текстовое значение строки.

Платформы могут указывать конкретное свойство в своей объектной модели, чтобы являться псевдонимом `x:Uid` , применяя атрибут <xref:System.Windows.Markup.UidPropertyAttribute> к определяющему типу. Если платформа определяет конкретное свойство, то нельзя одновременно указывать `x:Uid` и член, и псевдоним для одного и того же объекта. Если `x:Uid` указаны и член, и псевдоним, то API служб XAML .NET, как правило, выдает исключение <xref:System.Xaml.XamlDuplicateMemberException> для этого случая.

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

Дополнительные сведения о роли `x:Uid` в процессе локализации WPF и в форме BAML XAML см. в разделе [глобализация для WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf) или <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>См. также

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Глобализация для WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
