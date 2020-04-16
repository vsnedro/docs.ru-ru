---
title: Директива x:FieldModifier
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3e104b4c464d545e048f29901701c1c3dbb68229
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432782"
---
# <a name="xfieldmodifier-directive"></a>Директива x:FieldModifier
Изменяет поведение компиляции XAML таким образом, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> чтобы поля <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> для именованных ссылок объектов определялись с доступом вместо поведения по умолчанию.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|*Открытый*|Точная строка, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> которую вы передаете, чтобы указать по сравнению, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> варьируется в зависимости от используемого языка программирования. См. заметки.|

## <a name="dependencies"></a>Зависимости

 Если производство XAML `x:FieldModifier` используется где-либо, корневой элемент этого производства XAML должен объявить [директиву x:Class.](xclass-directive.md)

## <a name="remarks"></a>Примечания

`x:FieldModifier`не имеет значения для объявления общего уровня доступа класса или его членов. Это актуально только для поведения XAML-обработки, когда определенный объект XAML, который является частью производства XAML, обрабатывается и становится объектом, потенциально доступным на объекте графика приложения. По умолчанию ссылка на поле для такого объекта хранится в тайне, что не позволяет потребителям управления непосредственно изменять график объекта. Вместо этого предполагается, что потребители управления изменят график объекта, используя стандартные шаблоны, включенные моделями программирования, например, путем получения корневой компоновки, коллекций элементов ребенка, выделенных общедоступных свойств и так далее.

Значение атрибута `x:FieldModifier` варьируется в зависимости от языка программирования, и его назначение может варьироваться в определенных средах. Строка для использования зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>тип преобразователей он возвращается, чтобы определить значения для и , и является ли этот язык чувствительным к случаю.

- Для C, строка, чтобы <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public`пройти к назначению .

- Для Microsoft Visual Basic .NET строка <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public`для передачи в назначенный .

- Для КЗ/CLI в настоящее время не существует целевых показателей для XAML; таким образом, строка, чтобы пройти неопределенным.

Вы также <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> можете`internal` указать `Friend` (в C, в <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Visual `NotPublic` Basic), но указание необычно, потому что поведение уже по умолчанию.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>— это поведение по умолчанию, поскольку код за пределами сборки, компилированный XAML, нуждается в доступе к созданному XAML элементу. Архитектура безопасности WPF вместе с поведением компиляции XAML не будет `x:FieldModifier` декларировать поля, которые хранят экземпляры элементов, как общедоступные, если только вы специально не установите для обеспечения публичного доступа.

`x:FieldModifier`актуален только для элементов с [директивой x:Name,](xname-directive.md) поскольку это имя используется для ссылки на поле после того, как оно является общедоступным.

По умолчанию частичный класс для корневого элемента является общедоступным; однако, вы можете сделать его непубличным с помощью [директивы x:ClassModifier.](xclassmodifier-directive.md) [Директива x:ClassModifier](xclassmodifier-directive.md) также влияет на уровень доступа экземпляра класса корневого элемента. Вы можете `x:Name` поместить `x:FieldModifier` как на корневой элемент, но это делает только публичное поле копию корневого элемента, с истинным уровнем доступа к классу корневого элемента по-прежнему контролируется [x:ClassModifier Directive.](xclassmodifier-directive.md)

## <a name="see-also"></a>См. также

- [Код XAML и пользовательские классы для WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Код программной части и XAML в WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Директива x:Name](xname-directive.md)
- [Создание приложения WPF (WPF)](../../framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [Директива x:ClassModifier](xclassmodifier-directive.md)
