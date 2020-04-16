---
title: Атрибут x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: e1cd1d9db5c19decd840b433f986e0ba53557a8b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432650"
---
# <a name="xshared-attribute"></a>Атрибут x:Shared

При наборе `false`в ,изменяет поведение поиска ресурсов WPF таким образом, чтобы запросы для приписываемого ресурса создавали новый экземпляр для каждого запроса вместо совместного использования одного и того же экземпляра для всех запросов.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Примечания

`x:Shared`отображается на языке XAML XAML и признан действительным элементом языка XAML службами .NET XAML и его читателями XAML. Однако заявленные `x:Shared` возможности имеют отношение только к приложениям WPF и парзеру WPF XAML. В WPF `x:Shared` он полезен только в качестве атрибута, когда он <xref:System.Windows.ResourceDictionary>применяется к объекту, который существует в рамках WPF. Другие обычаи не выбрасывают исключения разбора или другие ошибки, но они не имеют эффекта.

Значение не `x:Shared` указывается в спецификации языка XAML. Другие реализации XAML, такие как те, которые основывается на услугах .NET XAML, не обязательно обеспечивают поддержку совместного использования ресурсов. Такие реализации XAML могут обеспечить аналогичное поведение `x:Shared` в поддерживающей структуре, которая также использует значения.

В WPF условием `x:Shared` дефолта `true`для ресурсов является . Это условие означает, что данный запрос ресурса всегда возвращает один и тот же экземпляр.

Изменение объекта, который возвращается через API <xref:System.Windows.FrameworkElement.FindResource%2A>ресурсов, например, изменение <xref:System.Windows.ResourceDictionary>объекта непосредственно внутри, изменяет исходный ресурс. Если ссылки на этот ресурс являются динамическими ссылками на ресурсы, потребители этого ресурса получают измененный ресурс.

Если ссылки на ресурс были статическими ссылками [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] на ресурсы, то изменения в ресурсе после обработки не имеют значения. Для получения дополнительной информации о статических и динамических ссылках на ресурсы [см.](../fundamentals/xaml-resources-define.md)

Явное `x:Shared="true"` указание редко выполняется, потому что это уже по умолчанию. В модели объекта WPF нет прямого кода; `x:Shared` он может быть указан только в использовании XAML и должен быть обработан либо поведением WPF по умолчанию, либо в промежуточном потоке узлов XAML на пути нагрузки при обработке с помощью .NET XAML Services и его считывателей XAML.

Сценарий `x:Shared="false"` для этого, <xref:System.Windows.FrameworkElement> если <xref:System.Windows.FrameworkContentElement> вы определяете или производный класс как ресурс, а затем вводите ресурс элемента в модель содержимого. `x:Shared="false"`позволяет вводить ресурс элемента несколько раз в <xref:System.Windows.Controls.UIElementCollection>одну и ту же коллекцию (например, в). Без `x:Shared="false"` этого является недействительным, поскольку коллекция обеспечивает уникальность своего содержимого. Однако `x:Shared="false"` поведение создает другой идентичный экземпляр ресурса вместо того, чтобы возвращать тот же экземпляр.

Другой `x:Shared="false"` сценарий, если <xref:System.Windows.Freezable> вы используете ресурс для значений анимации, но хотите изменить ресурс на основе анимации.

Обработка строки не является чувствительной `false` к делу.

В WPF, `x:Shared` действует только при следующих условиях:

- Содержащая <xref:System.Windows.ResourceDictionary> элементы `x:Shared` с обязательным испилированным. Не <xref:System.Windows.ResourceDictionary> может быть в пределах свободного XAML или используется для тем.

- Элементы, <xref:System.Windows.ResourceDictionary> содержащие элементы, <xref:System.Windows.ResourceDictionary>не должны быть вложены в другой. Например, нельзя `x:Shared` использовать элементы в <xref:System.Windows.ResourceDictionary> <xref:System.Windows.Style> элементе, <xref:System.Windows.ResourceDictionary> который находится внутри элемента, который уже является элементом.

## <a name="see-also"></a>См. также

- <xref:System.Windows.ResourceDictionary>
- [Ресурсы XAML](../fundamentals/xaml-resources-define.md)
- [Базовые элементы](../../framework/wpf/advanced/base-elements.md)
